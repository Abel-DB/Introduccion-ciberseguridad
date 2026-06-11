# Laboratorio HTML Injection

## Parte 1 - Preparación del Entorno

### Objetivo

Preparar un laboratorio local para analizar vulnerabilidades web utilizando OWASP Juice Shop y Burp Suite.

En este laboratorio se utilizará:

| Componente                   | Función                                         |
| ---------------------------- | ----------------------------------------------- |
| EndeavourOS Linux            | Sistema operativo utilizado durante las pruebas |
| Docker                       | Ejecución aislada de Juice Shop                 |
| OWASP Juice Shop             | Aplicación vulnerable para entrenamiento        |
| Burp Suite Community Edition | Interceptación y análisis de tráfico HTTP       |

Al finalizar esta práctica podremos:

* Ejecutar Juice Shop localmente.
* Acceder a la aplicación desde el navegador.
* Interceptar tráfico HTTP utilizando Burp Suite.
* Analizar las comunicaciones entre navegador y aplicación.

---

## Entorno Utilizado

Sistema operativo:

```text
EndeavourOS Linux
```

Es importante documentar el entorno utilizado porque algunos procedimientos pueden variar entre Linux, Windows y macOS.

Todas las pruebas descritas en este laboratorio fueron realizadas sobre Linux EndeavourOS.

---

## ¿Qué es OWASP Juice Shop?

OWASP Juice Shop es una aplicación web vulnerable desarrollada específicamente para entrenamiento en seguridad informática.

Fue diseñada para que estudiantes, analistas y pentesters puedan practicar técnicas de análisis y explotación en un entorno legal y controlado.

### Características

| Característica          | Descripción                                  |
| ----------------------- | -------------------------------------------- |
| Código abierto          | Puede ser descargada y estudiada libremente  |
| Entorno seguro          | Diseñada para entrenamiento                  |
| Vulnerabilidades reales | Simula problemas comunes en aplicaciones web |
| Amplia documentación    | Utilizada en cursos y laboratorios           |

---

## ¿Por Qué Utilizaremos Docker?

Docker permite ejecutar aplicaciones dentro de contenedores aislados.

Un contenedor puede entenderse como un entorno independiente que contiene todo lo necesario para ejecutar una aplicación.

### Ventajas

| Ventaja                  | Beneficio                                             |
| ------------------------ | ----------------------------------------------------- |
| Aislamiento              | No afecta al sistema operativo principal              |
| Reproducibilidad         | El laboratorio puede recrearse fácilmente             |
| Portabilidad             | Funciona de forma similar en distintos equipos        |
| Facilidad de eliminación | Puede eliminarse sin dejar configuraciones residuales |

---

## Descarga de OWASP Juice Shop

Abrimos una terminal y ejecutamos:

```bash
docker pull bkimminich/juice-shop
```

### Explicación del Comando

| Elemento              | Función                                   |
| --------------------- | ----------------------------------------- |
| docker                | Ejecuta Docker                            |
| pull                  | Descarga una imagen desde Docker Hub      |
| bkimminich/juice-shop | Nombre de la imagen oficial de Juice Shop |

Cuando finalice la descarga tendremos disponible una copia local de la aplicación.

---

## Ejecución del Contenedor

Iniciamos Juice Shop mediante:

```bash
docker run -d -p 3000:3000 --name juice-shop bkimminich/juice-shop
```

### Explicación de los Parámetros

| Parámetro         | Función                                |
| ----------------- | -------------------------------------- |
| run               | Crea e inicia un contenedor            |
| -d                | Ejecuta el contenedor en segundo plano |
| -p 3000:3000      | Expone el puerto 3000 del contenedor   |
| --name juice-shop | Asigna un nombre al contenedor         |

Una vez ejecutado el comando Docker devolverá un identificador correspondiente al contenedor creado.

---

## Verificación del Contenedor

Para comprobar que Juice Shop se encuentra en ejecución utilizamos:

```bash
docker ps
```

### Explicación

| Comando   | Función                          |
| --------- | -------------------------------- |
| docker ps | Muestra los contenedores activos |

Resultado esperado:

```text
STATUS: Up
```

Si observamos el estado "Up" significa que el contenedor está funcionando correctamente.

---

## Acceso a la Aplicación

Abrimos el navegador y visitamos:

```text
http://localhost:3000
```

