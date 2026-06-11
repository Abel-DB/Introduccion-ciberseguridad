# Laboratorio HTML Injection

## Parte 1 - Preparación del Entorno

### Objetivo

Preparar un entorno de análisis web utilizando OWASP Juice Shop y Burp Suite para estudiar vulnerabilidades relacionadas con la manipulación de entradas controladas por el usuario.

Al finalizar esta práctica podremos:

* Ejecutar OWASP Juice Shop localmente.
* Acceder a la aplicación desde el navegador.
* Interceptar tráfico HTTP mediante Burp Suite.
* Analizar la comunicación entre cliente y servidor.

---

## Entorno Utilizado

| Componente                   | Función                                  |
| ---------------------------- | ---------------------------------------- |
| EndeavourOS Linux            | Sistema operativo                        |
| Docker                       | Ejecución aislada de Juice Shop          |
| OWASP Juice Shop             | Aplicación vulnerable para entrenamiento |
| Burp Suite Community Edition | Interceptación y análisis de tráfico     |

---

## OWASP Juice Shop

OWASP Juice Shop es una aplicación vulnerable diseñada para el entrenamiento en seguridad ofensiva. Permite practicar técnicas de análisis y explotación en un entorno controlado y legal.

Características principales:

* Código abierto.
* Diseñada para entrenamiento.
* Simula vulnerabilidades reales.
* Amplia documentación y adopción en cursos de seguridad.

---

## Despliegue con Docker

Descargamos la imagen:

```bash
docker pull bkimminich/juice-shop
```

Iniciamos el contenedor:

```bash
docker run -d -p 3000:3000 --name juice-shop bkimminich/juice-shop
```

Verificamos que se encuentra en ejecución:

```bash
docker ps
```

Resultado esperado:

```text
STATUS: Up
```

---

## Acceso a la Aplicación

Abrimos el navegador y visitamos:

```text
http://localhost:3000
```

Si todo funciona correctamente veremos la página principal de OWASP Juice Shop.

---

## Burp Suite

Burp Suite actuará como intermediario entre el navegador y la aplicación, permitiendo observar y modificar solicitudes HTTP.

Herramientas utilizadas:

| Herramienta  | Función              |
| ------------ | -------------------- |
| Proxy        | Interceptar tráfico  |
| HTTP History | Revisar solicitudes  |
| Repeater     | Modificar peticiones |
| Burp Browser | Navegador integrado  |

### Inicio

Seleccionar:

```text
Temporary Project
```

Luego:

```text
Use Burp Defaults
```

Finalmente:

```text
Start Burp
```

---

## Burp Browser

Desde:

```text
Proxy → Intercept
```

Seleccionamos:

```text
Open Browser
```

Burp abrirá un navegador configurado para utilizar automáticamente el proxy.

---

## Verificación de Intercepción

Activamos:

```text
Intercept is on
```

Accedemos a:

```text
http://localhost:3000
```

Si Burp detiene una solicitud similar a:

```http
GET / HTTP/1.1
```

podemos confirmar que la configuración es correcta.

---

## Resultado Esperado

Al finalizar esta fase deberíamos tener:

| Verificación            | Estado |
| ----------------------- | ------ |
| Docker operativo        | ✓      |
| Juice Shop ejecutándose | ✓      |
| Acceso a localhost:3000 | ✓      |
| Burp Suite funcionando  | ✓      |
| Burp Browser operativo  | ✓      |
| Intercepción activa     | ✓      |

---

# Parte 2 - Comprendiendo HTML Injection

## Objetivo

Comprender qué es HTML Injection e identificar posibles puntos de entrada dentro de la aplicación.

Al finalizar podremos:

* Entender el funcionamiento de HTML Injection.
* Diferenciar entre texto y HTML interpretado.
* Identificar funcionalidades candidatas para pruebas.
* Formular hipótesis basadas en observaciones.

---

## ¿Qué es HTML Injection?

HTML Injection ocurre cuando una aplicación permite que contenido HTML controlado por el usuario sea interpretado por el navegador en lugar de mostrarse como texto.

Ejemplo:

Entrada:

```html
<h1>TEST</h1>
```

Comportamiento seguro:

```text
<h1>TEST</h1>
```

Comportamiento vulnerable:

# TEST

La etiqueta es interpretada y renderizada como un elemento HTML real.

---

## Metodología

Durante el análisis seguiremos el siguiente proceso:

1. Reconocimiento.
2. Observación.
3. Formulación de hipótesis.
4. Prueba controlada.
5. Recolección de evidencias.
6. Conclusión.

Pregunta clave:

> ¿La aplicación vuelve a mostrar información controlada por el usuario?

Si la respuesta es sí, existe un candidato interesante para análisis.

---

## Reconocimiento de la Aplicación

Durante la exploración observamos varias funcionalidades:

| Funcionalidad    | Entrada controlada por el usuario |
| ---------------- | --------------------------------- |
| Buscador         | Sí                                |
| Registro         | Sí                                |
| Inicio de sesión | Sí                                |
| Reseñas          | Sí                                |
| Productos        | No directamente                   |

El buscador resulta especialmente interesante porque modifica inmediatamente la interfaz utilizando datos introducidos por el usuario.

---

## Hipótesis Inicial

Si el buscador utiliza información proporcionada por el usuario para actualizar la interfaz, podría existir la posibilidad de que también interprete HTML.

Para comprobarlo introducimos:

```html
<h1>TEST</h1>
```

en el buscador.

---

## Observación

La aplicación no muestra:

```text
<h1>TEST</h1>
```

En su lugar observamos:

# TEST

Esto sugiere que el navegador está interpretando la etiqueta HTML.

---

## Evidencias Iniciales

✓ El usuario controla la entrada.

✓ La interfaz utiliza dicha entrada.

