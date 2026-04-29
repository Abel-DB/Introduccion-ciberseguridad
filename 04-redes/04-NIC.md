# NIC (Network Interface Card)

## Introducción

**NIC** significa:

`Network Interface Card`

En español:

**Tarjeta de Interfaz de Red**

Es el componente de hardware que permite que un dispositivo se conecte a una red.

Sin una NIC, un equipo no podría comunicarse con otros dispositivos ni acceder a Internet.

---

## 1. ¿Para qué sirve una NIC?

La NIC permite:

- Enviar datos a la red
- Recibir datos desde la red
- Identificar físicamente al dispositivo
- Conectarse por cable o inalámbricamente
- Comunicarse con routers, switches y otros equipos

Es la puerta de entrada y salida de la red.

---

## 2. ¿Dónde se encuentra?

Puede estar:

### Integrada en la placa base

Muy común en PCs y portátiles modernos.

### Tarjeta adicional

Instalada en ranura PCIe.

### Adaptador USB

Muy usado para WiFi o Ethernet extra.

---

## 3. Tipos de NIC

### NIC Ethernet

Conexión por cable RJ45.

Ejemplo:

- PCs de oficina
- Servidores
- Consolas

### NIC WiFi

Conexión inalámbrica.

Ejemplo:

- Portátiles
- Smartphones
- Tablets

### NIC Virtual

Creada por software.

Ejemplo:

- Máquinas virtuales
- VPN
- Docker

---

## 4. ¿Cómo funciona?

Cuando una aplicación envía datos:

1. El sistema operativo genera paquetes
2. La NIC los convierte en señales
3. Los transmite por cable o aire
4. También recibe señales y las entrega al sistema

---

## 5. Dirección MAC

Cada NIC tiene una dirección física única llamada:

`MAC Address`

Ejemplo:

`00:1A:2B:3C:4D:5E`

Sirve para identificar el dispositivo dentro de la red local.

---

## 6. Diferencia entre MAC e IP

Característica | MAC | IP
--------------|-----|----
Tipo | Física | Lógica
Nivel | Hardware | Red
Cambia | Normalmente no | Sí
Uso | LAN | Internet / Redes

---

## 7. Velocidad de NIC

Las tarjetas de red pueden trabajar a distintas velocidades:

- 100 Mbps
- 1 Gbps
- 2.5 Gbps
- 10 Gbps
- Más en servidores

Mientras mayor velocidad, mayor capacidad de transferencia.

---

## 8. Full Duplex y Half Duplex

### Half Duplex

Envía o recibe, pero no ambas al mismo tiempo.

### Full Duplex

Envía y recibe simultáneamente.

Es el estándar actual en Ethernet moderna.

---

## 9. NIC en WiFi

Las NIC inalámbricas trabajan con estándares como:

- 802.11n
- 802.11ac
- 802.11ax (WiFi 6)

Permiten movilidad sin cable.

---

## 10. NIC Virtual

Sistemas modernos crean interfaces virtuales.

Ejemplos:

- `tun0`
- `eth0`
- `wlan0`
- `docker0`

Muy comunes en Linux y virtualización.

---

## 11. NIC y Ciberseguridad

Las NIC son importantes en:

- Captura de tráfico
- Modo monitor WiFi
- Packet sniffing
- IDS/IPS
- Pentesting
- Segmentación de red

---

## 12. Modo Promiscuo

Permite que una NIC capture tráfico no dirigido solo a ella.

Usado en:

- Wireshark
- Análisis forense
- Monitoreo de red

---

## 13. Truco para Memorizar

NIC = Hardware de red

MAC = Identidad física

IP = Dirección lógica

Cable = Ethernet  
WiFi = Inalámbrica

---

## 14. Errores Comunes

### Pensar que NIC solo es tarjeta física

También existen NIC virtuales.

### Confundir MAC con IP

Son conceptos distintos.

### Pensar que WiFi no usa NIC

También usa NIC, solo que inalámbrica.

---

## 15. Para Examen Memoriza

- NIC = Tarjeta de red
- Permite conectar equipo a red
- Tiene MAC Address
- Puede ser cableada o WiFi
- Puede ser virtual
- Fundamental en comunicaciones

---

## Conclusión

La NIC es el componente que conecta un dispositivo con la red.

Comprender NIC, MAC e interfaces de red es esencial para redes, sistemas y ciberseguridad.