### ¿Qué Significa Esta Dirección?

| Elemento  | Descripción                             |
| --------- | --------------------------------------- |
| localhost | Hace referencia a nuestro propio equipo |
| 3000      | Puerto utilizado por Juice Shop         |

Si la aplicación se encuentra funcionando correctamente veremos la página principal de OWASP Juice Shop.

---

## ¿Qué es Burp Suite?

Burp Suite es una plataforma utilizada para analizar aplicaciones web.

Durante este laboratorio actuará como intermediario entre el navegador y Juice Shop.

Esto nos permitirá observar exactamente qué información se envía y qué información se recibe.

### Funcionalidades Utilizadas

| Herramienta  | Uso durante el laboratorio       |
| ------------ | -------------------------------- |
| Proxy        | Interceptar tráfico              |
| HTTP History | Revisar solicitudes realizadas   |
| Repeater     | Modificar peticiones manualmente |
| Burp Browser | Navegador integrado de Burp      |

---

## Inicio de Burp Suite

Abrimos Burp Suite Community Edition.

Durante el inicio seleccionamos:

```text
Temporary Project
```

Posteriormente:

```text
Use Burp Defaults
```

Finalmente:

```text
Start Burp
```

Burp cargará la interfaz principal.

---

## Apertura de Burp Browser

Accedemos a:

```text
Proxy → Intercept
```

Posteriormente seleccionamos:

```text
Open Browser
```

Burp abrirá un navegador Chromium preconfigurado para utilizar automáticamente el proxy.

### Ventajas de Burp Browser

| Ventaja                        | Descripción                                |
| ------------------------------ | ------------------------------------------ |
| Configuración automática       | No requiere modificar navegadores externos |
| Integración con Burp           | Todo el tráfico pasa por el proxy          |
| Menos errores de configuración | Ideal para laboratorios                    |

---

## Verificación de Intercepción

En Burp activamos:

```text
Intercept is on
```

Desde Burp Browser accedemos a:

```text
http://localhost:3000
```

Si Burp detiene una solicitud similar a:

```http
GET / HTTP/1.1
```

podemos confirmar que el navegador está utilizando correctamente el proxy.

---

## Resultado Esperado

Al finalizar esta práctica debemos haber conseguido lo siguiente:

| Verificación                   | Estado esperado |
| ------------------------------ | --------------- |
| Docker funcionando             | ✓               |
| Juice Shop ejecutándose        | ✓               |
| Acceso a localhost:3000        | ✓               |
| Burp Suite operativo           | ✓               |
| Burp Browser funcionando       | ✓               |
| Intercepción de tráfico activa | ✓               |

Con el entorno preparado ya podremos comenzar el análisis de la aplicación y estudiar el comportamiento de entradas controladas por el usuario en la siguiente parte.

---

## Parte 2 - Comprendiendo HTML Injection e Inicio del Análisis

### Objetivo

Comprender qué es HTML Injection y comenzar el análisis de OWASP Juice Shop utilizando observación directa y Burp Suite.

Al finalizar esta parte podremos:

* Comprender qué es HTML Injection.
* Diferenciar entre texto e HTML interpretado.
* Identificar posibles candidatos para pruebas.
* Formular hipótesis basadas en evidencias.
* Analizar el comportamiento inicial de la aplicación.

---

## ¿Qué es HTML Injection?

HTML Injection ocurre cuando una aplicación permite que contenido HTML controlado por el usuario sea interpretado por el navegador en lugar de mostrarse como texto.

En otras palabras, el navegador procesa etiquetas HTML introducidas por un usuario y las incorpora a la página.

---

## Ejemplo Conceptual

Supongamos que un usuario introduce:

```html
<h1>TEST</h1>
```

Pueden ocurrir dos situaciones.

### Comportamiento Seguro

La aplicación muestra:

```text
<h1>TEST</h1>
```

El navegador trata el contenido como texto.

No existe interpretación HTML.

---

### Comportamiento Vulnerable

La aplicación muestra:

## TEST

En este caso el navegador interpreta la etiqueta HTML y crea un encabezado real.

---

## Error Común Durante una Auditoría

Muchos principiantes comienzan probando payloads en todos los campos disponibles.

Por ejemplo:

```text
Buscador
Perfil
Comentarios
Reseñas
Direcciones
Mensajes
```

