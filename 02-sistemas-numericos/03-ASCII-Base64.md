# ASCII y Base64

## Introducción

En informática, los datos no se almacenan como letras o símbolos directamente.  
Los ordenadores trabajan con **números binarios**, por lo que los caracteres deben convertirse a valores numéricos.

Dos conceptos fundamentales para entender esto son:

- **ASCII** → sistema de codificación de caracteres.  
- **Base64** → sistema de codificación binario a texto.

Ambos son muy importantes en programación, redes y ciberseguridad.

---

# 1. ¿Qué es ASCII?

## Definición

**ASCII** significa:

`American Standard Code for Information Interchange`

Es un estándar que asigna un número a cada letra, símbolo o carácter.

Ejemplo:

| Carácter | Decimal | Binario | Hexadecimal |
|---------|---------|---------|-------------|
| A | 65 | 01000001 | 41 |
| B | 66 | 01000010 | 42 |
| a | 97 | 01100001 | 61 |
| 0 | 48 | 00110000 | 30 |
| Espacio | 32 | 00100000 | 20 |

---

# 2. ¿Por qué existe ASCII?

Porque los ordenadores necesitan una forma universal de representar texto.

Cuando escribes:

`Hola`

El sistema realmente guarda números.

Ejemplo:

| Letra | ASCII |
|------|------|
| H | 72 |
| o | 111 |
| l | 108 |
| a | 97 |

---

# 3. Cómo pensar ASCII

No memorices toda la tabla. Memoriza patrones.

## Letras mayúsculas

`A = 65`

Desde ahí siguen en orden:

`A=65, B=66, C=67 ... Z=90`

## Letras minúsculas

`a = 97`

`a=97, b=98, c=99 ... z=122`

## Números

`0=48, 1=49, 2=50 ... 9=57`

---

# 4. Truco rápido ASCII

## Diferencia entre mayúscula y minúscula

`a = 97`

`A = 65`

Diferencia:

`32`

Esto pasa con todas las letras.

Ejemplo:

`b = 98`

`B = 66`

También diferencia `32`.

## ¿Por qué sirve?

En programación y scripting permite convertir letras fácilmente.

---

# 5. ASCII en Ciberseguridad

ASCII aparece en:

- Contraseñas
- Logs
- Scripts
- Análisis forense
- Payloads
- Datos en red
- Terminal Linux

Ejemplo:

`Admin123`

Internamente son bytes ASCII.

---

# 6. Limitación de ASCII

ASCII clásico usa 7 bits:

`0 a 127`

Por eso no incluye muchos caracteres modernos como:

- ñ
- á
- €
- caracteres chinos
- emojis

Para eso existe **Unicode / UTF-8**.

---

# 7. ¿Qué es Base64?

## Definición

Base64 es un sistema que convierte datos binarios en texto usando 64 símbolos.

Se usan:

`A-Z`

`a-z`

`0-9`

`+`

`/`

Y a veces:

`=`

como relleno.

---

# 8. ¿Para qué sirve Base64?

Se usa cuando un sistema solo acepta texto pero queremos enviar datos binarios.

Ejemplos reales:

- Correos electrónicos (adjuntos MIME)
- APIs
- JSON Web Tokens (JWT)
- Cookies
- Imágenes embebidas en HTML/CSS
- Archivos transmitidos por texto

---

# 9. Importante: Base64 NO cifra

Muchos lo confunden.

## Base64 NO es seguridad

No protege datos.  
Solo cambia formato.

Ejemplo:

`Hola`

En Base64:

`SG9sYQ==`

Pero cualquiera puede decodificarlo.

---

# 10. Cómo funciona Base64 (idea simple)

1. Texto original → bytes ASCII  
2. Bytes → binario  
3. Se agrupan bits  
4. Se convierten en símbolos Base64

---

# 11. Ejemplo práctico

Texto:

`A`

ASCII:

`65`

Binario:

`01000001`

Codificado Base64:

`QQ==`

---

# 12. Truco rápido Base64

Si termina en:

`=`

o

`==`

Es muy probable que sea Base64.

Ejemplo:

`dXNlcg==`

Decodificado:

`user`

---

# 13. ASCII vs Base64

| Concepto | ASCII | Base64 |
|---------|------|--------|
| ¿Qué hace? | Representa caracteres | Convierte binario a texto |
| Uso | Letras y símbolos | Transporte de datos |
| Seguridad | No | No |
| Ejemplo | A = 65 | Hola = SG9sYQ== |

---

# 14. Aplicación en Ciberseguridad

## ASCII

- Contraseñas
- Comandos
- Scripts
- Payloads

## Base64

- Malware ofuscado
- Tokens web
- Datos ocultos en tráfico
- Archivos codificados
- Logs sospechosos

---

# 15. Errores comunes

## ASCII

Pensar que guarda letras directamente.

## Base64

Pensar que cifra.

## Ambos

Confundir codificación con criptografía.

---

# Para Memorizar

`A = 65`

`a = 97`

`0 = 48`

`Base64 NO cifra`

`ASCII = caracteres`

`Base64 = transporte`

---

# Conclusión

ASCII permite representar texto mediante números.  
Base64 permite representar datos binarios como texto.

Ambos conceptos son esenciales para comprender cómo viaja y se almacena la información en sistemas informáticos y entornos de ciberseguridad.
