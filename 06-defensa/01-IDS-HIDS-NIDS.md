# IDS, HIDS y NIDS

## Introducción

**IDS** significa:

`Intrusion Detection System`

En español:

**Sistema de Detección de Intrusiones**

Su función es detectar actividades sospechosas, ataques o comportamientos anómalos dentro de sistemas o redes.

No siempre bloquea ataques; muchas veces **detecta y alerta**.

Es una pieza clave en ciberseguridad defensiva.

---

## 1. ¿Para qué sirve un IDS?

Permite identificar:

- Intentos de intrusión
- Escaneos de red
- Malware
- Fuerza bruta
- Tráfico anómalo
- Cambios sospechosos
- Explotación de vulnerabilidades

---

## 2. Tipos Principales

Existen dos tipos más comunes:

- **HIDS**
- **NIDS**

---

## 3. HIDS

**HIDS** significa:

`Host Intrusion Detection System`

Protege un **equipo individual**.

Se instala en:

- Servidores
- PCs
- Laptops
- Endpoints críticos

Monitorea:

- Archivos
- Logs
- Procesos
- Integridad
- Usuarios
- Cambios del sistema

Ejemplo:

Un servidor cambia archivos sensibles sin autorización.

HIDS genera alerta.

---

## 4. NIDS

**NIDS** significa:

`Network Intrusion Detection System`

Monitorea el **tráfico de red**.

Se coloca en puntos estratégicos:

- Entrada a Internet
- Entre VLANs
- Data center
- Red interna

Analiza:

- Paquetes
- Protocolos
- Firmas de ataque
- Comportamiento extraño

Ejemplo:

Detecta escaneo de puertos masivo.

---

## 5. Diferencia Rápida

Característica | HIDS | NIDS
--------------|------|------
Protege | Host | Red
Ubicación | Equipo | Segmento red
Ve archivos | Sí | No
Ve tráfico | Parcial | Sí
Ejemplo | Servidor | Gateway

---

## 6. ¿Cómo Detectan?

### Basado en Firmas

Busca patrones conocidos.

Ejemplo:

Payload de malware conocido.

### Basado en Anomalías

Detecta comportamiento fuera de lo normal.

Ejemplo:

Servidor enviando miles de conexiones extrañas.

---

## 7. Ejemplo Real

Atacante hace fuerza bruta SSH.

NIDS detecta múltiples intentos.

HIDS detecta muchos fallos de login en servidor.

SOC recibe alerta.

---

## 8. IDS vs IPS

### IDS

Detecta y alerta.

### IPS

`Intrusion Prevention System`

Detecta y bloquea automáticamente.

---

## 9. Herramientas Conocidas

- Snort
- Suricata
- Zeek
- OSSEC
- Wazuh

---

## 10. IDS en Empresas

Se usa para:

- SOC
- SIEM
- Monitoreo continuo
- Cumplimiento
- Respuesta a incidentes
- Threat Hunting

---

## 11. Ventajas

- Visibilidad
- Detección temprana
- Alertas automáticas
- Investigación forense
- Reducción de tiempo de respuesta

---

## 12. Limitaciones

- Falsos positivos
- Requiere tuning
- Mucha alerta si está mal configurado
- No siempre bloquea
- Necesita personal que revise eventos

---

## 13. Truco para Memorizar

HIDS = Host

NIDS = Network

IDS = Detecta

IPS = Bloquea

---

## 14. Errores Comunes

### Pensar que IDS reemplaza firewall

No.

### Pensar que detecta todo

No siempre.

### Instalarlo y no revisar alertas

Error grave.

---

## 15. Para Examen Memoriza

- IDS = detección
- HIDS = equipo
- NIDS = red
- Firmas = ataques conocidos
- Anomalías = comportamiento raro
- IPS = prevención

---

## 16. Cadena de Defensa

Atacante escanea red  
↓  
NIDS alerta  
↓  
Ataca servidor  
↓  
HIDS alerta cambios internos  
↓  
SOC responde

---

## Conclusión

IDS, HIDS y NIDS son tecnologías esenciales para detectar amenazas antes de que causen daños mayores.

Comprender sus diferencias es fundamental en redes y ciberseguridad moderna.
