# Evil Twin

## Introducción

**Evil Twin** es un ataque inalámbrico en el que un atacante crea un punto de acceso Wi-Fi falso que imita una red legítima.

El objetivo es engañar a las víctimas para que se conecten a la red maliciosa y permitir la captura de información o la realización de ataques adicionales.

Es una técnica estrechamente relacionada con los ataques **Man in the Middle (MITM)**.

---

## ¿Qué Significa Evil Twin?

La expresión:

```text id="m61pyl"
Evil Twin
```

puede traducirse como:

```text id="fmp6gn"
Gemelo Malvado
```

El nombre hace referencia a una red falsa que intenta parecer idéntica a una red legítima.

Ejemplo:

```text id="ozr0r9"
Red legítima:
Universidad-WiFi

Red falsa:
Universidad-WiFi
```

Para el usuario ambas pueden parecer exactamente iguales.

---

## Objetivo del Ataque

El atacante busca que la víctima se conecte a la red falsa.

Una vez conectado el usuario, el atacante puede:

* Interceptar tráfico.
* Capturar credenciales.
* Redirigir páginas web.
* Distribuir malware.
* Realizar ataques MITM.

---

## Funcionamiento General

Escenario normal:

```text id="j9mwwv"
Usuario
    ↓
WiFi Legítima
    ↓
Internet
```

Ataque Evil Twin:

```text id="1y0gkq"
Usuario
    ↓
WiFi Falsa
    ↓
Atacante
    ↓
Internet
```

La víctima cree estar utilizando la red legítima.

---

## Fases del Ataque

### Reconocimiento

El atacante identifica una red Wi-Fi existente.

Ejemplo:

```text id="5g7sn5"
Universidad-WiFi
```

---

### Creación del Punto de Acceso Falso

Se configura una red con:

* Mismo SSID.
* Configuración similar.
* Apariencia legítima.

---

### Atracción de Víctimas

Los usuarios visualizan ambas redes y pueden conectarse a la falsa.

En algunos casos el atacante intenta aumentar la potencia de señal para hacerla más atractiva.

---

### Intercepción

Una vez conectada la víctima, el atacante puede observar o manipular el tráfico.

---

## Relación con Deauthentication

Frecuentemente el ataque Evil Twin se combina con:

```text id="9qv18d"
Deauthentication
```

El atacante fuerza la desconexión de los usuarios de la red legítima.

Posteriormente los dispositivos intentan reconectarse y pueden terminar conectándose a la red falsa.

---

## Información que Puede Robarse

Dependiendo del escenario:

* Usuarios y contraseñas.
* Cookies de sesión.
* Datos personales.
* Correos electrónicos.
* Información corporativa.
* Credenciales de acceso.

---

## Portales Cautivos Falsos

Un método común consiste en mostrar una página falsa de autenticación.

Ejemplo:

```text id="u3r0v4"
Bienvenido a la Red Wi-Fi

Ingrese sus credenciales institucionales
```

La víctima introduce sus datos y estos son capturados por el atacante.

---

## Evil Twin en Redes Públicas

Los entornos más habituales son:

* Aeropuertos
* Hoteles
* Cafeterías
* Centros comerciales
* Eventos públicos
* Universidades

En estos lugares los usuarios suelen conectarse rápidamente sin verificar la autenticidad de la red.

---

## Diferencia entre Evil Twin y Rogue Access Point

### Rogue Access Point

Punto de acceso no autorizado.

No necesariamente intenta imitar otra red.

### Evil Twin

Su propósito es hacerse pasar por una red legítima específica.

---

## Impacto del Ataque

Un ataque exitoso puede provocar:

* Robo de credenciales.
* Acceso no autorizado.
* Pérdida de privacidad.
* Compromiso de cuentas.
* Infecciones por malware.
* Ataques posteriores dentro de una organización.

---

## Indicadores de Alerta

Algunas señales que pueden indicar un Evil Twin:

### Redes Duplicadas

Dos redes con nombres idénticos o muy similares.

---

### Solicitudes Inusuales

Petición inesperada de credenciales.

---

### Certificados Inválidos

Advertencias del navegador al acceder a sitios HTTPS.

---

### Comportamientos Extraños

Redirecciones inesperadas o páginas sospechosas.

---

## Medidas de Protección

### Verificar la Red Correcta

Confirmar el nombre oficial de la red antes de conectarse.

---

### Evitar Redes Desconocidas

No conectarse automáticamente a cualquier punto de acceso disponible.

---

### Utilizar VPN

Las VPN ayudan a proteger el tráfico incluso si se utiliza una red comprometida.

---

### Verificar HTTPS

Comprobar certificados y conexiones seguras.

---

### Utilizar MFA

Reduce el impacto del robo de credenciales.

---

### Desactivar la Conexión Automática

Evita que los dispositivos se conecten automáticamente a redes previamente conocidas.

---

## Evil Twin y la Tríada CIA

### Confidencialidad

Permite capturar información sensible.

### Integridad

Puede modificar el tráfico transmitido.

### Disponibilidad

Puede interrumpir el acceso legítimo a la red.

---

## Relación con MITM

El ataque Evil Twin suele utilizarse como mecanismo para realizar ataques MITM.

Proceso simplificado:

```text id="1f0s8l"
Evil Twin
    ↓
Víctima Conectada
    ↓
Intercepción de Tráfico
    ↓
MITM
```

Por esta razón ambos conceptos suelen estudiarse conjuntamente.

---

## Aplicaciones en Pentesting

En entornos autorizados, la simulación de ataques Evil Twin permite:

* Evaluar concienciación de usuarios.
* Analizar configuraciones Wi-Fi.
* Verificar controles de acceso.
* Medir exposición al riesgo.

---

## Conclusión

Evil Twin es un ataque que aprovecha la confianza de los usuarios en redes inalámbricas aparentemente legítimas.

Comprender su funcionamiento ayuda a identificar riesgos asociados a redes Wi-Fi y a aplicar medidas de protección adecuadas para reducir la posibilidad de compromiso.
