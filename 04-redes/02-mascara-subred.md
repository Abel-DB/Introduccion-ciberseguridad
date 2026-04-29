# Máscara de Subred

## Introducción

La **máscara de subred** es un valor que se utiliza junto con una dirección IP para separar:

- Parte de red
- Parte de host (dispositivo)

Permite organizar redes, dividirlas y enrutar correctamente el tráfico.

Es un concepto fundamental en redes y ciberseguridad.

---

## 1. ¿Para qué sirve?

Una dirección IP sola no indica qué parte pertenece a la red y cuál al equipo.

La máscara define:

- Qué parte identifica la red
- Qué parte identifica al dispositivo

Ejemplo:

IP: `192.168.1.10`

Máscara: `255.255.255.0`

Resultado:

- Red = `192.168.1`
- Host = `10`

---

## 2. ¿Cómo funciona?

La máscara usa bits:

- `1` = parte de red
- `0` = parte de host

Ejemplo:

`255.255.255.0`

En binario:

11111111.11111111.11111111.00000000

Esto significa:

- Primeros 24 bits = red
- Últimos 8 bits = hosts

---

## 3. Formato CIDR

En vez de escribir toda la máscara, se usa:

`/n`

Donde **n** es la cantidad de bits en 1.

Ejemplos:

- `255.0.0.0 = /8`
- `255.255.0.0 = /16`
- `255.255.255.0 = /24`

---

## 4. Ejemplo práctico

Dirección:

`192.168.1.34/24`

Significa:

- Red = `192.168.1.0`
- Host = `34`

Todos los equipos `192.168.1.x` suelen pertenecer a la misma red.

---

## 5. Máscaras comunes

Máscara | CIDR | Hosts aprox
--------|------|------------
255.0.0.0 | /8 | 16 millones
255.255.0.0 | /16 | 65 mil
255.255.255.0 | /24 | 254
255.255.255.128 | /25 | 126
255.255.255.192 | /26 | 62

---

## 6. ¿Por qué /24 tiene 254 hosts?

Quedan 8 bits para hosts.

2^8 = 256 direcciones

Pero:

- 1 dirección = red
- 1 dirección = broadcast

Entonces:

256 - 2 = 254 hosts usables

---

## 7. Dirección de Red

Es la primera dirección del rango.

Ejemplo:

`192.168.1.0`

No se asigna a dispositivos.

---

## 8. Broadcast

Es la última dirección del rango.

Ejemplo:

`192.168.1.255`

Sirve para enviar datos a todos los equipos de esa red.

No se asigna a hosts.

---

## 9. Rango de Hosts

Para:

`192.168.1.0/24`

Rango usable:

- `192.168.1.1`
- hasta
- `192.168.1.254`

---

## 10. Subnetting

Es dividir una red grande en redes pequeñas.

Ejemplo:

Red original:

`192.168.1.0/24`

Dividida en dos:

- `192.168.1.0/25`
- `192.168.1.128/25`

Ventajas:

- Mejor organización
- Más seguridad
- Menos tráfico

---

## 11. Importancia en Ciberseguridad

Permite:

- Segmentar redes
- Separar departamentos
- Aislar servidores
- Limitar movimiento lateral
- Mejorar reglas firewall

---

## 12. Truco para Memorizar

/8 = 255.0.0.0  
/16 = 255.255.0.0  
/24 = 255.255.255.0

La más común:

/24 = 254 hosts

---

## 13. Errores Comunes

### Confundir IP con máscara

Son conceptos distintos.

### Pensar que /24 son 255 hosts

Incorrecto. Son 254 usables.

### Asignar red o broadcast a un host

Incorrecto.

---

## 14. Para Examen Memoriza

- Máscara separa red y host
- Bits 1 = red
- Bits 0 = host
- /24 = 255.255.255.0
- /24 = 254 hosts
- Primera IP = red
- Última IP = broadcast

---

## 15. Ejemplo rápido

IP:

`10.0.0.55/8`

Red:

`10.0.0.0`

Broadcast:

`10.255.255.255`

Hosts: millones

---

## Conclusión

La máscara de subred permite organizar redes y definir qué equipos pertenecen al mismo segmento.

Comprender máscaras es esencial para redes, administración de sistemas y ciberseguridad.