Este enfoque suele ser lento y genera mucho ruido.

Antes de enviar payloads debemos intentar comprender cómo funciona la aplicación.

---

## Metodología Utilizada

Durante este laboratorio utilizaremos la siguiente metodología:

| Paso           | Objetivo                                 |
| -------------- | ---------------------------------------- |
| Reconocimiento | Identificar funcionalidades interesantes |
| Observación    | Analizar cómo responde la aplicación     |
| Hipótesis      | Formular una posible explicación         |
| Prueba         | Ejecutar una prueba controlada           |
| Evidencia      | Recopilar información objetiva           |
| Conclusión     | Determinar si existe una vulnerabilidad  |

---

## Pregunta Clave

Antes de probar HTML debemos preguntarnos:

> ¿La aplicación vuelve a mostrar información controlada por el usuario?

Si la respuesta es sí:

```text
Posible candidato para análisis
```

Si la respuesta es no:

```text
Menor prioridad durante las pruebas iniciales
```

---

## Reconocimiento de OWASP Juice Shop

Abrimos OWASP Juice Shop desde Burp Browser.

Observamos diferentes funcionalidades:

| Funcionalidad    | ¿Controlada por el usuario? |
| ---------------- | --------------------------- |
| Buscador         | Sí                          |
| Registro         | Sí                          |
| Inicio de sesión | Sí                          |
| Reseñas          | Sí                          |
| Productos        | No directamente             |

Nuestro objetivo es identificar una funcionalidad donde la información introducida por el usuario pueda influir en la interfaz.

---

## Selección del Buscador

Durante la exploración observamos que el buscador modifica el contenido mostrado en pantalla según el valor introducido.

Esto llama nuestra atención porque existe una relación directa entre:

```text
Entrada del usuario
↓
Cambio visible en la interfaz
```

Por este motivo seleccionamos el buscador como candidato inicial para análisis.

---

## Primera Hipótesis

Si el buscador utiliza información controlada por el usuario para actualizar la interfaz, podría existir la posibilidad de que también interprete HTML.

Para comprobarlo realizaremos una prueba sencilla.

---

## Prueba Inicial

Introducimos en el buscador:

```html
<h1>TEST</h1>
```

y ejecutamos la búsqueda.

---

## Observación Visual

La aplicación no muestra:

```text
<h1>TEST</h1>
```

En su lugar observamos:

## TEST

La palabra aparece renderizada como un encabezado.

---

## Análisis de la Observación

Esta es una evidencia importante.

Si el navegador mostrara literalmente:

```text
<h1>TEST</h1>
```

podríamos concluir que el contenido se trata como texto.

Sin embargo observamos que la etiqueta es interpretada y convertida en un elemento visual.

---

## Evidencia Obtenida

Podemos afirmar que:

✓ El usuario controla una entrada.

✓ La aplicación utiliza esa entrada para modificar la interfaz.

✓ El navegador parece interpretar la etiqueta HTML.

---

## ¿Es Suficiente Para Confirmar una Vulnerabilidad?

Todavía no.

Aunque la evidencia visual es muy fuerte, aún debemos responder varias preguntas:

* ¿Qué petición genera la aplicación?
* ¿Qué parámetro recibe nuestros datos?
* ¿Qué devuelve el servidor?
* ¿Dónde ocurre exactamente la interpretación?

Para responder estas preguntas utilizaremos Burp Suite.

---

## Análisis con Burp Suite

Abrimos:

```text
Proxy → HTTP History
```

Buscamos las solicitudes generadas por la búsqueda.

Durante las pruebas observamos una petición similar a:

```http
GET /rest/products/search?q=
```

---

## Información Identificada

Aunque el valor introducido no aparece claramente reflejado en la petición observada, sí podemos identificar elementos importantes.

| Elemento    | Valor                 |
| ----------- | --------------------- |
| Endpoint    | /rest/products/search |
| Parámetro   | q                     |
| Método HTTP | GET                   |

Esto nos permite identificar el componente responsable de la búsqueda.

---

## Envío a Repeater

Seleccionamos la petición.

Posteriormente:

```text
Click derecho → Send to Repeater
```

Abrimos la pestaña:

```text
Repeater
```

---

## ¿Por Qué Utilizamos Repeater?

Repeater permite modificar manualmente una solicitud y analizar la respuesta generada por el servidor.

