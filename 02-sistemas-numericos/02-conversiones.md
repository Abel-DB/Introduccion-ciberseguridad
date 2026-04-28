# Conversión entre Sistemas Numéricos

## Introducción

Un mismo número puede representarse en distintas bases numéricas.

| Decimal | Binario | Hexadecimal |
|--------|---------|-------------|
| 10 | 1010 | A |
| 15 | 1111 | F |
| 255 | 11111111 | FF |

Estas conversiones son fundamentales en:

- Redes  
- Programación  
- Criptografía  
- Sistemas Operativos  
- Ciberseguridad  

---

# 1. Binario → Decimal

## Método

Multiplicar cada bit por su potencia de 2 correspondiente.

## Ejemplo

1011₂

| Bit | Potencia | Valor |
|----|----------|------|
| 1 | 2³ | 8 |
| 0 | 2² | 0 |
| 1 | 2¹ | 2 |
| 1 | 2⁰ | 1 |

8 + 0 + 2 + 1 = 11

### Resultado

1011₂ = 11₁₀

---

# 2. Decimal → Binario

## Método

Divisiones sucesivas entre 2.

## Ejemplo

13₁₀

| División | Cociente | Resto |
|---------|----------|------|
| 13 ÷ 2 | 6 | 1 |
| 6 ÷ 2 | 3 | 0 |
| 3 ÷ 2 | 1 | 1 |
| 1 ÷ 2 | 0 | 1 |

Leer restos de abajo hacia arriba:

1101₂

### Resultado

13₁₀ = 1101₂

---

# 3. Decimal → Hexadecimal

## Método

Divisiones sucesivas entre 16.

## Equivalencias

| Decimal | Hex |
|--------|-----|
| 10 | A |
| 11 | B |
| 12 | C |
| 13 | D |
| 14 | E |
| 15 | F |

## Ejemplo

58₁₀

| División | Cociente | Resto |
|---------|----------|------|
| 58 ÷ 16 | 3 | 10 |

10 = A

### Resultado

58₁₀ = 3A₁₆

---

# 4. Hexadecimal → Decimal

## Método

Multiplicar cada dígito por potencias de 16.

## Ejemplo

A8₁₆

| Dígito | Valor | Operación |
|------|------|-----------|
| A | 10 | 10 × 16¹ |
| 8 | 8 | 8 × 16⁰ |

160 + 8 = 168

### Resultado

A8₁₆ = 168₁₀

---

# 5. Binario → Hexadecimal

## Método

Agrupar en bloques de 4 bits.

## Ejemplo

10101111₂

1010   1111  
 A      F

### Resultado

10101111₂ = AF₁₆

---

# 6. Hexadecimal → Binario

## Método

Sustituir cada dígito por 4 bits.

## Ejemplo

3C₁₆

| Hex | Binario |
|----|---------|
| 3 | 0011 |
| C | 1100 |

### Resultado

3C₁₆ = 00111100₂

---

# Resumen General

| Conversión | Método |
|----------|--------|
| Binario → Decimal | Potencias de 2 |
| Decimal → Binario | Divisiones entre 2 |
| Decimal → Hexadecimal | Divisiones entre 16 |
| Hexadecimal → Decimal | Potencias de 16 |
| Binario → Hexadecimal | Bloques de 4 bits |
| Hexadecimal → Binario | Sustitución directa |

---

# Para Examen Memoriza

2 = Binario  
10 = Decimal  
16 = Hexadecimal  
4 bits = 1 Hex

---

# Conclusión

Dominar conversiones numéricas facilita el trabajo en redes, criptografía, análisis digital y programación.
