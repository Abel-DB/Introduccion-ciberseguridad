# IDS, HIDS y NIDS

## Introducción

La detección temprana de actividades sospechosas es una parte fundamental de la ciberseguridad.

Para ello existen sistemas especializados capaces de monitorear eventos y alertar sobre posibles incidentes de seguridad.

Estos sistemas se conocen como:

* IDS (Intrusion Detection System)
* HIDS (Host-based Intrusion Detection System)
* NIDS (Network-based Intrusion Detection System)

Su función principal es identificar comportamientos anómalos o actividades potencialmente maliciosas.

---

## ¿Qué es un IDS?

### Definición

Un **IDS (Intrusion Detection System)** es una herramienta diseñada para detectar actividades sospechosas o intentos de intrusión.

Su objetivo no es bloquear ataques, sino identificarlos y generar alertas.

---

## Funcionamiento General

Proceso simplificado:

```text
Actividad
    ↓
Monitoreo
    ↓
Análisis
    ↓
Detección
    ↓
Alerta
```

Cuando se detecta un comportamiento anómalo, el sistema notifica al administrador o equipo de seguridad.

---

## Métodos de Detección

### Basado en Firmas

Compara eventos con patrones conocidos de ataques.

Ejemplo:

* Malware conocido
* Exploits documentados
* Ataques previamente identificados

Ventaja:

* Alta precisión para amenazas conocidas.

Desventaja:

* No detecta amenazas nuevas.

---

### Basado en Anomalías

Detecta comportamientos diferentes a los habituales.

Ejemplo:

* Tráfico inusualmente elevado.
* Accesos fuera de horario.
* Actividad anormal de usuarios.

Ventaja:

* Puede detectar amenazas desconocidas.

Desventaja:

* Mayor cantidad de falsos positivos.

---

## HIDS (Host-based Intrusion Detection System)

### Definición

Un HIDS monitorea actividades dentro de un equipo específico.

Analiza:

* Archivos
* Procesos
* Logs
* Configuraciones
* Usuarios

---

## ¿Qué Puede Detectar un HIDS?

Ejemplos:

* Modificación de archivos críticos.
* Escalada de privilegios.
* Instalación de malware.
* Creación de usuarios sospechosos.
* Cambios de configuración no autorizados.

---

## Ejemplo de HIDS

Servidor:

```text
Servidor Linux
      ↓
HIDS
      ↓
Monitoreo Local
```

Si alguien modifica archivos sensibles, el sistema genera una alerta.

---

## Ventajas del HIDS

* Visibilidad detallada del sistema.
* Detección de cambios internos.
* Monitoreo de archivos críticos.
* Identificación de actividad local sospechosa.

---

## Limitaciones del HIDS

* Consume recursos del equipo.
* Debe instalarse en cada dispositivo.
* Puede generar gran cantidad de eventos.

---

## NIDS (Network-based Intrusion Detection System)

### Definición

Un NIDS monitorea el tráfico de red para identificar actividades sospechosas.

Analiza paquetes que circulan entre dispositivos.

---

## ¿Qué Puede Detectar un NIDS?

Ejemplos:

* Escaneos de puertos.
* Intentos de explotación.
* Malware en tránsito.
* Ataques DoS y DDoS.
* Comunicación con servidores maliciosos.

---

## Ejemplo de NIDS

```text
Internet
    ↓
Firewall
    ↓
NIDS
    ↓
Red Interna
```

El sistema analiza el tráfico que atraviesa la red.

---

## Ventajas del NIDS

* Visibilidad de múltiples dispositivos.
* Monitoreo centralizado.
* No requiere instalación en cada host.
* Detección de actividad de red sospechosa.

---

## Limitaciones del NIDS

* No observa procesos internos de los equipos.
* Puede perder visibilidad en tráfico cifrado.
* Requiere una ubicación adecuada dentro de la red.

---

## HIDS vs NIDS

| Característica              | HIDS              | NIDS           |
| --------------------------- | ----------------- | -------------- |
| Ubicación                   | Equipo individual | Red            |
| Analiza                     | Sistema local     | Tráfico de red |
| Detecta cambios en archivos | Sí                | No             |
| Detecta escaneos de red     | Limitado          | Sí             |
| Instalación                 | Por host          | Centralizada   |

---

## IDS vs IPS

Es común confundir IDS con IPS.

### IDS

Detecta y alerta.

### IPS

Detecta y puede bloquear automáticamente.

Comparación:

| Característica     | IDS | IPS |
| ------------------ | --- | --- |
| Detección          | Sí  | Sí  |
| Alertas            | Sí  | Sí  |
| Bloqueo automático | No  | Sí  |

---

## Herramientas Conocidas

### HIDS

* OSSEC
* Wazuh
* Samhain

### NIDS

* Snort
* Suricata
* Zeek

Estas herramientas son ampliamente utilizadas en entornos profesionales.

---

## Aplicaciones en Ciberseguridad

Los IDS ayudan a detectar:

* Malware
* Phishing interno
* Fuerza bruta
* Escaneo de puertos
* Movimiento lateral
* Exfiltración de datos
* Actividad anómala

Por ello suelen formar parte de los centros de operaciones de seguridad (SOC).

---

## Relación con la Tríada CIA

### Confidencialidad

Detectan accesos no autorizados.

### Integridad

Identifican modificaciones sospechosas.

### Disponibilidad

Ayudan a detectar ataques que afectan servicios.

---

## Buenas Prácticas

* Mantener reglas actualizadas.
* Revisar alertas periódicamente.
* Correlacionar eventos con logs.
* Combinar HIDS y NIDS.
* Integrar con SIEM cuando sea posible.

---

## Conclusión

Los IDS son herramientas fundamentales para la detección de incidentes de seguridad.

Mientras que los HIDS se enfocan en la actividad interna de los equipos, los NIDS supervisan el tráfico de red.

La combinación de ambos proporciona una mayor visibilidad y mejora la capacidad de detectar amenazas en entornos tecnológicos modernos.
