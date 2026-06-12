# Conversión entre Sistemas Numéricos

## Introducción

En informática, un mismo valor puede representarse utilizando distintos sistemas numéricos.

Los sistemas más utilizados son:

* Decimal (base 10)
* Binario (base 2)
* Hexadecimal (base 16)

Comprender cómo convertir entre ellos es fundamental para interpretar datos utilizados en programación, redes, sistemas operativos y ciberseguridad.

---

## Binario a Decimal

### Método

Cada posición binaria representa una potencia de 2.

Ejemplo:

```text
1011₂
```

| Bit | Valor |
| --- | ----- |
| 1   | 8     |
| 0   | 0     |
| 1   | 2     |
| 1   | 1     |

Resultado:

```text
8 + 0 + 2 + 1 = 11
```

Por lo tanto:

```text
1011₂ = 11₁₀
```

---

## Decimal a Binario

### Método de Divisiones Sucesivas

Ejemplo:

```text
13₁₀
```

| División | Cociente | Resto |
| -------- | -------- | ----- |
| 13 ÷ 2   | 6        | 1     |
| 6 ÷ 2    | 3        | 0     |
| 3 ÷ 2    | 1        | 1     |
| 1 ÷ 2    | 0        | 1     |

Leyendo los restos de abajo hacia arriba:

```text
1101₂
```

Resultado:

```text
13₁₀ = 1101₂
```

---

## Decimal a Hexadecimal

### Método

Dividir sucesivamente entre 16.

Ejemplo:

```text
58₁₀
```

```text
58 ÷ 16 = 3 resto 10
```

El valor 10 en hexadecimal corresponde a:

```text
A
```

Resultado:

```text
58₁₀ = 3A₁₆
```

---

## Hexadecimal a Decimal

### Método

Cada posición representa una potencia de 16.

Ejemplo:

```text
A8₁₆
```

```text
A = 10
```

Cálculo:

```text
(10 × 16) + 8
```

Resultado:

```text
168₁₀
```

---

## Binario a Hexadecimal

### Método

Agrupar los bits de cuatro en cuatro desde la derecha.

Ejemplo:

```text
10101111₂
```

Agrupando:

```text
1010 1111
```

Conversión:

```text
1010 = A
1111 = F
```

Resultado:

```text
AF₁₆
```

---

## Hexadecimal a Binario

### Método

Cada dígito hexadecimal equivale a 4 bits.

Ejemplo:

```text
3C₁₆
```

Conversión:

```text
3 = 0011
C = 1100
```

Resultado:

```text
00111100₂
```

---

## Tabla de Referencia Rápida

| Decimal | Binario | Hexadecimal |
| ------- | ------- | ----------- |
| 0       | 0000    | 0           |
| 1       | 0001    | 1           |
| 2       | 0010    | 2           |
| 3       | 0011    | 3           |
| 4       | 0100    | 4           |
| 5       | 0101    | 5           |
| 6       | 0110    | 6           |
| 7       | 0111    | 7           |
| 8       | 1000    | 8           |
| 9       | 1001    | 9           |
| 10      | 1010    | A           |
| 11      | 1011    | B           |
| 12      | 1100    | C           |
| 13      | 1101    | D           |
| 14      | 1110    | E           |
| 15      | 1111    | F           |

---

## Aplicaciones en Ciberseguridad

Las conversiones entre sistemas numéricos aparecen en:

* Direcciones IP
* Direcciones MAC
* Análisis de tráfico de red
* Criptografía
* Programación
* Ingeniería inversa
* Análisis forense

---

## Errores Comunes

### Confundir bases numéricas

Un mismo valor puede representarse de distintas formas.

Ejemplo:

```text
10₁₀ = 1010₂ = A₁₆
```

### Olvidar agrupar de cuatro en cuatro

Es un error frecuente al convertir entre binario y hexadecimal.

### No identificar correctamente las letras hexadecimales

Recordar:

```text
A=10
B=11
C=12
D=13
E=14
F=15
```

---

## Conclusión

La conversión entre decimal, binario y hexadecimal es una habilidad básica en informática y ciberseguridad.

Dominar estas conversiones facilita la comprensión de redes, programación, criptografía y análisis de sistemas.
