# Sistemas Numéricos: Decimal, Binario y Hexadecimal

## Introducción

Un sistema numérico es un conjunto de símbolos y reglas utilizado para representar cantidades.

En informática, los sistemas numéricos son esenciales porque los ordenadores almacenan, procesan y transmiten información mediante valores numéricos.

Los tres sistemas más importantes en informática y ciberseguridad son:

* Decimal (base 10)
* Binario (base 2)
* Hexadecimal (base 16)

Comprender estos sistemas permite interpretar cómo los equipos representan datos, direcciones de red, caracteres y valores utilizados en criptografía.

---

## Sistema Decimal

### Definición

Es el sistema utilizado habitualmente por las personas.

Trabaja en base 10, utilizando diez símbolos:

```text
0 1 2 3 4 5 6 7 8 9
```

### Valor Posicional

Cada posición representa una potencia de 10.

Ejemplo:

```text
345₁₀ = (3 × 10²) + (4 × 10¹) + (5 × 10⁰)
```

Resultado:

```text
345₁₀ = 300 + 40 + 5
```

---

## Sistema Binario

### Definición

Es el sistema utilizado internamente por los ordenadores.

Trabaja en base 2 y utiliza únicamente dos símbolos:

```text
0 y 1
```

Estos valores representan estados eléctricos:

* 0 → apagado
* 1 → encendido

### Valor Posicional

Cada posición representa una potencia de 2.

Ejemplo:

```text
1011₂ = (1 × 2³) + (0 × 2²) + (1 × 2¹) + (1 × 2⁰)
```

Resultado:

```text
1011₂ = 8 + 0 + 2 + 1 = 11₁₀
```

---

## Sistema Hexadecimal

### Definición

Es un sistema numérico de base 16 ampliamente utilizado en informática.

Utiliza:

```text
0 1 2 3 4 5 6 7 8 9 A B C D E F
```

Donde:

```text
A = 10
B = 11
C = 12
D = 13
E = 14
F = 15
```

### Ejemplo

```text
2F₁₆ = (2 × 16¹) + (15 × 16⁰)
```

Resultado:

```text
2F₁₆ = 32 + 15 = 47₁₀
```

---

## Relación entre Binario y Hexadecimal

Cada dígito hexadecimal equivale exactamente a 4 bits.

| Binario | Hexadecimal |
| ------- | ----------- |
| 0000    | 0           |
| 0001    | 1           |
| 0010    | 2           |
| 0011    | 3           |
| 0100    | 4           |
| 0101    | 5           |
| 0110    | 6           |
| 0111    | 7           |
| 1000    | 8           |
| 1001    | 9           |
| 1010    | A           |
| 1011    | B           |
| 1100    | C           |
| 1101    | D           |
| 1110    | E           |
| 1111    | F           |

---

## Aplicaciones en Ciberseguridad

### Redes

* Direcciones IP
* Máscaras de subred
* Direcciones MAC

### Criptografía

* Claves
* Hashes
* Datos cifrados

### Análisis Forense

* Hex Editors
* Análisis de archivos binarios

### Programación

* Manipulación de memoria
* Representación de bytes

---

## Ejemplos Prácticos

| Decimal | Binario  | Hexadecimal |
| ------- | -------- | ----------- |
| 10      | 1010     | A           |
| 15      | 1111     | F           |
| 64      | 1000000  | 40          |
| 255     | 11111111 | FF          |

---

## Relación con el Siguiente Tema

Comprender estos sistemas numéricos es necesario para realizar conversiones entre bases, interpretar caracteres ASCII y entender cómo se representan los datos en informática.

El siguiente tema estudia precisamente cómo convertir valores entre decimal, binario y hexadecimal.

---

## Conclusión

Los sistemas decimal, binario y hexadecimal constituyen la base de la representación de datos en informática.

Comprender su funcionamiento permite interpretar correctamente información utilizada en redes, programación, sistemas operativos y ciberseguridad.