Ventajas:

| Ventaja              | Beneficio                                     |
| -------------------- | --------------------------------------------- |
| Control total        | Modificamos exactamente lo que enviamos       |
| Repetición rápida    | Podemos realizar múltiples pruebas            |
| Análisis aislado     | Eliminamos variables de la interfaz           |
| Comparación sencilla | Podemos observar diferencias entre respuestas |

---

## Modificación de la Solicitud

Dentro de Repeater modificamos:

```http
q=
```

por:

```http
q=<h1>TEST</h1>
```

Posteriormente presionamos:

```text
Send
```

---

## Respuesta Observada

El servidor responde:

```json
{
  "status":"success",
  "data":[]
}
```

---

## Análisis de la Respuesta

Observamos que:

| Observación                  | Resultado |
| ---------------------------- | --------- |
| Respuesta HTML               | No        |
| Respuesta JSON               | Sí        |
| HTML interpretado            | No        |
| Generación de etiquetas HTML | No        |

---

## Hipótesis Actual

Hasta este momento sabemos que:

| Evidencia                              | Resultado |
| -------------------------------------- | --------- |
| El usuario controla la entrada         | Sí        |
| El navegador interpreta HTML           | Sí        |
| El servidor devuelve JSON              | Sí        |
| El servidor devuelve HTML interpretado | No        |

Esto plantea una pregunta importante:

> Si el servidor no devuelve HTML interpretado, ¿dónde está ocurriendo la interpretación?

---

## Evidencias Reunidas Hasta el Momento

✓ El buscador utiliza información controlada por el usuario.

✓ El navegador interpreta HTML.

✓ El endpoint identificado es:

```text
/rest/products/search
```

✓ El parámetro utilizado es:

```text
q
```

✓ El servidor devuelve JSON.

✓ No observamos evidencia de interpretación HTML por parte del servidor.

---

## Próximo Paso

Todavía debemos responder varias preguntas:

1. ¿El navegador está creando elementos HTML reales?
2. ¿El DOM fue modificado?
3. ¿La interpretación ocurre en el navegador?
4. ¿Existe realmente HTML Injection?

Para responder estas preguntas inspeccionaremos el DOM utilizando DevTools en la siguiente parte del laboratorio.

---

## Parte 3 - Verificación con DevTools y Conclusión de la Vulnerabilidad

### Objetivo

Confirmar si el navegador está creando elementos HTML reales dentro del DOM y determinar dónde ocurre la interpretación observada durante las pruebas.

Hasta este momento hemos obtenido las siguientes evidencias:

| Evidencia                                | Resultado             |
| ---------------------------------------- | --------------------- |
| El usuario controla la entrada           | Sí                    |
| El navegador interpreta HTML visualmente | Sí                    |
| El endpoint identificado                 | /rest/products/search |
| El parámetro utilizado                   | q                     |
| El servidor devuelve JSON                | Sí                    |

Ahora debemos verificar qué está ocurriendo dentro del navegador.

---

## ¿Qué es el DOM?

DOM significa:

```text
Document Object Model
```

Es la representación interna que el navegador construye de una página web.

Cuando una página contiene elementos HTML como:

```html
<h1>TEST</h1>
```

el navegador crea nodos dentro del DOM para representar esos elementos.

Por este motivo, inspeccionar el DOM nos permite comprobar si el contenido fue tratado como texto o si fue interpretado como HTML.

---

## Apertura de DevTools

Con OWASP Juice Shop abierto, presionamos:

```text
F12
```

También podemos utilizar:

```text
Click derecho → Inspect
```

Se abrirán las herramientas de desarrollo del navegador.

---

## Inspección del DOM

Seleccionamos la pestaña:

```text
Elements
```

Posteriormente utilizamos la búsqueda:

```text
Ctrl + F
```

Buscamos:

```text
TEST
```

---

## Resultado Observado

Durante la inspección encontramos un elemento similar a:

```html
<span id="searchValue">
    <h1>TEST</h1>
</span>
```

---

## ¿Por Qué es Importante?

Esta observación nos proporciona una evidencia muy valiosa.

Si la aplicación estuviera tratando nuestro contenido como texto, esperaríamos encontrar algo similar a:

```html
<span id="searchValue">
    &lt;h1&gt;TEST&lt;/h1&gt;
</span>
```

o simplemente una cadena de texto.

