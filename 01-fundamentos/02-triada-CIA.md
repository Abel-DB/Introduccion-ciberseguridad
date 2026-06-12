# Tríada CIA

## Introducción

La **Tríada CIA** es uno de los modelos fundamentales de la ciberseguridad. Define los tres principios esenciales que deben protegerse en cualquier sistema de información:

* **C**onfidentiality (Confidencialidad)
* **I**ntegrity (Integridad)
* **A**vailability (Disponibilidad)

Estos tres pilares sirven como base para diseñar políticas, controles y estrategias de seguridad.

---

## Confidencialidad

### Definición

La **confidencialidad** garantiza que la información solo sea accesible por personas, sistemas o procesos autorizados.

El objetivo es evitar accesos no autorizados, fugas de datos o espionaje.

### Ejemplos

* Acceso a cuentas bancarias mediante contraseña.
* Documentos internos visibles solo para empleados autorizados.
* Bases de datos cifradas.
* Historiales médicos protegidos.

### Mecanismos de Protección

* Contraseñas seguras
* Autenticación multifactor (MFA)
* Cifrado de datos
* Control de accesos
* Gestión de privilegios
* Segmentación de redes

### Riesgos Comunes

* Robo de credenciales
* Phishing
* Malware espía
* Fugas internas
* Ingeniería social

---

## Integridad

### Definición

La **integridad** asegura que la información se mantenga correcta, completa y sin modificaciones no autorizadas.

Los datos no deben alterarse accidentalmente ni de forma maliciosa.

### Ejemplos

* Notas académicas sin manipulación.
* Transferencias bancarias con importes correctos.
* Archivos descargados sin cambios.
* Registros empresariales consistentes.

### Mecanismos de Protección

* Hashes criptográficos
* Firmas digitales
* Control de versiones
* Logs de auditoría
* Permisos de escritura restringidos

### Riesgos Comunes

* Manipulación de bases de datos
* Virus que alteran archivos
* Errores humanos
* Corrupción de datos

---

## Disponibilidad

### Definición

La **disponibilidad** garantiza que los sistemas, servicios y datos estén accesibles cuando sean necesarios.

No basta con proteger la información; también debe poder utilizarse.

### Ejemplos

* Página web operativa 24/7.
* Plataforma educativa disponible durante exámenes.
* Servidor empresarial sin interrupciones.
* Servicios de emergencia siempre accesibles.

### Mecanismos de Protección

* Copias de seguridad
* Redundancia de servidores
* Balanceo de carga
* Sistemas UPS
* Planes de recuperación ante desastres

### Riesgos Comunes

* Ataques DoS y DDoS
* Fallos eléctricos
* Errores de hardware
* Caídas de red
* Desastres naturales

---

## Relación entre los Tres Pilares

Los tres principios deben mantenerse equilibrados.

Un sistema extremadamente seguro pero inaccesible falla en disponibilidad.

Un sistema rápido pero sin control de acceso falla en confidencialidad.

Un sistema accesible pero manipulable falla en integridad.

La seguridad efectiva requiere proteger simultáneamente los tres pilares.

---

## Relación con Otros Conceptos

La Tríada CIA sirve como base para comprender gran parte de la ciberseguridad.

* La criptografía ayuda a proteger la confidencialidad.
* Los hashes y firmas digitales ayudan a mantener la integridad.
* Los backups y sistemas redundantes contribuyen a la disponibilidad.
* Los ataques buscan comprometer uno o más de estos principios.

Por esta razón, la mayoría de controles de seguridad pueden relacionarse con alguno de los pilares de la Tríada CIA.

---

## Ejemplo Práctico

### Plataforma Bancaria Online

#### Confidencialidad

Solo el cliente puede acceder a su cuenta mediante credenciales válidas.

#### Integridad

Los saldos, transferencias y movimientos deben mantenerse correctos y sin alteraciones.

#### Disponibilidad

La plataforma debe estar accesible cuando el cliente necesite operar.

---

## Importancia en Ciberseguridad

La mayoría de medidas de seguridad buscan proteger uno o varios elementos de la Tríada CIA.

Ejemplos:

* Firewall → confidencialidad y disponibilidad
* Cifrado → confidencialidad
* Backup → disponibilidad
* Firma digital → integridad
* MFA → confidencialidad

Comprender este modelo permite analizar amenazas y diseñar controles de seguridad de manera más efectiva.

---

## Conclusión

La Tríada CIA constituye la base conceptual de la ciberseguridad moderna. Sus tres pilares —confidencialidad, integridad y disponibilidad— permiten definir qué debe protegerse y cómo evaluar la efectividad de las medidas de seguridad.

Comprender este modelo es fundamental para interpretar riesgos, analizar ataques y aplicar controles adecuados en cualquier entorno tecnológico.
