# Criptografía Asimétrica

## Introducción

La **criptografía asimétrica** es un método de cifrado que utiliza dos claves diferentes pero matemáticamente relacionadas:

* Clave pública
* Clave privada

Este modelo resolvió uno de los principales problemas de la criptografía simétrica: el intercambio seguro de claves.

Actualmente es una de las tecnologías fundamentales de Internet y de la seguridad moderna.

---

## ¿Cómo Funciona?

Cada usuario posee un par de claves:

### Clave Pública

Puede compartirse libremente.

Su función principal es:

* Cifrar información
* Verificar firmas digitales

### Clave Privada

Debe mantenerse secreta.

Su función principal es:

* Descifrar información
* Firmar digitalmente

---

## Proceso de Cifrado

Supongamos que Ana desea enviar un mensaje a Juan.

### Paso 1

Juan comparte su clave pública.

### Paso 2

Ana utiliza esa clave para cifrar el mensaje.

### Paso 3

Juan recibe el mensaje cifrado.

### Paso 4

Juan utiliza su clave privada para descifrarlo.

Proceso:

```text
Mensaje
    ↓
Clave Pública
    ↓
Texto Cifrado
    ↓
Clave Privada
    ↓
Mensaje Original
```

---

## Ventaja Principal

El emisor no necesita conocer la clave privada del destinatario.

Por lo tanto:

* No es necesario compartir secretos previamente.
* El intercambio inicial es más seguro.
* Se reduce el riesgo de exposición de claves.

---

## Par de Claves

Las dos claves están relacionadas matemáticamente.

Sin embargo:

* La clave pública puede conocerse.
* No debería ser posible calcular la clave privada a partir de ella.

Esta propiedad es la base de la seguridad de los algoritmos asimétricos.

---

## Ejemplo Conceptual

Imagina un buzón.

### Clave Pública

Permite introducir cartas.

Cualquiera puede usarla.

### Clave Privada

Permite abrir el buzón y leer el contenido.

Solo el propietario debe poseerla.

---

## Firma Digital

La criptografía asimétrica también permite demostrar la autenticidad de la información.

Proceso:

### Firmar

Se utiliza la clave privada.

### Verificar

Se utiliza la clave pública.

Esto permite comprobar:

* Quién envió el mensaje.
* Que no fue modificado.
* Que el autor no pueda negar su envío.

---

## Beneficios de las Firmas Digitales

### Autenticidad

Verifica la identidad del emisor.

### Integridad

Detecta modificaciones en los datos.

### No Repudio

Impide negar la autoría de una acción.

---

## Algoritmos Asimétricos Conocidos

### RSA

Uno de los algoritmos más utilizados.

Características:

* Muy popular
* Basado en matemáticas de números primos
* Utilizado en certificados y firmas digitales

---

### ECC

Elliptic Curve Cryptography.

Características:

* Claves más pequeñas
* Menor consumo de recursos
* Alta seguridad

Actualmente se utiliza ampliamente en sistemas modernos.

---

### Diffie-Hellman

Permite intercambiar claves de forma segura.

No se utiliza directamente para cifrar información.

Su función principal es establecer secretos compartidos.

---

## Criptografía Asimétrica en Internet

Está presente en:

* HTTPS
* Certificados digitales
* VPN
* SSH
* Firmas electrónicas
* Correo seguro
* Infraestructuras PKI

Prácticamente toda comunicación segura moderna depende de ella.

---

## Certificados Digitales

Un certificado digital vincula una identidad con una clave pública.

Permite verificar que un sitio web pertenece realmente a quien dice ser.

Ejemplo:

```text
Usuario
   ↓
https://banco.com
   ↓
Certificado válido
   ↓
Conexión confiable
```

---

## Relación con HTTPS

Cuando un usuario accede a una página segura:

### Fase Inicial

Se utiliza criptografía asimétrica para:

* Autenticar el servidor.
* Intercambiar claves de sesión.

### Comunicación Posterior

Se utiliza criptografía simétrica para cifrar el tráfico.

Esto combina:

* Seguridad
* Rendimiento

---

## Ventajas

### Intercambio Seguro de Claves

No requiere compartir secretos previamente.

### Soporte para Firmas Digitales

Permite verificar identidad y autenticidad.

### Escalabilidad

Más adecuada para entornos con muchos usuarios.

### Base de la Seguridad Moderna

Utilizada en la mayoría de servicios digitales.

---

## Desventajas

### Menor Velocidad

Es más lenta que la criptografía simétrica.

### Mayor Consumo de Recursos

Requiere más procesamiento.

### No Ideal para Grandes Volúmenes

Normalmente se utiliza junto con criptografía simétrica.

---

## Comparación con Criptografía Simétrica

| Característica      | Simétrica     | Asimétrica |
| ------------------- | ------------- | ---------- |
| Claves              | Una           | Dos        |
| Velocidad           | Alta          | Menor      |
| Consumo de recursos | Bajo          | Mayor      |
| Intercambio seguro  | Difícil       | Sencillo   |
| Firmas digitales    | No            | Sí         |
| Ejemplos            | AES, ChaCha20 | RSA, ECC   |

---

## Aplicaciones en Ciberseguridad

La criptografía asimétrica se utiliza en:

* HTTPS
* TLS
* SSH
* VPN
* Certificados digitales
* PKI
* Firmas electrónicas
* Gestión de identidades

---

## Errores Comunes

### Pensar que Sustituye a la Simétrica

Ambas suelen utilizarse juntas.

### Compartir la Clave Privada

La clave privada nunca debe compartirse.

### Confundir Cifrado con Firma

Cifrar protege la confidencialidad.

Firmar protege autenticidad e integridad.

---

## Conclusión

La criptografía asimétrica revolucionó la seguridad informática al permitir el intercambio seguro de información sin necesidad de compartir previamente una clave secreta.

Gracias al uso de claves públicas y privadas, hoy es posible proteger comunicaciones, verificar identidades y garantizar la autenticidad de la información en Internet.
