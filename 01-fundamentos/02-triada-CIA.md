# Triada CIA

## Introducción

La **Triada CIA** es uno de los modelos fundamentales de la ciberseguridad. Define los tres principios esenciales que deben protegerse en cualquier sistema de información:

- **C**onfidentiality (Confidencialidad)
- **I**ntegrity (Integridad)
- **A**vailability (Disponibilidad)

Estos tres pilares sirven como base para diseñar políticas, controles y estrategias de seguridad.

---

# 1. Confidencialidad

## Definición

La **confidencialidad** garantiza que la información solo sea accesible por personas, sistemas o procesos autorizados.

El objetivo es evitar accesos no autorizados, fugas de datos o espionaje.

## Ejemplos

- Acceso a cuentas bancarias mediante contraseña.
- Documentos internos visibles solo para empleados autorizados.
- Bases de datos cifradas.

## Mecanismos de protección

- Contraseñas seguras
- Autenticación multifactor (MFA)
- Cifrado de datos
- Control de accesos
- Gestión de privilegios

## Riesgos comunes

- Robo de credenciales
- Phishing
- Malware espía
- Fugas internas
- Ingeniería social

---

# 2. Integridad

## Definición

La **integridad** asegura que la información se mantenga correcta, completa y sin modificaciones no autorizadas.

Los datos no deben alterarse accidentalmente ni de forma maliciosa.

## Ejemplos

- Notas académicas sin manipulación.
- Transferencias bancarias con importes correctos.
- Archivos descargados sin cambios.

## Mecanismos de protección

- Hashes criptográficos
- Firmas digitales
- Control de versiones
- Logs de auditoría
- Permisos de escritura restringidos

## Riesgos comunes

- Manipulación de bases de datos
- Virus que alteran archivos
- Errores humanos
- Corrupción de datos

---

# 3. Disponibilidad

## Definición

La **disponibilidad** garantiza que los sistemas, servicios y datos estén accesibles cuando sean necesarios.

No basta con proteger datos: también deben poder utilizarse.

## Ejemplos

- Página web operativa 24/7.
- Plataforma universitaria disponible en época de exámenes.
- Servidor empresarial sin caídas.

## Mecanismos de protección

- Copias de seguridad
- Redundancia de servidores
- Balanceo de carga
- Sistemas UPS / energía auxiliar
- Planes de recuperación ante desastres

## Riesgos comunes

- Ataques DoS / DDoS
- Fallos eléctricos
- Errores de hardware
- Caídas de red
- Desastres naturales

---

# Relación entre los tres pilares

Los tres principios deben mantenerse equilibrados.

Ejemplo:

Un sistema extremadamente seguro pero inaccesible falla en disponibilidad.

Un sistema rápido pero sin control de acceso falla en confidencialidad.

Un sistema accesible pero manipulable falla en integridad.

---

# Ejemplo Práctico

## Plataforma bancaria online

### Confidencialidad

Solo el cliente puede entrar con sus credenciales.

### Integridad

Los saldos y movimientos deben ser exactos.

### Disponibilidad

La banca online debe funcionar cuando el cliente la necesite.

---

# Importancia en Ciberseguridad

La mayoría de medidas de seguridad buscan proteger uno o varios elementos de la Triada CIA.

Ejemplos:

- Firewall → disponibilidad y confidencialidad
- Cifrado → confidencialidad
- Backup → disponibilidad
- Firma digital → integridad

---

# Conclusión

La Triada CIA representa la base conceptual de la seguridad informática.

Cualquier organización que gestione información debe proteger:

- La privacidad de los datos
- La exactitud de la información
- La continuidad de los servicios

Comprender este modelo es esencial para analizar riesgos y diseñar sistemas seguros.
