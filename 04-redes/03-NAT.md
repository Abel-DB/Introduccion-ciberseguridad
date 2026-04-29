# NAT (Network Address Translation)

## Introducción

**NAT** significa:

`Network Address Translation`

Es una técnica usada por routers y firewalls para traducir direcciones IP privadas en direcciones IP públicas, y viceversa.

Gracias a NAT, muchos dispositivos de una red interna pueden compartir una sola IP pública para salir a Internet.

Es una tecnología fundamental en redes modernas.

---

## 1. ¿Para qué sirve NAT?

Sin NAT, cada dispositivo necesitaría una IP pública propia.

Con NAT:

- Muchos equipos usan una sola IP pública
- Se ahorran direcciones IPv4
- Se ocultan IP internas
- Se facilita la conexión doméstica y empresarial

Ejemplo:

- PC = `192.168.1.10`
- Móvil = `192.168.1.11`
- TV = `192.168.1.12`

Todos salen a Internet con:

`80.25.100.44`

---

## 2. ¿Cómo funciona?

Cuando un equipo interno envía tráfico:

1. Sale con IP privada
2. El router reemplaza esa IP por la pública
3. Guarda la relación en una tabla NAT
4. Cuando vuelve la respuesta, la devuelve al equipo correcto

---

## 3. Ejemplo práctico

Equipo interno:

`192.168.1.10`

Quiere acceder a:

`google.com`

El router cambia:

`192.168.1.10 → 80.25.100.44`

Internet solo ve la IP pública.

---

## 4. NAT en casa

PC = `192.168.1.2`  
Móvil = `192.168.1.3`  
TV = `192.168.1.4`

Todos pasan por:

Router con NAT

Salida pública:

`80.25.100.44`

---

## 5. Tipos de NAT

### NAT Estático

Una IP privada siempre se traduce a una IP pública fija.

Uso:

- Servidores
- Cámaras
- Equipos críticos

### NAT Dinámico

Usa un conjunto de IP públicas disponibles.

### PAT / NAT Overload

Muchos equipos comparten una sola IP pública usando puertos.

Es el más común en hogares.

---

## 6. ¿Qué es PAT?

PAT significa:

`Port Address Translation`

Ejemplo:

`192.168.1.2:5000`  
`192.168.1.3:5001`  
`192.168.1.4:5002`

Todos salen por:

`80.25.100.44`

Pero diferenciados por puertos.

---

## 7. Ventajas de NAT

- Ahorra IP públicas
- Permite redes privadas
- Añade cierta ocultación interna
- Fácil implementación
- Muy usado mundialmente

---

## 8. Desventajas de NAT

- Rompe conexiones directas
- Puede complicar VoIP o gaming
- Requiere port forwarding
- Añade complejidad al diagnosticar problemas

---

## 9. Port Forwarding

Permite abrir un puerto externo hacia un equipo interno.

Ejemplo:

`Puerto 80 público → 192.168.1.50`

Uso común:

- Servidor web
- Cámara IP
- Juegos online
- Acceso remoto

---

## 10. NAT y Seguridad

NAT no es firewall, pero ayuda porque:

- Oculta IP privadas
- Bloquea conexiones entrantes no solicitadas

Aun así, siempre se recomienda firewall real.

---

## 11. NAT en Empresas

Se usa para:

- Salida de empleados a Internet
- Publicar servidores internos
- Redes corporativas grandes
- Segmentación

---

## 12. NAT y IPv6

IPv6 tiene muchísimas direcciones disponibles.

Por eso NAT no es tan necesario en IPv6.

Sin embargo, aún se usa en entornos mixtos.

---

## 13. Truco para Memorizar

Privada dentro  
Pública fuera

Muchos equipos  
1 sola IP pública

Router = Traductor

---

## 14. Aplicación en Ciberseguridad

NAT aparece en:

- Firewalls
- Logs
- Análisis de tráfico
- Publicación de servicios
- Pentesting interno
- Troubleshooting

---

## 15. Errores Comunes

### Pensar que NAT = Firewall

Incorrecto.

### Pensar que NAT da anonimato total

Incorrecto.

### No entender puertos en PAT

Muy común.

---

## 16. Para Examen Memoriza

- NAT = Traducción de direcciones
- Privada → Pública
- Router realiza NAT
- Ahorra IPv4
- PAT usa puertos
- Muy común en hogares

---

## Conclusión

NAT es una tecnología esencial que permitió el crecimiento de Internet al reutilizar direcciones privadas.

Comprender NAT es básico para redes, administración de sistemas y ciberseguridad.
