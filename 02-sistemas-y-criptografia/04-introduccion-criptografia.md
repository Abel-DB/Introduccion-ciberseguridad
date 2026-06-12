# Introducción a la Criptografía

## Introducción

La **criptografía** es la disciplina encargada de proteger información mediante técnicas matemáticas que permiten ocultar, transformar o verificar datos.

Su objetivo principal es garantizar que la información solo pueda ser comprendida por personas autorizadas.

Actualmente es una pieza fundamental de la ciberseguridad y está presente en prácticamente todos los servicios digitales modernos.

---

## Origen del Término

La palabra criptografía proviene del griego:

* **Kryptos** → oculto
* **Graphia** → escritura

Su significado literal es:

```text
Escritura oculta
```

---

## ¿Para Qué Sirve la Criptografía?

La criptografía permite proteger información frente a accesos no autorizados y modificaciones indebidas.

Entre sus principales funciones se encuentran:

* Ocultar información sensible
* Proteger comunicaciones
* Verificar identidad
* Garantizar integridad de datos
* Evitar manipulaciones
* Proteger credenciales y secretos

---

## Principios Fundamentales

### Confidencialidad

Garantiza que únicamente usuarios autorizados puedan acceder a la información.

Ejemplo:

Un mensaje cifrado que solo puede leer el destinatario.

---

### Integridad

Garantiza que los datos no hayan sido modificados durante su almacenamiento o transmisión.

Ejemplo:

Verificar que un archivo descargado no fue alterado.

---

### Autenticación

Permite comprobar la identidad de usuarios, dispositivos o sistemas.

Ejemplo:

Verificar que un servidor web es legítimo.

---

### No Repudio

Impide que el emisor niegue haber enviado una determinada información.

Ejemplo:

Una firma digital utilizada en documentos electrónicos.

---

## Conceptos Básicos

### Texto Plano

Es la información original sin protección.

Ejemplo:

```text
Hola Mundo
```

---

### Cifrado

Proceso mediante el cual la información se transforma en un formato ilegible.

Ejemplo:

```text
Hola Mundo → X7A9#P2Q
```

---

### Texto Cifrado

Resultado del proceso de cifrado.

No debería ser comprensible sin la clave adecuada.

---

### Descifrado

Proceso inverso que permite recuperar la información original.

---

## Elementos de un Sistema Criptográfico

| Elemento   | Función                            |
| ---------- | ---------------------------------- |
| Mensaje    | Información original               |
| Algoritmo  | Método matemático utilizado        |
| Clave      | Valor utilizado durante el cifrado |
| Cifrado    | Transformación de datos            |
| Descifrado | Recuperación del mensaje original  |

---

## ¿Qué es una Clave?

Una **clave criptográfica** es un valor utilizado por un algoritmo para proteger información.

La seguridad del sistema depende en gran medida de la protección de esta clave.

Ejemplo:

```text
Mensaje: HOLA
Clave: 1234
```

Sin la clave correcta no debería ser posible recuperar el mensaje original.

---

## Tipos Principales de Criptografía

### Criptografía Simétrica

Utiliza la misma clave para cifrar y descifrar.

Ejemplos:

* AES
* DES
* ChaCha20

Ventaja principal:

* Muy rápida

Desventaja principal:

* Distribución segura de la clave

---

### Criptografía Asimétrica

Utiliza dos claves relacionadas matemáticamente:

* Clave pública
* Clave privada

Ejemplos:

* RSA
* ECC

Ventaja principal:

* Intercambio seguro de información

Desventaja principal:

* Mayor consumo de recursos

---

## Ejemplo Histórico: Cifrado César

Uno de los sistemas criptográficos más antiguos.

Consiste en desplazar letras del alfabeto.

Ejemplo:

```text
A → D
B → E
C → F
```

Mensaje:

```text
HOLA
```

Resultado:

```text
KROD
```

Actualmente se considera inseguro, pero es útil para comprender los conceptos básicos del cifrado.

---

## Criptografía en la Vida Cotidiana

La criptografía está presente en numerosos servicios utilizados diariamente:

* HTTPS
* Aplicaciones bancarias
* WhatsApp
* Signal
* VPN
* WiFi WPA2 y WPA3
* Correos electrónicos seguros
* Firmas digitales

---

## Importancia en Ciberseguridad

Sin criptografía:

* Las contraseñas viajarían sin protección.
* Las comunicaciones podrían ser interceptadas fácilmente.
* Los servicios bancarios serían inseguros.
* Las redes WiFi serían vulnerables.
* La privacidad digital sería prácticamente inexistente.

La criptografía constituye una de las principales herramientas de protección en el mundo digital.

---

## Errores Comunes

### Pensar que Criptografía y Contraseña Son lo Mismo

Una contraseña es solo un mecanismo de autenticación.

La criptografía es una disciplina mucho más amplia.

---

### Pensar que Base64 Es Cifrado

Incorrecto.

Base64 únicamente codifica información.

No proporciona seguridad.

---

### Pensar que el Algoritmo es Más Importante que la Clave

Un algoritmo fuerte con una clave mal protegida sigue siendo vulnerable.

La protección de la clave es fundamental.

---

## Relación con los Siguientes Temas

La criptografía moderna se divide principalmente en dos enfoques:

* Criptografía Simétrica
* Criptografía Asimétrica

Además, existen operaciones fundamentales como XOR, utilizadas en numerosos algoritmos y aplicaciones de seguridad.

Los siguientes temas profundizarán en cada uno de estos conceptos.

---

## Conclusión

La criptografía es una de las bases de la ciberseguridad moderna.

Permite proteger la confidencialidad, integridad y autenticidad de la información mediante el uso de algoritmos y claves criptográficas.

Comprender sus fundamentos es esencial para entender cómo se protegen los datos en sistemas, redes y aplicaciones actuales.
