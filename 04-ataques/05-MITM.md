# Man in the Middle (MITM)

## Introducción

Un ataque **Man in the Middle (MITM)** ocurre cuando un atacante se sitúa entre dos partes que se comunican para interceptar, observar o incluso modificar la información intercambiada.

El objetivo principal es acceder a datos sensibles sin que las víctimas detecten la presencia del atacante.

MITM es una de las técnicas clásicas más conocidas dentro de la ciberseguridad.

---

## ¿Qué Significa MITM?

MITM significa:

```text
Man in the Middle
```

En español:

```text
Hombre en el Medio
```

El nombre describe exactamente la situación:

```text
Usuario
    ↓
Atacante
    ↓
Servidor
```

Las dos partes creen comunicarse directamente, pero en realidad el atacante se encuentra entre ellas.

---

## Funcionamiento General

En una comunicación normal:

```text
Usuario
    ↓
Servidor
```

En un ataque MITM:

```text
Usuario
    ↓
Atacante
    ↓
Servidor
```

El atacante puede:

* Observar el tráfico.
* Capturar credenciales.
* Robar información.
* Modificar datos.
* Redirigir conexiones.

---

## Objetivos de un Ataque MITM

Los atacantes suelen buscar:

* Contraseñas
* Credenciales corporativas
* Datos bancarios
* Información personal
* Cookies de sesión
* Información confidencial

---

## Ejemplo Básico

Un usuario se conecta a una red Wi-Fi pública.

El atacante intercepta el tráfico entre:

```text
Usuario ↔ Sitio Web
```

Si la comunicación no está protegida correctamente, podría capturar:

* Usuarios
* Contraseñas
* Formularios
* Datos sensibles

---

## Técnicas Comunes de MITM

### Rogue Access Point

El atacante crea un punto de acceso falso para atraer víctimas.

Ejemplo:

```text
WiFi_Gratis
```

Los usuarios se conectan creyendo que es legítimo.

---

### Evil Twin

Se crea una red Wi-Fi falsa que imita una red legítima.

Ejemplo:

```text
Universidad-WiFi
Universidad_WiFi
```

La víctima puede conectarse por error.

---

### ARP Spoofing

El atacante manipula el protocolo ARP para hacerse pasar por otro dispositivo de la red.

Objetivo:

* Interceptar tráfico local.
* Redirigir comunicaciones.

---

### DNS Spoofing

Consiste en alterar respuestas DNS.

Ejemplo:

```text
banco.com
```

es redirigido a:

```text
sitio-falso.com
```

La víctima cree estar en el sitio legítimo.

---

### Session Hijacking

El atacante roba identificadores de sesión para acceder a cuentas ya autenticadas.

No necesita conocer la contraseña si obtiene la sesión activa.

---

## MITM en Redes Wi-Fi Públicas

Las redes abiertas representan un escenario común para este tipo de ataques.

Ejemplos:

* Cafeterías
* Aeropuertos
* Hoteles
* Centros comerciales

Los usuarios suelen asumir que la red es segura cuando no siempre es así.

---

## Impacto del MITM

Un ataque exitoso puede provocar:

* Robo de credenciales
* Robo de identidad
* Fraude financiero
* Acceso no autorizado
* Exposición de datos sensibles
* Compromiso de sistemas corporativos

---

## Relación con HTTPS

HTTPS ayuda a proteger las comunicaciones mediante cifrado.

Proceso:

```text
Usuario
    ↓
HTTPS
    ↓
Servidor
```

Aunque HTTPS reduce significativamente el riesgo, configuraciones incorrectas o certificados fraudulentos pueden generar problemas.

---

## Indicadores de Posible MITM

Algunas señales incluyen:

* Advertencias de certificados.
* Redirecciones inesperadas.
* Redes Wi-Fi sospechosas.
* Comportamientos extraños en la navegación.
* Solicitudes inusuales de credenciales.

---

## Medidas de Protección

### Utilizar HTTPS

Comprobar que los sitios utilicen conexiones seguras.

---

### Verificar Certificados

No ignorar advertencias del navegador.

---

### Utilizar VPN

Las VPN cifran el tráfico y reducen el riesgo de interceptación.

---

### Evitar Redes Wi-Fi Sospechosas

Especialmente aquellas sin autenticación o de origen desconocido.

---

### Utilizar MFA

Reduce el impacto del robo de credenciales.

---

### Mantener Sistemas Actualizados

Las actualizaciones corrigen vulnerabilidades explotables.

---

## MITM y la Tríada CIA

### Confidencialidad

El atacante puede acceder a información privada.

### Integridad

Los datos pueden ser modificados durante la transmisión.

### Disponibilidad

Algunos ataques pueden interrumpir comunicaciones.

MITM puede afectar simultáneamente los tres pilares de la seguridad.

---

## Aplicaciones en Pentesting

En entornos controlados y autorizados, las técnicas MITM permiten:

* Evaluar configuraciones de red.
* Analizar riesgos.
* Verificar controles de seguridad.
* Identificar vulnerabilidades.

---

## Relación con el Siguiente Tema

Una variante muy conocida de MITM es el ataque **Evil Twin**, donde el atacante crea un punto de acceso Wi-Fi falso para engañar a las víctimas y capturar información.

---

## Conclusión

Los ataques Man in the Middle permiten interceptar y manipular comunicaciones entre usuarios y sistemas.

Comprender cómo funcionan y aplicar medidas de protección adecuadas es fundamental para reducir el riesgo de exposición de información sensible en redes modernas.
