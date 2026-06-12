# ASCII y Base64

## Introducción

Los ordenadores no almacenan letras, símbolos o palabras directamente. Toda la información se representa mediante números y datos binarios.

Dos conceptos fundamentales para comprender esta representación son:

* ASCII
* Base64

Ambos son ampliamente utilizados en programación, redes, sistemas operativos y ciberseguridad.

---

## ¿Qué es ASCII?

### Definición

**ASCII** significa:

```text
American Standard Code for Information Interchange
```

Es un estándar que asigna un valor numérico a cada carácter.

Gracias a ASCII, los ordenadores pueden representar letras, números y símbolos utilizando valores binarios.

---

## Ejemplos de ASCII

| Carácter | Decimal | Binario  | Hexadecimal |
| -------- | ------- | -------- | ----------- |
| A        | 65      | 01000001 | 41          |
| B        | 66      | 01000010 | 42          |
| a        | 97      | 01100001 | 61          |
| 0        | 48      | 00110000 | 30          |
| Espacio  | 32      | 00100000 | 20          |

---

## ¿Por Qué Existe ASCII?

Los sistemas informáticos necesitan una forma estandarizada para representar texto.

Cuando escribimos:

```text
Hola
```

El sistema almacena internamente:

| Letra | ASCII |
| ----- | ----- |
| H     | 72    |
| o     | 111   |
| l     | 108   |
| a     | 97    |

---

## Patrones Útiles de ASCII

### Letras Mayúsculas

```text
A = 65
```

A partir de ahí continúan en orden:

```text
B = 66
C = 67
...
Z = 90
```

---

### Letras Minúsculas

```text
a = 97
```

A partir de ahí continúan en orden:

```text
b = 98
c = 99
...
z = 122
```

---

### Números

```text
0 = 48
1 = 49
2 = 50
...
9 = 57
```

---

## Diferencia entre Mayúsculas y Minúsculas

Una característica interesante de ASCII es que existe una diferencia constante entre letras mayúsculas y minúsculas.

Ejemplo:

```text
A = 65
a = 97
```

Diferencia:

```text
32
```

Esta propiedad se utiliza frecuentemente en programación.

---

## ASCII en Ciberseguridad

ASCII aparece constantemente en:

* Contraseñas
* Scripts
* Logs
* Terminales Linux
* Análisis forense
* Tráfico de red
* Payloads

Comprender ASCII facilita interpretar información almacenada o transmitida por los sistemas.

---

## Limitaciones de ASCII

ASCII clásico utiliza únicamente 7 bits.

Por ello solo puede representar valores entre:

```text
0 y 127
```

No incluye muchos caracteres modernos como:

* ñ
* á
* €
* Caracteres chinos
* Emojis

Para solucionar estas limitaciones surgieron estándares como Unicode y UTF-8.

---

## ¿Qué es Base64?

### Definición

Base64 es un sistema de codificación que convierte datos binarios en texto.

Utiliza 64 símbolos:

```text
A-Z
a-z
0-9
+
/
```

Y el carácter:

```text
=
```

como relleno cuando es necesario.

---

## ¿Para Qué Sirve Base64?

Se utiliza cuando un sistema solo admite texto pero es necesario transmitir datos binarios.

Ejemplos comunes:

* Correos electrónicos
* APIs
* JSON Web Tokens (JWT)
* Cookies
* Imágenes embebidas
* Archivos codificados

---

## Base64 No Es Cifrado

Uno de los errores más comunes es pensar que Base64 protege información.

Base64:

* No cifra
* No protege
* No oculta realmente los datos

Simplemente cambia su representación.

Ejemplo:

```text
Hola
```

Codificado:

```text
SG9sYQ==
```

Cualquier persona puede decodificarlo fácilmente.

---

## Ejemplo de Conversión

Texto:

```text
A
```

ASCII:

```text
65
```

Binario:

```text
01000001
```

Base64:

```text
QQ==
```

---

## Cómo Identificar Base64

Muchos datos codificados en Base64 terminan con:

```text
=
```

o

```text
==
```

Ejemplo:

```text
dXNlcg==
```

Decodificado:

```text
user
```

Aunque no siempre termina de esa forma, suele ser una señal útil.

---

## ASCII vs Base64

| Característica | ASCII                  | Base64                    |
| -------------- | ---------------------- | ------------------------- |
| Función        | Representar caracteres | Convertir binario a texto |
| Uso            | Texto                  | Transporte de datos       |
| Seguridad      | No                     | No                        |
| Ejemplo        | A = 65                 | Hola = SG9sYQ==           |

---

## Aplicaciones en Ciberseguridad

### ASCII

* Contraseñas
* Scripts
* Comandos
* Logs
* Terminales

### Base64

* Malware ofuscado
* Tokens web
* Tráfico codificado
* Archivos transmitidos por texto
* Datos embebidos en aplicaciones

---

## Errores Comunes

### Pensar que Base64 es Criptografía

Incorrecto.

Base64 solo codifica datos.

---

### Confundir ASCII con Unicode

ASCII es un subconjunto mucho más pequeño.

Unicode permite representar miles de caracteres modernos.

---

### Pensar que ASCII Almacena Texto Directamente

ASCII almacena valores numéricos asociados a caracteres.

---

## Relación con el Siguiente Tema

Comprender ASCII y Base64 facilita el estudio de la criptografía, ya que muchos algoritmos trabajan directamente con datos binarios, caracteres codificados y representaciones numéricas.

---

## Conclusión

ASCII y Base64 son mecanismos fundamentales para representar y transmitir información en sistemas informáticos.

Comprender cómo funcionan permite interpretar correctamente datos utilizados en programación, redes, análisis forense y ciberseguridad.