✓ El navegador parece interpretar HTML.

Sin embargo, todavía no podemos confirmar dónde ocurre la interpretación.

Para ello analizaremos el tráfico HTTP.

---

## Análisis con Burp Suite

En:

```text
Proxy → HTTP History
```

identificamos una solicitud similar a:

```http
GET /rest/products/search?q=
```

Información relevante:

| Elemento  | Valor                 |
| --------- | --------------------- |
| Endpoint  | /rest/products/search |
| Método    | GET                   |
| Parámetro | q                     |

---

## Análisis con Repeater

Enviamos la solicitud a Repeater:

```text
Click derecho → Send to Repeater
```

Modificamos:

```http
q=
```

por:

```http
q=<h1>TEST</h1>
```

y enviamos la petición.

Respuesta obtenida:

```json
{
  "status":"success",
  "data":[]
}
```

---

## Resultados

Observamos que:

* El servidor responde con JSON.
* No devuelve HTML interpretado.
* No genera elementos HTML visibles en la respuesta.

Esto plantea una pregunta importante:

> Si el servidor devuelve únicamente JSON, ¿dónde ocurre la interpretación observada?

Para responderla analizaremos el DOM.

---

# Parte 3 - Verificación con DevTools

## Objetivo

Determinar si el navegador está creando elementos HTML reales dentro del DOM.

---

## ¿Qué es el DOM?

El DOM (Document Object Model) es la representación interna de una página web utilizada por el navegador.

Cuando el navegador interpreta HTML, crea nodos dentro del DOM para representar cada elemento.

Por este motivo, inspeccionar el DOM permite diferenciar entre texto e HTML interpretado.

---

## Inspección

Abrimos DevTools:

```text
F12
```

o:

```text
Click derecho → Inspect
```

Dentro de la pestaña:

```text
Elements
```

buscamos:

```text
TEST
```

---

## Resultado

Encontramos un elemento similar a:

```html
<span id="searchValue">
    <h1>TEST</h1>
</span>
```

Si el contenido hubiera sido tratado como texto esperaríamos algo parecido a:

```html
<span id="searchValue">
    &lt;h1&gt;TEST&lt;/h1&gt;
</span>
```

Sin embargo observamos un elemento HTML real dentro del DOM.

---

## Correlación de Evidencias

| Evidencia                               | Resultado |
| --------------------------------------- | --------- |
| El usuario controla la entrada          | Sí        |
| La aplicación utiliza la entrada        | Sí        |
| El navegador interpreta HTML            | Sí        |
| Existen nuevos elementos HTML en el DOM | Sí        |
| El servidor devuelve JSON               | Sí        |
| El servidor interpreta HTML             | No        |

---

## Reconstrucción del Proceso

```text
Entrada del usuario
        ↓
Petición HTTP
        ↓
Respuesta JSON
        ↓
JavaScript procesa datos
        ↓
Modificación del DOM
        ↓
Renderizado HTML
```

La interpretación ocurre después de recibir la respuesta del servidor.

---

## Conclusión Técnica

Las evidencias obtenidas permiten concluir que:

* El usuario controla la entrada.
* El navegador interpreta HTML.
* El servidor devuelve únicamente JSON.
* DevTools confirma la creación de elementos HTML reales.

Por tanto, la interpretación no ocurre en el servidor sino en el navegador.

---

## Clasificación

| Elemento       | Resultado                |
| -------------- | ------------------------ |
| Vulnerabilidad | HTML Injection           |
| Ubicación      | Frontend                 |
| Clasificación  | DOM-Based HTML Injection |

---

## Impacto

La vulnerabilidad permite incorporar contenido HTML controlado por el usuario dentro de la interfaz.

Posibles consecuencias:

| Impacto                  | Descripción                               |
| ------------------------ | ----------------------------------------- |
| Alteración visual        | Modificación de la apariencia             |
| Inserción de contenido   | Inclusión de HTML arbitrario              |
| Engaño al usuario        | Creación de mensajes o formularios falsos |
| Manipulación de interfaz | Alteración del contenido mostrado         |

---

# Caso Comparativo - Sistema de Reseñas

Durante una auditoría también es importante identificar comportamientos seguros.

Introducimos:

```html
<h1>TEST</h1>
```

como contenido de una reseña.

Resultado observado:

```text
<h1>TEST</h1>
```

El contenido es mostrado como texto.

---

## Análisis

| Comportamiento               | Resultado |
| ---------------------------- | --------- |
| El contenido se almacena     | Sí        |
| El contenido se muestra      | Sí        |
| El navegador interpreta HTML | No        |
| Se crean elementos HTML      | No        |

Conclusión:

```text
No existe HTML Injection.
```

---

## Diferencia Fundamental

| Situación                          | HTML Injection |
| ---------------------------------- | -------------- |
| HTML almacenado como texto         | No             |
| HTML mostrado como texto           | No             |
| HTML interpretado por el navegador | Sí             |

La vulnerabilidad aparece únicamente cuando contenido HTML controlado por el usuario es interpretado y convertido en elementos reales dentro del DOM.

---

# Conclusión General

Durante el análisis del buscador de OWASP Juice Shop se comprobó que contenido HTML controlado por el usuario era insertado e interpretado dentro del DOM. El análisis con Burp Suite mostró que el servidor únicamente devolvía respuestas JSON y no generaba HTML interpretado. La inspección mediante DevTools confirmó la creación de elementos HTML reales a partir de la entrada del usuario.

Con base en estas evidencias se concluyó la existencia de una vulnerabilidad de DOM-Based HTML Injection localizada en el frontend de la aplicación.

Como contraste, el sistema de reseñas almacenaba y mostraba etiquetas HTML como texto plano, por lo que no se identificó HTML Injection en dicha funcionalidad.
