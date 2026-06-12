# Ransomware

## Introducción

El **ransomware** es un tipo de malware diseñado para impedir el acceso a sistemas o archivos y exigir un pago económico a cambio de su recuperación.

Actualmente es una de las amenazas más graves para personas, empresas, organismos públicos e infraestructuras críticas.

El término proviene de:

```text
Ransom = Rescate
Ware = Software
```

Por lo tanto:

```text
Ransomware = Software de Rescate
```

---

## ¿Cómo Funciona?

El ransomware suele seguir una secuencia de etapas:

```text
Infección
    ↓
Ejecución
    ↓
Cifrado de Archivos
    ↓
Bloqueo del Acceso
    ↓
Exigencia de Rescate
```

Una vez cifrados los datos, la víctima pierde el acceso a su información.

---

## Objetivos del Ransomware

Los atacantes buscan:

* Obtener beneficios económicos.
* Interrumpir operaciones.
* Extorsionar organizaciones.
* Robar información sensible.
* Presionar a las víctimas para realizar pagos.

---

## Métodos de Infección

### Phishing

Es la vía de entrada más frecuente.

Ejemplo:

* Correos con archivos adjuntos maliciosos.
* Enlaces falsos.
* Facturas fraudulentas.

---

### Vulnerabilidades

Sistemas sin actualizar pueden ser comprometidos automáticamente.

---

### Credenciales Robadas

Los atacantes utilizan:

* Fuerza bruta
* Credential stuffing
* Contraseñas filtradas

para acceder a servidores o equipos.

---

### Software Malicioso

Otros malware pueden descargar ransomware posteriormente.

---

### Servicios Expuestos

Sistemas accesibles desde Internet mal configurados pueden ser comprometidos.

---

## Proceso de Ataque

### Acceso Inicial

El atacante obtiene acceso al sistema.

---

### Persistencia

Intenta mantenerse dentro de la red el mayor tiempo posible.

---

### Reconocimiento

Busca:

* Servidores
* Bases de datos
* Recursos compartidos
* Copias de seguridad

---

### Cifrado

Los archivos son cifrados mediante algoritmos criptográficos.

---

### Extorsión

La víctima recibe una nota exigiendo un pago.

Ejemplo:

```text
Sus archivos han sido cifrados.

Para recuperarlos debe pagar 2 BTC.
```

---

## Doble Extorsión

Muchas variantes modernas utilizan una estrategia adicional.

Antes de cifrar:

* Roban información.
* Extraen documentos.
* Obtienen bases de datos.

Posteriormente amenazan con publicar los datos si no se realiza el pago.

Este enfoque se conoce como:

```text
Double Extortion
```

---

## Triple Extorsión

Algunos grupos criminales agregan presión adicional mediante:

* Ataques DDoS
* Contacto a clientes
* Presión mediática

Este enfoque recibe el nombre de:

```text
Triple Extortion
```

---

## Tipos de Ransomware

### Crypto Ransomware

Cifra archivos.

La víctima pierde acceso a la información.

---

### Locker Ransomware

Bloquea completamente el sistema.

Impide el uso normal del equipo.

---

### Ransomware como Servicio (RaaS)

Modelo criminal en el que desarrolladores alquilan ransomware a otros atacantes.

Significa:

```text
Ransomware as a Service
```

Ha contribuido al crecimiento de este tipo de ataques.

---

## Impacto del Ransomware

Las consecuencias pueden incluir:

* Pérdida de información.
* Interrupción de operaciones.
* Costes económicos elevados.
* Daño reputacional.
* Sanciones legales.
* Pérdida de clientes.

---

## Sectores Frecuentemente Afectados

* Hospitales
* Universidades
* Empresas privadas
* Organismos públicos
* Infraestructuras críticas
* Servicios financieros

Ninguna organización está completamente exenta del riesgo.

---

## Casos Históricos Conocidos

### WannaCry (2017)

Uno de los ataques más conocidos.

Características:

* Propagación automática.
* Alcance global.
* Afectó miles de organizaciones.

---

### Ryuk

Orientado principalmente a organizaciones empresariales.

---

### Conti

Grupo criminal responsable de múltiples campañas de ransomware.

---

### LockBit

Una de las familias más activas en los últimos años.

---

## Relación con la Criptografía

El ransomware utiliza conceptos criptográficos para impedir el acceso a la información.

Generalmente combina:

* Criptografía simétrica
* Criptografía asimétrica

Esto dificulta la recuperación de los archivos sin las claves correspondientes.

---

## Medidas de Protección

### Mantener Sistemas Actualizados

Corregir vulnerabilidades conocidas.

---

### Realizar Copias de Seguridad

Las copias de seguridad son una de las defensas más efectivas.

Deben mantenerse:

* Actualizadas
* Verificadas
* Separadas de la red principal

---

### Utilizar MFA

Reduce el riesgo de acceso mediante credenciales robadas.

---

### Capacitación de Usuarios

Permite detectar correos y enlaces sospechosos.

---

### Segmentación de Red

Limita la propagación del ataque.

---

### Monitoreo Continuo

Ayuda a detectar actividad anómala de forma temprana.

---

## ¿Debe Pagarse el Rescate?

Las autoridades suelen desaconsejar el pago porque:

* No garantiza la recuperación.
* Financia actividades criminales.
* Incentiva nuevos ataques.

Cada incidente requiere una evaluación específica, pero pagar no asegura la solución del problema.

---

## Relación con la Tríada CIA

### Confidencialidad

Puede existir robo de información.

### Integridad

Los datos pueden ser alterados o destruidos.

### Disponibilidad

Los sistemas y archivos dejan de estar accesibles.

Por ello el ransomware puede afectar simultáneamente los tres pilares de la seguridad.

---

## Relación con Otros Ataques

El ransomware suele combinarse con:

* Phishing
* Malware
* Fuerza bruta
* Robo de credenciales
* Explotación de vulnerabilidades

Normalmente forma parte de una cadena de ataque más amplia.

---

## Conclusión

El ransomware es una de las amenazas más importantes de la ciberseguridad moderna.

Su capacidad para cifrar información, interrumpir operaciones y generar pérdidas económicas lo convierte en un riesgo crítico para cualquier organización.

La prevención, las copias de seguridad, la capacitación de usuarios y las medidas de seguridad adecuadas son fundamentales para reducir su impacto.
