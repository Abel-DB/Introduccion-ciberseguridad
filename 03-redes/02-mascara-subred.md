# Máscara de Subred

## Introducción

Una **máscara de subred** es un valor utilizado junto con una dirección IP para determinar qué parte de la dirección identifica a la red y qué parte identifica al dispositivo dentro de esa red.

Las máscaras permiten organizar redes, mejorar la administración y optimizar el uso de direcciones IP.

---

## ¿Por Qué se Necesita una Máscara?

Una dirección IP por sí sola no indica dónde termina la red y dónde comienza el identificador del dispositivo.

Ejemplo:

```text
192.168.1.10
```

Para saber a qué red pertenece esta dirección es necesaria una máscara de subred.

---

## Función Principal

La máscara permite dividir una dirección IP en dos partes:

* Identificador de red (Network ID)
* Identificador de host (Host ID)

Ejemplo:

```text
IP:       192.168.1.10
Máscara:  255.255.255.0
```

Resultado:

```text
Red:   192.168.1.0
Host:  10
```

---

## Formato de una Máscara

Las máscaras IPv4 tienen el mismo formato que una dirección IP.

Ejemplos:

```text
255.0.0.0
255.255.0.0
255.255.255.0
255.255.255.192
```

---

## Máscara en Binario

Ejemplo:

```text
255.255.255.0
```

Representación binaria:

```text
11111111.11111111.11111111.00000000
```

Los bits en 1 representan la parte de red.

Los bits en 0 representan la parte de host.

---

## Ejemplo Práctico

Dirección IP:

```text
192.168.1.25
```

Máscara:

```text
255.255.255.0
```

Interpretación:

```text
Red: 192.168.1.0
Host: 25
```

Todos los dispositivos que compartan la misma red podrán comunicarse directamente.

---

## Notación CIDR

Actualmente es muy común expresar la máscara utilizando notación CIDR.

Ejemplos:

| Máscara         | CIDR |
| --------------- | ---- |
| 255.0.0.0       | /8   |
| 255.255.0.0     | /16  |
| 255.255.255.0   | /24  |
| 255.255.255.128 | /25  |
| 255.255.255.192 | /26  |

---

## Significado de /24

Ejemplo:

```text
192.168.1.10/24
```

El número:

```text
24
```

indica que los primeros 24 bits pertenecen a la red.

Equivale a:

```text
255.255.255.0
```

---

## Redes y Hosts

### Red /24

Ejemplo:

```text
192.168.1.0/24
```

Hosts disponibles:

```text
192.168.1.1
hasta
192.168.1.254
```

---

### Red /16

Ejemplo:

```text
192.168.0.0/16
```

Permite una cantidad mucho mayor de dispositivos.

---

## Dirección de Red

La dirección de red identifica a toda la red.

Ejemplo:

```text
192.168.1.0/24
```

No puede asignarse a un dispositivo.

---

## Dirección de Broadcast

Es una dirección especial utilizada para enviar información a todos los dispositivos de una red.

Ejemplo:

```text
192.168.1.255
```

Tampoco puede asignarse a un host.

---

## Ejemplo Completo

Dirección:

```text
192.168.1.100/24
```

Resultado:

| Elemento    | Valor         |
| ----------- | ------------- |
| Red         | 192.168.1.0   |
| Primer Host | 192.168.1.1   |
| Último Host | 192.168.1.254 |
| Broadcast   | 192.168.1.255 |

---

## Ventajas del Subnetting

El subnetting permite:

* Mejor organización de redes
* Menor tráfico innecesario
* Mayor control administrativo
* Mejor seguridad
* Uso más eficiente de direcciones IP

---

## Aplicaciones en Ciberseguridad

Las máscaras de subred son importantes para:

* Segmentación de redes
* Firewalls
* IDS/IPS
* Control de acceso
* Diseño de redes seguras
* Análisis de tráfico

Una correcta segmentación ayuda a limitar el movimiento lateral de un atacante dentro de una organización.

---

## Errores Comunes

### Confundir Dirección de Red con Dirección de Host

La dirección de red no puede asignarse a dispositivos.

---

### Ignorar la Dirección Broadcast

La dirección broadcast tiene un propósito especial y tampoco puede asignarse.

---

### Pensar que Todas las Redes Son /24

Existen múltiples tamaños de red según las necesidades de cada organización.

---

## Relación con el Siguiente Tema

Una vez comprendidas las direcciones IP y las máscaras de subred, es posible entender cómo los dispositivos se comunican con otras redes mediante mecanismos como NAT.

---

## Conclusión

Las máscaras de subred permiten identificar la parte de red y la parte de host de una dirección IP.

Son fundamentales para la organización, administración y seguridad de redes modernas, además de ser un concepto esencial para comprender el direccionamiento IP.
