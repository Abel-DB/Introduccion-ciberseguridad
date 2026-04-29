# Introducción a la Criptografía

## Introducción

La **criptografía** es la disciplina encargada de proteger información mediante técnicas matemáticas que permiten ocultar, transformar o verificar datos.

Su objetivo principal es garantizar que la información solo pueda ser entendida por personas autorizadas.

Actualmente es una parte esencial de:

- Ciberseguridad
- Internet
- Banca digital
- Redes privadas
- Comercio electrónico
- Aplicaciones móviles
- Sistemas militares
- Mensajería segura

---

# 1. ¿Qué significa criptografía?

La palabra proviene del griego:

- **Kryptos** = oculto  
- **Graphia** = escritura

Literalmente:

`escritura oculta`

---

# 2. ¿Para qué sirve la criptografía?

La criptografía protege datos frente a accesos no autorizados y ataques.

Permite:

- Ocultar información sensible
- Proteger contraseñas
- Verificar identidad
- Garantizar integridad
- Asegurar comunicaciones
- Evitar manipulación de datos

---

# 3. Principios Fundamentales

## Confidencialidad

Solo personas autorizadas pueden leer la información.

Ejemplo:

Un mensaje cifrado que solo el receptor puede abrir.

## Integridad

Garantiza que la información no fue modificada.

Ejemplo:

Un archivo descargado sin cambios.

## Autenticación

Permite verificar identidad del emisor.

Ejemplo:

Confirmar que un servidor web es real.

## No repudio

El emisor no puede negar que envió el mensaje.

Ejemplo:

Firma digital legal.

---

# 4. Conceptos Básicos

## Texto plano

Información original sin proteger.

Ejemplo:

`Hola mundo`

## Cifrado

Proceso de transformar texto legible en texto ilegible.

Ejemplo:

`Hola` → `X7Q#91`

## Texto cifrado

Resultado del cifrado.

## Descifrado

Proceso inverso para recuperar mensaje original.

---

# 5. Elementos de un Sistema Criptográfico

| Elemento | Función |
|---------|--------|
| Mensaje | Información original |
| Algoritmo | Método matemático |
| Clave | Valor secreto usado en cifrado |
| Cifrado | Transformación del mensaje |
| Descifrado | Recuperación del mensaje |

---

# 6. ¿Qué es una clave?

La **clave** es el valor que controla el algoritmo criptográfico.

Sin la clave correcta no debería poder recuperarse la información.

Ejemplo:

Mensaje: `HOLA`  
Clave: `1234`

---

# 7. Tipos Principales de Criptografía

## Criptografía Simétrica

Usa la misma clave para cifrar y descifrar.

Ejemplo:

- AES
- DES (antiguo)

## Criptografía Asimétrica

Usa dos claves:

- Pública
- Privada

Ejemplo:

- RSA
- ECC

---

# 8. Ejemplo sencillo

## Cifrado César

Desplaza letras del alfabeto.

A → D  
B → E  
C → F

Mensaje:

`HOLA`

Resultado:

`KROD`

Es simple y educativo, pero inseguro hoy.

---

# 9. Criptografía en la Vida Real

La usamos todos los días sin notarlo:

- HTTPS en páginas web
- WhatsApp / Signal
- Tarjetas bancarias
- VPN
- WiFi WPA2/WPA3
- Tokens de acceso
- Firmas digitales

---

# 10. ¿Por qué es importante en Ciberseguridad?

Sin criptografía:

- Contraseñas viajarían visibles
- Bancos serían inseguros
- Emails serían fáciles de leer
- WiFi sería vulnerable
- Datos empresariales quedarían expuestos

---

# 11. Errores Comunes

## Pensar que criptografía = contraseña

No. Una contraseña es solo una credencial.

## Pensar que Base64 cifra

No. Base64 solo codifica.

## Pensar que algoritmo secreto basta

Lo importante es proteger la clave.

---

# 12. Truco para Recordar

Texto plano → Cifrado → Texto cifrado  
Texto cifrado → Descifrado → Texto plano

Y:

Seguridad real = Algoritmo fuerte + Clave segura

---

# 13. Aplicación en Ingeniería

Todo profesional informático necesita entender criptografía para:

- Desarrollar software seguro
- Proteger bases de datos
- Implementar autenticación
- Diseñar APIs seguras
- Auditar sistemas

---

# Conclusión

La criptografía es uno de los pilares de la seguridad digital moderna. Permite proteger información, verificar identidades y asegurar comunicaciones.

Sin criptografía no existiría internet seguro tal como lo conocemos hoy.
