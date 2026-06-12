# Ataques DDoS

## Introducción

Un **DDoS (Distributed Denial of Service)** es un ataque cuyo objetivo es impedir que un servicio, sistema o sitio web funcione correctamente.

Para lograrlo, el atacante genera una enorme cantidad de tráfico o solicitudes hasta agotar los recursos disponibles.

Los ataques DDoS afectan principalmente la **disponibilidad**, uno de los pilares de la Tríada CIA.

---

## ¿Qué Significa DDoS?

DDoS significa:

```text id="cl4h3z"
Distributed Denial of Service
```

En español:

```text id="r5q8mw"
Denegación de Servicio Distribuida
```

---

## Diferencia entre DoS y DDoS

### DoS

Un único sistema genera el ataque.

```text id="nd1df5"
Atacante
    ↓
Servidor
```

---

### DDoS

Múltiples sistemas participan simultáneamente.

```text id="pd8vju"
Equipo 1
Equipo 2
Equipo 3
Equipo 4
    ↓
Servidor
```

La naturaleza distribuida hace que el ataque sea mucho más difícil de detener.

---

## Objetivo del Ataque

Los ataques DDoS buscan:

* Interrumpir servicios.
* Saturar servidores.
* Impedir el acceso de usuarios legítimos.
* Generar pérdidas económicas.
* Afectar la reputación de una organización.

---

## ¿Cómo Funciona?

Todo sistema posee recursos limitados:

* CPU
* Memoria
* Ancho de banda
* Conexiones simultáneas

El atacante intenta consumir esos recursos hasta que el servicio deje de responder correctamente.

---

## Botnets

La mayoría de ataques DDoS modernos utilizan:

```text id="0c0ndn"
Botnets
```

Una botnet es una red de dispositivos comprometidos controlados remotamente por un atacante.

Puede incluir:

* Computadoras
* Servidores
* Cámaras IP
* Routers
* Dispositivos IoT

Los propietarios normalmente desconocen que sus dispositivos participan en el ataque.

---

## Tipos de Ataques DDoS

### Ataques Volumétricos

Buscan saturar el ancho de banda.

Ejemplo:

```text id="c8f9l8"
Tráfico masivo
        ↓
Red saturada
```

---

### Ataques de Protocolo

Explotan características de protocolos de red.

Objetivo:

* Agotar recursos del servidor.
* Consumir conexiones disponibles.

---

### Ataques a la Aplicación

Se dirigen directamente a servicios específicos.

Ejemplo:

```text id="gm9dh0"
Miles de solicitudes HTTP
```

contra una página web.

Aunque el volumen sea menor, pueden resultar muy efectivos.

---

## Ejemplo Práctico

Sitio web empresarial:

```text id="l7ww2m"
100 usuarios normales
```

Capacidad del servidor:

```text id="v8qyz9"
500 solicitudes por segundo
```

Ataque:

```text id="5wy15j"
50.000 solicitudes por segundo
```

Resultado:

```text id="iqaxcc"
Servicio inaccesible
```

---

## Consecuencias

Un ataque exitoso puede provocar:

* Caída de servicios.
* Interrupción de operaciones.
* Pérdidas económicas.
* Pérdida de clientes.
* Daño reputacional.
* Incumplimiento de contratos.

---

## Sectores Frecuentemente Afectados

Los ataques DDoS pueden dirigirse contra:

* Bancos
* Universidades
* Empresas tecnológicas
* Comercio electrónico
* Organismos públicos
* Infraestructuras críticas

Prácticamente cualquier servicio conectado a Internet puede convertirse en objetivo.

---

## Indicadores de un Ataque DDoS

Algunas señales incluyen:

* Lentitud extrema.
* Sitios inaccesibles.
* Incremento repentino de tráfico.
* Elevado consumo de recursos.
* Múltiples conexiones simultáneas.

---

## Medidas de Mitigación

### Balanceo de Carga

Distribuye tráfico entre varios servidores.

---

### Infraestructura Escalable

Permite absorber aumentos de tráfico.

---

### Sistemas Anti-DDoS

Herramientas especializadas para detectar y filtrar tráfico malicioso.

---

### Firewalls y WAF

Ayudan a bloquear solicitudes sospechosas.

---

### Monitoreo Continuo

Permite detectar anomalías rápidamente.

---

### Redes de Distribución de Contenido (CDN)

Las CDN ayudan a distribuir la carga y mejorar la resiliencia frente a ataques.

---

## DDoS y la Tríada CIA

### Disponibilidad

Es el objetivo principal.

Los usuarios legítimos pierden acceso a los servicios.

### Confidencialidad

Generalmente no es el objetivo principal.

### Integridad

Normalmente no modifica información.

Por ello se considera un ataque orientado principalmente contra la disponibilidad.

---

## Casos Históricos

### Dyn (2016)

Un ataque masivo afectó servicios ampliamente utilizados en Internet.

---

### GitHub (2018)

Uno de los mayores ataques DDoS registrados hasta ese momento.

---

### Ataques contra Instituciones Financieras

Numerosos bancos han sufrido campañas DDoS destinadas a interrumpir operaciones.

---

## Relación con Otros Ataques

Los ataques DDoS pueden combinarse con:

* Malware
* Botnets
* Ingeniería social
* Extorsión digital
* Ransomware

En algunos casos se utilizan como distracción mientras se ejecutan otras actividades maliciosas.

---

## Aplicaciones en Ciberseguridad

Comprender los ataques DDoS permite:

* Diseñar infraestructuras resilientes.
* Implementar mecanismos de defensa.
* Mejorar la disponibilidad de servicios.
* Analizar incidentes de red.

Por ello son un tema fundamental en seguridad informática.

---

## Conclusión

Los ataques DDoS buscan impedir el funcionamiento normal de servicios y sistemas mediante la generación masiva de tráfico o solicitudes.

Su impacto puede ser significativo tanto a nivel técnico como económico, por lo que la planificación, el monitoreo y las medidas de mitigación son esenciales para proteger la disponibilidad de los servicios digitales.
