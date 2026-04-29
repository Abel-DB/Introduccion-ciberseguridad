# Direcciones IP

## Introducción

Una **dirección IP** es un identificador numérico asignado a un dispositivo dentro de una red.

Sirve para que los equipos puedan:

- Identificarse
- Comunicarse
- Enviar datos
- Recibir datos
- Ubicarse en una red

Sin direcciones IP no existiría Internet moderna.

---

## 1. ¿Qué significa IP?

IP significa:

`Internet Protocol`

Es el protocolo encargado de identificar dispositivos y enrutar información entre redes.

---

## 2. ¿Para qué sirve una IP?

Cuando un equipo quiere comunicarse necesita saber:

- Quién envía
- Quién recibe
- Dónde enviar datos
- Cómo responder

La dirección IP cumple esa función.

Ejemplo:

PC → Router → Servidor Web

Cada uno tiene una IP distinta.

---

## 3. Versiones principales

Existen dos tipos principales:

- IPv4
- IPv6

---

## 4. IPv4

Es la versión clásica más conocida.

Está formada por 4 bloques separados por puntos.

Ejemplo:

`192.168.1.10`

Formato:

X.X.X.X

Cada bloque va de:

`0 a 255`

Ejemplos válidos:

- 8.8.8.8
- 192.168.0.1
- 10.0.0.5

---

## 5. ¿Por qué máximo 255?

Cada bloque representa 8 bits.

8 bits = 1 byte

Valor máximo:

`11111111 = 255`

---

## 6. IPv6

Fue creado porque IPv4 se quedó sin suficientes direcciones.

Formato hexadecimal largo.

Ejemplo:

`2001:0db8:85a3:0000:0000:8a2e:0370:7334`

Ventajas:

- Muchísimas más direcciones
- Mejor diseño moderno
- Mejor escalabilidad

---

## 7. IP Pública vs Privada

### IP Pública

Es visible en Internet.

Normalmente la entrega el proveedor de Internet.

Ejemplo:

`80.25.100.44`

### IP Privada

Se usa dentro de redes internas.

Ejemplos:

- 192.168.x.x
- 10.x.x.x
- 172.16.x.x hasta 172.31.x.x

No son accesibles directamente desde Internet.

---

## 8. Ejemplo real en casa

Internet  
↓  
IP pública del router  
↓  
Router WiFi  
↓  

PC → 192.168.1.2  
Móvil → 192.168.1.3  
TV → 192.168.1.4

---

## 9. IP Estática vs Dinámica

### Estática

No cambia.

Útil para:

- Servidores
- Cámaras
- Impresoras

### Dinámica

Cambia automáticamente.

Muy común en hogares.

La asigna DHCP.

---

## 10. DHCP

Significa:

`Dynamic Host Configuration Protocol`

Asigna automáticamente:

- Dirección IP
- Gateway
- DNS
- Máscara de red

Ejemplo:

Cuando conectas tu móvil al WiFi.

---

## 11. DNS e IP

Las personas usamos nombres:

`google.com`

Pero los equipos usan IP.

DNS traduce:

google.com → 142.250.x.x

---

## 12. Loopback

IP especial del propio equipo:

`127.0.0.1`

También llamada:

`localhost`

Sirve para probar servicios internos.

---

## 13. Rangos Privados Importantes

Rango | Uso
------|-----
10.0.0.0/8 | Empresas grandes
172.16.0.0/12 | Redes medianas
192.168.0.0/16 | Hogares

---

## 14. Truco para Memorizar

192.168.x.x = Casa  
127.0.0.1 = Mi PC  
8.8.8.8 = DNS Google

Privada = Red interna  
Pública = Internet

---

## 15. Aplicación en Ciberseguridad

Las IP se usan para:

- Logs
- Rastreo de ataques
- Firewalls
- Escaneo de redes
- SIEM
- IDS/IPS
- VPN

---

## 16. Errores Comunes

### Pensar que IP identifica persona exacta

No siempre.

### Confundir pública con privada

Muy común.

### Pensar que IP nunca cambia

Muchas cambian dinámicamente.

---

## 17. Para Examen Memoriza

- IP = identificador en red
- IPv4 = 4 bloques
- IPv6 = hexadecimal largo
- Pública = Internet
- Privada = LAN
- 127.0.0.1 = localhost
- DHCP asigna IP

---

## Conclusión

Las direcciones IP permiten identificar dispositivos y enrutar información entre redes.

Comprenderlas es fundamental para redes, administración de sistemas y ciberseguridad.
