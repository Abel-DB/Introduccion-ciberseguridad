# XOR en Criptografía

## Introducción

**XOR** significa **Exclusive OR** (O exclusivo).

Es una operación lógica fundamental en informática, programación y criptografía.

Se usa en:

- Cifrado simple
- Algoritmos modernos
- Malware
- Ingeniería inversa
- Operaciones binarias
- CTFs

---

## 1. ¿Qué hace XOR?

Compara dos bits:

- `1` si son diferentes
- `0` si son iguales

### Tabla XOR

A | B | XOR
--|---|----
0 | 0 | 0
0 | 1 | 1
1 | 0 | 1
1 | 1 | 0

### Regla rápida

Iguales = 0  
Diferentes = 1

---

## 2. ¿Por qué es importante?

Permite mezclar datos con una clave y recuperar luego el valor original usando la misma clave.

---

## 3. Ejemplo simple con bits

1010  
1100  
----  
0110

### Paso a paso

A | B | XOR
--|---|----
1 | 1 | 0
0 | 1 | 1
1 | 0 | 1
0 | 0 | 0

### Resultado final

`0110`

---

## 4. Propiedad principal

Dato XOR Clave = Cifrado

Cifrado XOR Clave = Dato original

Esto hace que XOR sea reversible.

---

## 5. Ejemplo criptográfico

Dato original:

`1011`

Clave:

`1100`

### Cifrado

1011  
1100  
----  
0111

Resultado:

`0111`

### Descifrado

0111  
1100  
----  
1011

Dato recuperado:

`1011`

---

## 6. ¿Por qué funciona?

0 XOR 0 = 0  
1 XOR 1 = 0  
X XOR 0 = X  
X XOR X = 0

Y especialmente:

`A XOR B XOR B = A`

---

## 7. XOR con texto

Letra:

`A`

ASCII:

`01000001`

Clave:

`00000001`

Aplicando XOR:

01000001  
00000001  
--------  
01000000

Resultado:

`@`

---

## 8. Uso real

XOR aparece en:

- One-Time Pad
- RC4
- Stream Ciphers
- ChaCha20
- Malware
- Ingeniería inversa

---

## 9. XOR en Malware

Muchos malware esconden texto con XOR.

Ejemplo:

`cmd.exe`

Lo almacenan cifrado y luego lo recuperan en memoria.

---

## 10. XOR en Programación

Se usa para:

- Cambiar bits
- Flags binarias
- Enmascarar valores
- Operaciones rápidas
- Retos CTF

---

## 11. Truco para Memorizar

0 XOR 0 = 0  
1 XOR 1 = 0  
0 XOR 1 = 1  
1 XOR 0 = 1

Iguales = 0  
Diferentes = 1

Lo más importante:

XOR dos veces con misma clave = original

---

## 12. Comparación rápida

Operación | Resultado
---------|----------
AND | Ambos deben ser 1
OR | Uno o ambos en 1
XOR | Solo uno en 1

---

## 13. Aplicación en Ciberseguridad

- Malware analysis
- Reverse engineering
- Criptografía moderna
- Forense digital
- CTFs

---

## 14. Errores Comunes

### Pensar que XOR solo sirve en matemáticas

Incorrecto.

### Pensar que XOR solo cifra archivos básicos

Incorrecto.

### No memorizar la tabla XOR

Error común.

---

## 15. Para Examen Memoriza

- XOR = Exclusive OR
- Iguales = 0
- Diferentes = 1
- Reversible
- Muy usado en criptografía

---

## Conclusión

XOR es una operación simple pero poderosa.

Comprender XOR ayuda enormemente en criptografía, malware y ciberseguridad.
