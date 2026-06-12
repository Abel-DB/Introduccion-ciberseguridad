# Direcciones IP

## Introducción

Una **dirección IP** es un identificador numérico asignado a un dispositivo dentro de una red.

Su función principal es permitir que los equipos puedan identificarse, comunicarse y enviar información entre sí.

Sin direcciones IP, los dispositivos no podrían localizarse ni intercambiar datos a través de una red o de Internet.

---

## ¿Qué Significa IP?

IP significa:

```text
Internet Protocol
```

Es el protocolo encargado de identificar dispositivos y enrutar información entre redes.

Cada dispositivo conectado a una red necesita una dirección IP para poder comunicarse.

---

## ¿Para Qué Sirve una Dirección IP?

Una dirección IP permite:

* Identificar dispositivos.
* Enviar información.
* Recibir información.
* Localizar equipos en una red.
* Establecer comunicaciones entre sistemas.

Ejemplo:

```text
PC → Router → Servidor Web
```

Cada uno posee una dirección IP distinta.

---

## Versiones de IP

Actualmente existen dos versiones principales:

* IPv4
* IPv6

---

## IPv4

Es la versión más utilizada actualmente.

Está formada por cuatro bloques separados por puntos.

Ejemplo:

```text
192.168.1.10
```

Formato general:

```text
X.X.X.X
```

Cada bloque puede contener valores entre:

```text
0 y 255
```

Ejemplos válidos:

```text
8.8.8.8
192.168.0.1
10.0.0.5
```

---

## ¿Por Qué el Máximo es 255?

Cada bloque de IPv4 representa 8 bits.

Ejemplo:

```text
11111111
```

En decimal:

```text
255
```

Por esta razón el rango posible de cada octeto es:

```text
0 - 255
```

---

## IPv6

IPv6 fue desarrollado para solucionar la escasez de direcciones IPv4.

Ejemplo:

```text
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Ventajas:

* Muchísima mayor cantidad de direcciones.
* Mejor escalabilidad.
* Diseño más moderno.
* Mejor soporte para redes futuras.

---

## IP Pública e IP Privada

### IP Pública

Es la dirección visible en Internet.

Generalmente es asignada por el proveedor de Internet.

Ejemplo:

```text
80.25.100.44
```

---

### IP Privada

Se utiliza dentro de redes internas.

Ejemplos:

```text
192.168.x.x
10.x.x.x
172.16.x.x - 172.31.x.x
```

Estas direcciones no son accesibles directamente desde Internet.

---

## Ejemplo de Red Doméstica

```text
Internet
     ↓
IP Pública del Router
     ↓
Router WiFi
     ↓
PC      → 192.168.1.2
Móvil   → 192.168.1.3
TV      → 192.168.1.4
```

Todos los dispositivos utilizan direcciones privadas dentro de la red local.

---

## IP Estática e IP Dinámica

### IP Estática

Permanece siempre igual.

Se utiliza frecuentemente en:

* Servidores
* Cámaras IP
* Impresoras
* Equipos críticos

---

### IP Dinámica

Puede cambiar automáticamente.

Es la opción más habitual en hogares y pequeñas empresas.

---

## DHCP

DHCP significa:

```text
Dynamic Host Configuration Protocol
```

Su función es asignar automáticamente:

* Dirección IP
* Máscara de red
* Puerta de enlace (Gateway)
* DNS

Ejemplo:

Cuando conectas tu teléfono al WiFi, normalmente recibe una IP mediante DHCP.

---

## DNS e IP

Las personas utilizan nombres fáciles de recordar:

```text
google.com
```

Los equipos utilizan direcciones IP.

El sistema DNS traduce nombres a direcciones IP.

Ejemplo:

```text
google.com
↓
142.250.x.x
```

---

## Dirección Loopback

Existe una dirección especial utilizada por el propio sistema.

```text
127.0.0.1
```

También se conoce como:

```text
localhost
```

Permite que un equipo se comunique consigo mismo.

Es muy utilizada para pruebas y desarrollo.

---

## Rangos Privados Más Importantes

| Rango          | Uso Habitual           |
| -------------- | ---------------------- |
| 10.0.0.0/8     | Grandes organizaciones |
| 172.16.0.0/12  | Redes empresariales    |
| 192.168.0.0/16 | Redes domésticas       |

---

## Aplicaciones en Ciberseguridad

Las direcciones IP son fundamentales para:

* Firewalls
* IDS e IPS
* Logs
* Análisis forense
* Escaneo de redes
* SIEM
* VPN
* Investigación de incidentes

Muchos ataques y actividades sospechosas se identifican mediante direcciones IP.

---

## Errores Comunes

### Confundir IP Pública con Privada

Es uno de los errores más frecuentes.

---

### Pensar que una IP Identifica Siempre a una Persona

Una dirección IP identifica una conexión o dispositivo, no necesariamente a una persona concreta.

---

### Pensar que una IP Nunca Cambia

Muchas direcciones IP son dinámicas y cambian periódicamente.

---

## Relación con el Siguiente Tema

Una dirección IP por sí sola no es suficiente para determinar qué dispositivos pertenecen a una misma red.

Para ello se utilizan las **máscaras de subred**, que permiten dividir y organizar redes de forma eficiente.

---

## Conclusión

Las direcciones IP son la base de la comunicación en redes e Internet.

Comprender su funcionamiento permite entender cómo se identifican los dispositivos, cómo circula la información y cómo se realizan tareas fundamentales de administración y ciberseguridad.
