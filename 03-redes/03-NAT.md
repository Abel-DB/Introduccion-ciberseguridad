# NAT (Network Address Translation)

## Introducción

**NAT** (Network Address Translation) es una técnica utilizada por los routers para traducir direcciones IP privadas en direcciones IP públicas y viceversa.

Su principal objetivo es permitir que múltiples dispositivos dentro de una red local compartan una única dirección IP pública para acceder a Internet.

Actualmente NAT es una tecnología fundamental en la mayoría de redes domésticas y empresariales.

---

## ¿Qué Significa NAT?

NAT significa:

```text
Network Address Translation
```

En español:

```text
Traducción de Direcciones de Red
```

Su función es modificar direcciones IP cuando los paquetes atraviesan un router.

---

## ¿Por Qué Existe NAT?

Las direcciones IPv4 son limitadas.

Si cada dispositivo conectado a Internet necesitara una dirección IP pública única, las direcciones disponibles se agotarían rápidamente.

NAT permite solucionar este problema reutilizando direcciones privadas dentro de las redes locales.

---

## Funcionamiento Básico

Supongamos la siguiente red:

```text
PC      → 192.168.1.2
Laptop  → 192.168.1.3
Móvil   → 192.168.1.4
        ↓
Router
        ↓
IP Pública: 80.25.100.44
        ↓
Internet
```

Todos los dispositivos utilizan direcciones privadas.

Cuando acceden a Internet, el router sustituye sus IP privadas por la IP pública.

---

## Ejemplo de Traducción

Antes de NAT:

```text
Origen: 192.168.1.2
Destino: google.com
```

Después de NAT:

```text
Origen: 80.25.100.44
Destino: google.com
```

Para Internet, parece que la comunicación proviene directamente del router.

---

## Tabla NAT

El router mantiene una tabla interna que registra las conexiones activas.

Ejemplo:

| IP Privada  | Puerto | IP Pública   |
| ----------- | ------ | ------------ |
| 192.168.1.2 | 54001  | 80.25.100.44 |
| 192.168.1.3 | 54002  | 80.25.100.44 |
| 192.168.1.4 | 54003  | 80.25.100.44 |

Gracias a esta tabla, el router sabe a qué dispositivo debe enviar cada respuesta.

---

## Tipos de NAT

### NAT Estático

Asocia una IP privada con una IP pública específica.

Ejemplo:

```text
192.168.1.10 ↔ 80.25.100.44
```

Se utiliza habitualmente en servidores.

---

### NAT Dinámico

Asigna direcciones públicas desde un conjunto disponible.

La asignación puede cambiar con el tiempo.

---

### PAT (Port Address Translation)

También conocido como:

```text
NAT Overload
```

Es el tipo más utilizado actualmente.

Permite que muchos dispositivos compartan una única dirección IP pública utilizando distintos puertos.

---

## Ventajas de NAT

### Ahorro de Direcciones IPv4

Reduce la necesidad de direcciones públicas.

### Facilidad de Administración

Permite conectar muchos dispositivos mediante una sola IP pública.

### Ocultación de la Red Interna

Las direcciones privadas no son visibles directamente desde Internet.

### Compatibilidad

Funciona con prácticamente cualquier red moderna.

---

## Limitaciones de NAT

### No Es un Mecanismo de Seguridad

Aunque oculta direcciones internas, NAT no sustituye a un firewall.

### Complejidad en Algunos Servicios

Puede dificultar:

* Juegos en línea
* Videollamadas
* Servidores caseros
* Aplicaciones P2P

### Problemas de Conectividad

Algunas aplicaciones requieren configuraciones adicionales.

---

## NAT y Port Forwarding

En ocasiones es necesario permitir conexiones externas hacia dispositivos internos.

Para ello se utiliza:

```text
Port Forwarding
```

Ejemplo:

```text
IP Pública
Puerto 80
      ↓
Servidor Web
192.168.1.10
```

Esto permite publicar servicios internos en Internet.

---

## NAT y Seguridad

NAT aporta cierto nivel de aislamiento porque los dispositivos internos no son accesibles directamente desde Internet.

Sin embargo:

* No inspecciona tráfico.
* No detecta malware.
* No reemplaza IDS o firewalls.
* No bloquea ataques sofisticados.

Por ello debe combinarse con otras medidas de seguridad.

---

## NAT e IPv6

Una de las ventajas de IPv6 es que proporciona una enorme cantidad de direcciones disponibles.

Gracias a ello, NAT deja de ser tan necesario como en IPv4.

Sin embargo, sigue siendo ampliamente utilizado debido a la enorme presencia de IPv4 en Internet.

---

## Aplicaciones en Ciberseguridad

NAT aparece en:

* Redes domésticas
* Redes corporativas
* Firewalls
* VPN
* Segmentación de redes
* Publicación de servicios

Comprender NAT ayuda a interpretar correctamente registros de red y configuraciones de seguridad.

---

## Errores Comunes

### Pensar que NAT es un Firewall

NAT traduce direcciones.

Un firewall filtra tráfico.

Son tecnologías diferentes.

---

### Pensar que NAT Hace una Red Inhackeable

NAT aporta aislamiento, pero no elimina riesgos.

---

### Confundir NAT con DHCP

DHCP asigna direcciones IP.

NAT traduce direcciones IP.

---

## Relación con el Siguiente Tema

Una vez comprendidas las direcciones IP, las máscaras y NAT, es posible estudiar los componentes físicos que permiten la conectividad de red.

Uno de ellos es la **NIC (Network Interface Card)**, responsable de conectar los dispositivos a la red.

---

## Conclusión

NAT es una tecnología fundamental que permite que múltiples dispositivos compartan una única dirección IP pública.

Su uso ha sido clave para prolongar la vida útil de IPv4 y continúa siendo una pieza esencial en redes modernas, tanto domésticas como empresariales.