Sin embargo, encontramos un elemento:

```html
<h1>
```

real dentro del DOM.

---

## Primera Conclusión

Podemos afirmar que:

✓ El navegador creó un nuevo elemento HTML.

✓ El contenido no fue tratado como texto.

✓ Existe interpretación de HTML controlado por el usuario.

---

## Relacionando las Evidencias

Ahora analizaremos todas las evidencias obtenidas durante el laboratorio.

---

### Evidencia 1 - Observación Visual

Introducimos:

```html
<h1>TEST</h1>
```

Resultado observado:

## TEST

El navegador renderiza un encabezado real.

---

### Evidencia 2 - Tráfico HTTP

Petición identificada:

```http
GET /rest/products/search?q=
```

Respuesta observada:

```json
{
  "status":"success",
  "data":[]
}
```

La respuesta corresponde a un objeto JSON.

---

### Evidencia 3 - Inspección del DOM

DevTools muestra:

```html
<span id="searchValue">
    <h1>TEST</h1>
</span>
```

El elemento HTML existe realmente dentro del DOM.

---

## ¿Por Qué la Vulnerabilidad No Ocurre en el Servidor?

Una vez confirmada la interpretación HTML debemos determinar dónde ocurre exactamente.

Para ello analizamos las evidencias obtenidas.

---

### Respuesta del Servidor

La petición enviada fue:

```http
GET /rest/products/search?q=<h1>TEST</h1>
```

La respuesta observada fue:

```json
{
  "status":"success",
  "data":[]
}
```

Observamos que el servidor responde únicamente con JSON.

No devuelve:

```html
<h1>TEST</h1>
```

Tampoco genera una página HTML que contenga nuestro payload.

---

### ¿Qué Esperaríamos Si la Vulnerabilidad Estuviera en el Servidor?

Si el servidor fuera responsable de la interpretación HTML podríamos esperar observar:

| Posible evidencia                    | ¿Se observa? |
| ------------------------------------ | ------------ |
| HTML generado por el servidor        | No           |
| Payload reflejado en la respuesta    | No           |
| HTML interpretado en la respuesta    | No           |
| Página HTML generada por el servidor | No           |

Durante las pruebas no observamos ninguna de estas situaciones.

---

### Comportamiento del Navegador

A pesar de que el servidor responde únicamente con JSON, la aplicación muestra:

## TEST

Esto significa que la interpretación ocurre después de recibir la respuesta.

---

### Evidencia del DOM

DevTools muestra:

```html
<span id="searchValue">
    <h1>TEST</h1>
</span>
```

Este elemento no aparece dentro de la respuesta JSON.

Fue creado posteriormente por el navegador.

---

## Reconstrucción del Proceso

Durante las pruebas observamos la siguiente secuencia:

```text
Usuario introduce:

<h1>TEST</h1>

↓

La aplicación genera:

GET /rest/products/search?q=<h1>TEST</h1>

↓

El servidor responde:

{
  "status":"success",
  "data":[]
}

↓

JavaScript procesa la información recibida

↓

El navegador modifica el DOM

↓

Se crea un nuevo elemento HTML

↓

TEST aparece como encabezado
```

---

## Evidencias Finales

| Evidencia                              | Resultado |
| -------------------------------------- | --------- |
| El usuario controla la entrada         | Sí        |
| La aplicación utiliza esa entrada      | Sí        |
| El navegador interpreta HTML           | Sí        |
| DevTools muestra nuevos elementos HTML | Sí        |
| El servidor devuelve JSON              | Sí        |
| El servidor interpreta HTML            | No        |

---

## Conclusión Técnica

Las evidencias obtenidas indican que:

* El usuario controla la entrada.
* El navegador interpreta HTML.
* El servidor devuelve JSON.
* El servidor no devuelve HTML interpretado.
* DevTools confirma la creación de elementos HTML dentro del DOM.

Por tanto, la interpretación no ocurre en el servidor.

La interpretación ocurre en el navegador.

---

## Clasificación de la Vulnerabilidad

| Elemento       | Resultado                |
| -------------- | ------------------------ |
| Vulnerabilidad | HTML Injection           |
| Ubicación      | Frontend                 |
| Clasificación  | DOM-Based HTML Injection |

---

## Impacto

La vulnerabilidad permite que contenido HTML controlado por el usuario sea incorporado al DOM y mostrado dentro de la interfaz.

