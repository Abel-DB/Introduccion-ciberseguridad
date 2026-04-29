# Laboratorio Linux: XOR Cifrado Real (Guía Profesional y Ordenada)

## Introducción

Este laboratorio muestra un proceso completo de **cifrado y descifrado usando XOR**, combinando herramientas básicas de Linux.

Además de ejecutar pasos, aquí se explica:

- Qué hace cada comando  
- Qué significa cada argumento  
- Para qué sirve cada símbolo  
- Cómo fluye la información  

El objetivo es comprender el proceso técnico real.

---

# Esquema General

## Proceso de Cifrado

```text
mensaje.txt + clave.txt
        ↓
 Conversión a Hexadecimal
        ↓
      XOR
        ↓
 Conversión a Binario
        ↓
      Base64
        ↓
   cifrado.txt
```

## Proceso de Descifrado

```text
cifrado.txt
     ↓
Base64 Decode
     ↓
 Binario
     ↓
Hexadecimal
     ↓
XOR con misma clave
     ↓
mensaje original
```

---

# Parte I — CIFRAR

---

## 1. Crear Archivos

```bash
nvim mensaje.txt
nvim clave.txt
```

### Explicación

| Elemento | Función |
|--------|---------|
| `nvim` | Editor de texto en terminal (Neovim) |
| `mensaje.txt` | Archivo que contiene el mensaje |
| `clave.txt` | Archivo que contiene la clave secreta |

### Ejemplo

**mensaje.txt**

```text
hola mundo
```

**clave.txt**

```text
abc1
```

---

## 2. Convertir a Hexadecimal

```bash
xxd -p mensaje.txt > mensaje.hex
xxd -p clave.txt > clave.hex
```

---

## Explicación del comando

### `xxd`

Convierte contenido entre:

- texto
- binario
- hexadecimal

### `-p`

Significa:

```text
plain mode
```

Muestra solo hexadecimal limpio.

### `>`

Redirige la salida hacia un archivo.

---

## Resultado

```text
mensaje.txt → mensaje.hex
clave.txt   → clave.hex
```

Ejemplo:

```text
hola
```

Se transforma en:

```text
686f6c61
```

---

## 3. Verificar Tamaños

```bash
wc -c mensaje.hex
wc -c clave.hex
```

---

## Explicación

### `wc`

Significa:

```text
word count
```

Cuenta información.

### `-c`

Cuenta caracteres / bytes.

---

## ¿Por qué se usa?

Porque para aplicar XOR correctamente, mensaje y clave deben tener igual longitud.

---

## 4. Ajustar Clave al Tamaño del Mensaje

```bash
yes "$(cat clave.hex)" | head -c $(wc -c < mensaje.hex) > clave-ajustada.hex
```

---

# Explicación Profesional

## `cat clave.hex`

Lee contenido del archivo.

## `$( )`

Ejecuta un comando dentro de otro.

## `yes`

Repite infinitamente el texto recibido.

Ejemplo:

```text
abcd
abcd
abcd
abcd
```

## `|`

Pipe.

Envía la salida del primer comando al siguiente.

## `head -c`

Corta una cantidad exacta de caracteres.

## `<`

Usa archivo como entrada.

---

## Resultado Final

La clave se repite automáticamente hasta tener el mismo tamaño que el mensaje.

---

## 5. Aplicar XOR

En clase se utilizó la web:

```text
xor.pw
```

Se ingresó:

- `mensaje.hex`
- `clave-ajustada.hex`

Resultado:

```text
cifrado.hex
```

---

# Qué Hace XOR

Opera bit a bit.

```text
0 XOR 0 = 0
1 XOR 0 = 1
0 XOR 1 = 1
1 XOR 1 = 0
```

---

## Ejemplo

```text
A = 01000001
B = 00110001
------------
XOR
= 01110000
```

---

## 6. Convertir Hexadecimal a Binario

```bash
xxd -r -p cifrado.hex > cifrado.bin
```

### Explicación

| Opción | Significado |
|------|-------------|
| `-r` | reverse |
| `-p` | plain mode |

Hace el proceso inverso:

```text
hexadecimal → bytes reales
```

---

## 7. Convertir Binario a Base64

```bash
base64 cifrado.bin > cifrado.txt
```

---

## Explicación

Base64 convierte datos binarios a texto legible.

Ejemplo:

```text
hola → aG9sYQ==
```

---

## ¿Por qué se usa?

Porque datos binarios no siempre pueden enviarse fácilmente.

Base64 sí.

---

# Resultado Final del Cifrado

Archivos importantes:

```text
clave.txt
cifrado.txt
```

---

# Parte II — DESCIFRAR

---

## 1. Decodificar Base64

```bash
base64 -d cifrado.txt > cifrado.bin
```

### `-d`

Significa:

```text
decode
```

---

## 2. Binario a Hexadecimal

```bash
xxd -p cifrado.bin > cifrado.hex
```

---

## 3. Clave a Hexadecimal

```bash
xxd -p clave.txt > clave.hex
```

---

## 4. Ajustar Clave Nuevamente

```bash
yes "$(cat clave.hex)" | head -c $(wc -c < cifrado.hex) > clave-ajustada.hex
```

---

## 5. Aplicar XOR Otra Vez

Usando:

```text
xor.pw
```

Entradas:

- `cifrado.hex`
- `clave-ajustada.hex`

Resultado:

```text
mensaje.hex
```

---

## 6. Recuperar Texto Original

```bash
xxd -r -p mensaje.hex > mensaje-recuperado.txt
```

Contenido:

```text
hola mundo
```

---

# Símbolos Importantes de Linux

| Símbolo | Función |
|--------|--------|
| `>` | Guarda salida |
| `|` | Conecta comandos |
| `<` | Entrada desde archivo |
| `$( )` | Ejecuta comando interno |

---

# Resumen de Comandos

| Comando | Función |
|--------|--------|
| `nvim` | Editar archivos |
| `xxd` | Convertir datos |
| `cat` | Mostrar archivo |
| `wc` | Contar bytes |
| `yes` | Repetir texto |
| `head` | Cortar cantidad |
| `base64` | Codificar / decodificar |

---

# Concepto Fundamental

## XOR es Reversible

```text
A XOR B = C
C XOR B = A
```

Por eso sirve para cifrar y descifrar con la misma clave.

---

# Diferencia Importante

## XOR

Sí transforma datos con una clave.

## Base64

No cifra.  
Solo cambia formato.

---

# Errores Comunes

## Clave Incorrecta

No recupera el mensaje.

## Tamaños Diferentes

El XOR saldrá mal.

## Confundir Base64 con Seguridad

Base64 no protege información.

## Perder la Clave

Sin la clave correcta no recuperas fácilmente el contenido.

---

# Truco Mental

## Cifrar

```text
Texto → Hex → XOR → Binario → Base64
```

## Descifrar

```text
Base64 → Binario → Hex → XOR → Texto
```

---

# Conclusión

Este laboratorio enseña fundamentos reales de ciberseguridad:

- representación de datos  
- hexadecimal  
- operaciones binarias  
- XOR  
- codificación Base64  
- automatización Linux  

No se trata solo de ejecutar comandos.

Se trata de entender cómo fluye la información y cómo se protegen datos digitalmente.
