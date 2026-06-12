# Criptografía Simétrica

## Introducción

La **criptografía simétrica** es un método de cifrado en el que se utiliza la misma clave tanto para cifrar como para descifrar la información.

Es uno de los métodos criptográficos más antiguos y continúa siendo ampliamente utilizado debido a su rapidez y eficiencia.

---

## ¿Cómo Funciona?

El emisor y el receptor comparten una clave secreta.

Proceso:

```text
Mensaje Original
       ↓
Cifrado con Clave
       ↓
Texto Cifrado
       ↓
Descifrado con la Misma Clave
       ↓
Mensaje Original
```

Ambas partes deben conocer y proteger la misma clave.

---

## Ejemplo Conceptual

Supongamos el mensaje:

```text
HOLA
```

Y una clave secreta:

```text
1234
```

El algoritmo utiliza esa clave para transformar el mensaje en un formato ilegible.

Resultado:

```text
X7A9#P2Q
```

Quien posea la misma clave podrá recuperar el mensaje original.

---

## Características Principales

### Misma Clave

La misma clave se utiliza para:

* Cifrar
* Descifrar

---

### Alta Velocidad

Es considerablemente más rápida que la criptografía asimétrica.

Por esta razón suele utilizarse para proteger grandes volúmenes de datos.

---

### Menor Consumo de Recursos

Requiere menos procesamiento y memoria.

---

### Dependencia de la Clave

Toda la seguridad depende de mantener la clave protegida.

Si un atacante obtiene la clave, podrá acceder a la información.

---

## Ventajas

### Rapidez

Permite cifrar grandes cantidades de datos rápidamente.

### Eficiencia

Consume pocos recursos del sistema.

### Fácil Implementación

Muchos sistemas modernos la utilizan como mecanismo principal de cifrado.

### Uso Masivo

Está presente en:

* WiFi
* VPN
* Discos cifrados
* Bases de datos
* Sistemas operativos

---

## Desventajas

### Distribución de Claves

El principal problema es compartir la clave de forma segura.

Si la clave es interceptada durante el intercambio, la confidencialidad se pierde.

### Escalabilidad

A medida que aumenta el número de usuarios, aumenta también la cantidad de claves necesarias.

### Riesgo de Compromiso

Una única clave comprometida puede exponer toda la información protegida.

---

## Algoritmos Simétricos Conocidos

### DES

Data Encryption Standard.

Características:

* Antiguo
* Actualmente inseguro
* Claves pequeñas

Hoy se utiliza principalmente con fines educativos.

---

### 3DES

Triple DES.

Mejoró la seguridad de DES aplicando el algoritmo varias veces.

Actualmente también se considera obsoleto frente a alternativas modernas.

---

### AES

Advanced Encryption Standard.

Es el estándar de cifrado simétrico más utilizado actualmente.

Características:

* Seguro
* Rápido
* Eficiente
* Amplio soporte

Tamaños de clave comunes:

* 128 bits
* 192 bits
* 256 bits

---

### ChaCha20

Algoritmo moderno diseñado para ofrecer alto rendimiento y seguridad.

Se utiliza en diversos protocolos actuales.

---

## Uso en la Vida Real

### HTTPS

Las conexiones seguras utilizan cifrado simétrico para proteger la comunicación una vez establecida la sesión.

### WiFi

WPA2 y WPA3 utilizan mecanismos basados en criptografía simétrica.

### VPN

Protegen el tráfico mediante algoritmos simétricos.

### Cifrado de Discos

Herramientas como BitLocker o LUKS utilizan cifrado simétrico para proteger datos almacenados.

---

## Relación con la Criptografía Asimétrica

En muchos sistemas modernos se utilizan ambos enfoques.

Proceso habitual:

1. La criptografía asimétrica intercambia una clave segura.
2. La criptografía simétrica cifra toda la comunicación posterior.

Esto permite combinar seguridad y rendimiento.

---

## Ejemplo Práctico

Dos usuarios desean intercambiar información.

### Problema

Necesitan compartir una clave secreta.

### Solución

Utilizan criptografía asimétrica para intercambiar la clave.

Posteriormente utilizan AES para cifrar toda la comunicación.

Este enfoque es utilizado por protocolos como TLS.

---

## Aplicaciones en Ciberseguridad

La criptografía simétrica aparece en:

* HTTPS
* VPN
* WiFi
* Almacenamiento cifrado
* Bases de datos
* Sistemas operativos
* Protección de archivos

---

## Errores Comunes

### Compartir la Clave por Canales Inseguros

La seguridad depende de la protección de la clave.

### Utilizar Algoritmos Obsoletos

DES y otros algoritmos antiguos ya no ofrecen protección adecuada.

### Pensar que AES es Inquebrantable

La seguridad también depende de:

* La gestión de claves
* La configuración
* La implementación

---

## Comparación Rápida

| Característica      | Criptografía Simétrica |
| ------------------- | ---------------------- |
| Número de claves    | Una                    |
| Velocidad           | Muy alta               |
| Consumo de recursos | Bajo                   |
| Escalabilidad       | Limitada               |
| Uso principal       | Cifrado de datos       |
| Ejemplo             | AES                    |

---

## Conclusión

La criptografía simétrica es uno de los mecanismos más importantes para proteger información digital.

Su principal ventaja es la velocidad, lo que la convierte en la opción ideal para cifrar grandes cantidades de datos. Sin embargo, la gestión segura de las claves sigue siendo su principal desafío.