Dependiendo del contexto de la aplicación, esto podría permitir:

| Posible Impacto | Descripción |
|----------------|-------------|
| Alteración visual | Modificación de la apariencia de la página |
| Inserción de contenido | Inclusión de elementos HTML arbitrarios |
| Engaño al usuario | Creación de formularios o mensajes falsos |
| Manipulación de interfaz | Alteración del contenido visible para el usuario |

En este laboratorio el impacto observado consiste en la capacidad de insertar elementos HTML dentro de la interfaz mediante contenido controlado por el usuario.

---

## Caso Comparativo - Sistema de Reseñas

Hasta este momento hemos analizado un caso vulnerable.

Sin embargo, durante una auditoría también es importante demostrar cuándo una funcionalidad **no es vulnerable**.

Por este motivo analizaremos el sistema de reseñas.

---

## Prueba Realizada

Introducimos:

```html
<h1>TEST</h1>
```

como contenido de una reseña.

---

## Observación Visual

La aplicación muestra:

```text
<h1>TEST</h1>
```

No aparece ningún encabezado.

---

## Análisis

Observaciones:

| Comportamiento                 | Resultado |
| ------------------------------ | --------- |
| El contenido es almacenado     | Sí        |
| El contenido es devuelto       | Sí        |
| El navegador interpreta HTML   | No        |
| Se crean nuevos elementos HTML | No        |

---

## Conclusión del Caso Comparativo

Aunque la aplicación almacena contenido HTML, dicho contenido es tratado como texto.

Por tanto:

```text
No existe HTML Injection.
```

---

## Diferencia Entre Almacenar e Interpretar HTML

Uno de los errores más comunes consiste en asumir que almacenar HTML implica una vulnerabilidad.

Esto es incorrecto.

| Situación                                              | ¿Existe HTML Injection? |
| ------------------------------------------------------ | ----------------------- |
| Se almacena HTML como texto                            | No                      |
| Se devuelve HTML como texto                            | No                      |
| El navegador interpreta HTML controlado por el usuario | Sí                      |

La vulnerabilidad aparece cuando el navegador interpreta contenido HTML controlado por el usuario y lo convierte en elementos reales dentro del DOM.

---

## Metodología Utilizada

Durante este laboratorio se siguió la siguiente metodología:

1. Reconocimiento de la aplicación.
2. Identificación de entradas controladas por el usuario.
3. Formulación de hipótesis.
4. Observación visual.
5. Análisis HTTP con Burp Suite.
6. Modificación de peticiones mediante Repeater.
7. Inspección del DOM con DevTools.
8. Correlación de evidencias.
9. Determinación del origen de la vulnerabilidad.
10. Documentación del hallazgo.

---

## Preguntas que Debe Responder una Auditoría

Durante el análisis intentamos responder las siguientes preguntas:

1. ¿Qué entrada controla el usuario?
2. ¿La aplicación refleja esa entrada?
3. ¿El navegador interpreta HTML?
4. ¿Dónde ocurre la interpretación?
5. ¿Qué devuelve el servidor?
6. ¿El DOM fue modificado?
7. ¿Existe impacto real?
8. ¿La vulnerabilidad ocurre en frontend o backend?

Responder estas preguntas permitió llegar a una conclusión basada en evidencias y no únicamente en observaciones visuales.

---

## Conclusión General del Laboratorio

Durante el laboratorio se analizaron dos comportamientos diferentes dentro de OWASP Juice Shop.

En el buscador se observó que contenido HTML controlado por el usuario era interpretado por el navegador y convertido en elementos reales dentro del DOM. El análisis de las respuestas HTTP mostró que el servidor únicamente devolvía JSON, mientras que DevTools confirmó la creación de nuevos elementos HTML. Estas evidencias permitieron concluir la existencia de una vulnerabilidad de DOM-Based HTML Injection ubicada en el frontend.

Por otra parte, el sistema de reseñas almacenaba y devolvía contenido HTML, pero este era tratado como texto y no era interpretado por el navegador. Por tanto, no se identificó HTML Injection en dicha funcionalidad.

La combinación de observación visual, análisis HTTP e inspección del DOM permitió demostrar técnicamente dónde ocurría la vulnerabilidad y diferenciar correctamente entre almacenar HTML e interpretarlo.

