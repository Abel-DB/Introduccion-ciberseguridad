# Sistemas Numéricos: Decimal, Binario y Hexadecimal

## Introducción

Un sistema numérico es un conjunto de símbolos y reglas utilizado para representar cantidades.

En informática, los sistemas numéricos son esenciales porque los ordenadores almacenan, procesan y transmiten información mediante valores numéricos.

Los tres sistemas más importantes en ciberseguridad e informática son:

- Decimal (base 10)
- Binario (base 2)
- Hexadecimal (base 16)

---

# 1. Sistema Decimal

## Definición

Es el sistema utilizado habitualmente por las personas.

Trabaja en **base 10**, lo que significa que usa diez símbolos:

0, 1, 2, 3, 4, 5, 6, 7, 8, 9

## Valor posicional

Cada posición representa una potencia de 10.

Ejemplo:

345₁₀ = (3 × 10²) + (4 × 10¹) + (5 × 10⁰)

= 300 + 40 + 5

= 345

---

# 2. Sistema Binario

## Definición

Es el sistema utilizado internamente por los ordenadores.

Trabaja en **base 2**, usando únicamente dos símbolos:

0 y 1

Estos valores representan estados eléctricos:

- 0 = apagado / falso / bajo voltaje
- 1 = encendido / verdadero / alto voltaje

## Valor posicional

Cada posición representa una potencia de 2.

Ejemplo:

1011₂ = (1 × 2³) + (0 × 2²) + (1 × 2¹) + (1 × 2⁰)

= 8 + 0 + 2 + 1

= 11₁₀

---

# 3. Sistema Hexadecimal

## Definición

Es un sistema compacto muy usado en informática.

Trabaja en **base 16** y utiliza:

0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F

Donde:

- A = 10
- B = 11
- C = 12
- D = 13
- E = 14
- F = 15

## Ejemplo

2F₁₆ = (2 × 16¹) + (15 × 16⁰)

= 32 + 15

= 47₁₀

---

# 4. ¿Por qué se usa hexadecimal?

El binario puede resultar muy largo.

Ejemplo:

11111111₂

En hexadecimal:

FF₁₆

Es más corto, legible y práctico.

Por eso se usa en:

- Direcciones MAC
- Colores RGB (#FF0000)
- Programación
- Memoria
- Hashes
- Forense digital

---

# 5. Relación entre Binario y Hexadecimal

Cada dígito hexadecimal equivale exactamente a **4 bits**.

| Binario | Hexadecimal |
|--------|-------------|
| 0000 | 0 |
| 0001 | 1 |
| 0010 | 2 |
| 0011 | 3 |
| 0100 | 4 |
| 0101 | 5 |
| 0110 | 6 |
| 0111 | 7 |
| 1000 | 8 |
| 1001 | 9 |
| 1010 | A |
| 1011 | B |
| 1100 | C |
| 1101 | D |
| 1110 | E |
| 1111 | F |

---

# 6. Aplicaciones en Ciberseguridad

## Direcciones IP y Redes

Representación binaria de máscaras y direcciones.

## Criptografía

Claves, hashes y datos cifrados suelen mostrarse en hexadecimal.

## Análisis Forense

Archivos binarios examinados en hex editors.

## Programación

Manipulación de bytes y memoria.

---

# 7. Ejemplos Prácticos

## Número decimal 10

10₁₀ = 1010₂ = A₁₆

## Número decimal 64

64₁₀ = 1000000₂ = 40₁₆

## Número hexadecimal FF

FF₁₆ = 255₁₀

---

# 8. Errores Comunes

## Confundir base del número

1010 puede significar:

- Decimal: mil diez
- Binario: diez decimal

Depende de la base.

## No entender valor posicional

Cada posición cambia según la base utilizada.

---

# Conclusión

Los sistemas decimal, binario y hexadecimal son fundamentales en informática.

El decimal se usa en la vida cotidiana, el binario en el funcionamiento interno de los equipos y el hexadecimal como representación compacta y técnica.

Dominar estos sistemas es esencial para redes, programación y ciberseguridad.
