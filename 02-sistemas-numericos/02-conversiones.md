# Conversión entre Sistemas Numéricos

## Introducción

En informática, un mismo valor puede representarse utilizando distintos sistemas numéricos. Los más importantes son:

- **Decimal (base 10)** → sistema usado habitualmente por las personas.  
- **Binario (base 2)** → sistema usado por los ordenadores.  
- **Hexadecimal (base 16)** → representación compacta muy usada en informática.

Ejemplo de equivalencia:

| Decimal | Binario | Hexadecimal |
|--------|---------|-------------|
| 10 | 1010 | A |
| 15 | 1111 | F |
| 255 | 11111111 | FF |

Comprender estas conversiones es fundamental para redes, programación, criptografía y ciberseguridad.

---

# 1. Binario → Decimal

## ¿Qué estamos haciendo?

Convertimos un número escrito en base 2 al sistema decimal (base 10).

Ejemplo:

`1011₂`

## ¿Por qué usamos potencias de 2?

Porque cada posición binaria representa una potencia de 2.

| Posición | Valor |
|---------|------|
| 2⁰ | 1 |
| 2¹ | 2 |
| 2² | 4 |
| 2³ | 8 |
| 2⁴ | 16 |
| 2⁵ | 32 |
| 2⁶ | 64 |
| 2⁷ | 128 |

## Ejemplo resuelto

`1011₂`

| Bit | Valor |
|----|------|
| 1 | 8 |
| 0 | 0 |
| 1 | 2 |
| 1 | 1 |

Suma:

`8 + 0 + 2 + 1 = 11`

### Resultado final

`1011₂ = 11₁₀`

## Truco rápido

Escribe mentalmente:

`16   8   4   2   1`

Si el número es:

`1    1   0   0   1`

Solo sumas donde haya **1**:

`16 + 8 + 1 = 25`

Resultado:

`11001₂ = 25₁₀`

## ¿Por qué funciona?

Cada bit en **1** activa ese valor.  
Cada bit en **0** lo ignora.

## Error común

No empezar desde la derecha.

---

# 2. Decimal → Binario

## ¿Qué estamos haciendo?

Pasamos decimal a binario.

Ejemplo:

`13₁₀`

## Método clásico

| División | Cociente | Resto |
|---------|----------|------|
| 13 ÷ 2 | 6 | 1 |
| 6 ÷ 2 | 3 | 0 |
| 3 ÷ 2 | 1 | 1 |
| 1 ÷ 2 | 0 | 1 |

Leer restos de abajo arriba:

`1101₂`

### Resultado final

`13₁₀ = 1101₂`

## Truco rápido

Buscar potencias de 2:

`25₁₀`

`16 cabe → 1`

Queda `9`

`8 cabe → 1`

Queda `1`

`4 no cabe → 0`

`2 no cabe → 0`

`1 sí cabe → 1`

Resultado:

`11001₂`

## ¿Por qué funciona?

Todo número decimal puede escribirse como suma de potencias de 2.

`25 = 16 + 8 + 1`

---

# 3. Decimal → Hexadecimal

## Método

Dividir entre 16.

## Tabla rápida

| Decimal | Hex |
|--------|-----|
| 10 | A |
| 11 | B |
| 12 | C |
| 13 | D |
| 14 | E |
| 15 | F |

## Ejemplo

`58₁₀`

`58 ÷ 16 = 3 resto 10`

`10 = A`

Resultado:

`3A₁₆`

---

# 4. Hexadecimal → Decimal

## Método

Potencias de 16.

Ejemplo:

`A8₁₆`

`A = 10`

`(10 × 16) + 8 = 168`

Resultado:

`A8₁₆ = 168₁₀`

---

# 5. Binario → Hexadecimal

## Método

Agrupar de 4 en 4.

Ejemplo:

`10101111₂`

`1010   1111`

`A      F`

Resultado:

`AF₁₆`

---

# 6. Hexadecimal → Binario

## Método

Cada dígito = 4 bits.

Ejemplo:

`3C₁₆`

`3 = 0011`

`C = 1100`

Resultado:

`00111100₂`

---

# Resumen General

| Conversión | Método |
|----------|--------|
| Binario → Decimal | Potencias de 2 |
| Decimal → Binario | Divisiones entre 2 |
| Decimal → Hexadecimal | Divisiones entre 16 |
| Hexadecimal → Decimal | Potencias de 16 |
| Binario → Hexadecimal | Grupos de 4 bits |
| Hexadecimal → Binario | Sustitución directa |

---

# Para Memorizar

- Base 2 = Binario  
- Base 10 = Decimal  
- Base 16 = Hexadecimal  
- 1 Hex = 4 bits

---

# Conclusión

Dominar conversiones es esencial para informática, redes y ciberseguridad.
