# Ataque de Fuerza Bruta

## Introducción

Un **ataque de fuerza bruta** consiste en probar múltiples combinaciones de contraseñas, claves o credenciales hasta encontrar la correcta.

Es uno de los métodos más antiguos y conocidos para obtener acceso no autorizado a sistemas, aplicaciones y servicios.

Su efectividad depende principalmente de:

* La fortaleza de las contraseñas.
* La existencia de límites de intentos.
* Las medidas de protección implementadas.
* La capacidad de procesamiento del atacante.

---

## ¿Cómo Funciona?

El atacante automatiza intentos de acceso utilizando herramientas especializadas.

Ejemplo:

```text
123456
password
admin123
qwerty
letmein
```

Si ninguna funciona, puede generar combinaciones automáticamente hasta encontrar la correcta.

---

## Objetivos Comunes

Los ataques de fuerza bruta suelen dirigirse contra:

* Cuentas de correo electrónico
* Redes WiFi
* Servicios SSH
* Servidores FTP
* Paneles web
* Bases de datos
* Aplicaciones empresariales

Cualquier sistema que utilice autenticación puede convertirse en un objetivo.

---

## Tipos de Ataque de Fuerza Bruta

### Fuerza Bruta Pura

Prueba todas las combinaciones posibles.

Ejemplo:

```text
aaaa
aaab
aaac
...
```

Es efectiva, pero puede requerir mucho tiempo.

---

### Ataque de Diccionario

Utiliza listas de contraseñas comunes.

Ejemplos:

```text
password
123456
admin
qwerty
```

Es mucho más rápido que probar todas las combinaciones posibles.

---

### Credential Stuffing

Utiliza credenciales obtenidas en filtraciones previas.

Ejemplo:

```text
usuario@email.com
Contraseña123
```

Si una persona reutiliza la misma contraseña en varios servicios, el ataque puede tener éxito.

---

### Password Spraying

Prueba una contraseña común contra muchas cuentas diferentes.

Ejemplo:

```text
Verano2024!
```

aplicada a cientos de usuarios.

Esto reduce la probabilidad de activar bloqueos por múltiples intentos.

---

### Ataque Híbrido

Combina diccionarios con modificaciones automáticas.

Ejemplo:

```text
Password
Password1
Password123
Password2024
```

Es una técnica muy utilizada actualmente.

---

## ¿Por Qué Funciona?

Muchas personas utilizan contraseñas:

* Cortas
* Predecibles
* Reutilizadas
* Basadas en datos personales
* Fáciles de recordar

Ejemplos:

```text
Juan123
maria2024
password
```

Este tipo de claves pueden descubrirse rápidamente.

---

## Fuerza Bruta Online

Se realiza directamente contra un sistema real.

Ejemplo:

```text
Usuario
     ↓
Página de Login
     ↓
Intentos automáticos
```

Suele estar limitada por:

* Bloqueos de cuenta
* CAPTCHA
* Rate Limiting
* MFA

---

## Fuerza Bruta Offline

Ocurre cuando el atacante obtiene hashes de contraseñas y realiza pruebas localmente.

Ejemplo:

```text
Base de datos comprometida
        ↓
Hashes robados
        ↓
Ataque local
```

Es especialmente peligrosa porque no existen límites de intentos.

---

## Tiempo de Ataque

El tiempo necesario depende de:

* Longitud de la contraseña
* Complejidad
* Algoritmo de hash
* Potencia del hardware
* Medidas defensivas

Ejemplo:

```text
123456
```

Puede descubrirse en segundos.

Mientras que:

```text
Montaña!Cafe#Luna92
```

Resulta mucho más difícil de comprometer.

---

## Herramientas Utilizadas

En entornos de laboratorio y pruebas autorizadas suelen utilizarse herramientas como:

* Hydra
* John the Ripper
* Hashcat
* Medusa
* Burp Intruder

Estas herramientas también son empleadas por profesionales de seguridad para evaluar la fortaleza de sistemas.

---

## Ataques Contra Redes WiFi

La fuerza bruta también puede utilizarse contra redes inalámbricas.

Proceso simplificado:

```text
Captura del Handshake
          ↓
Obtención de la Clave
          ↓
Pruebas Automáticas
```

Si la contraseña es débil, puede ser descubierta.

---

## Medidas de Protección

### Utilizar Contraseñas Largas

La longitud es uno de los factores más importantes.

Ejemplo:

```text
Montaña!Cafe#Luna92
```

---

### Habilitar MFA

La autenticación multifactor añade una capa adicional de protección.

Aunque una contraseña sea descubierta, el atacante necesitará un segundo factor.

---

### Aplicar Bloqueos Temporales

Bloquear cuentas después de varios intentos fallidos.

---

### Implementar Rate Limiting

Reducir la cantidad de intentos permitidos.

---

### Utilizar Gestores de Contraseñas

Permiten generar y almacenar claves únicas y complejas.

---

### Utilizar Hashes Seguros

Ejemplos recomendados:

* bcrypt
* scrypt
* Argon2

---

## Impacto en la Ciberseguridad

Un ataque exitoso puede permitir:

* Robo de información
* Acceso no autorizado
* Escalada de privilegios
* Movimiento lateral
* Instalación de malware
* Compromiso de sistemas corporativos

Por ello sigue siendo una amenaza relevante incluso en entornos modernos.

---

## Relación con Otros Ataques

La fuerza bruta suele combinarse con:

* Phishing
* Malware
* Credential Stuffing
* Ataques a WiFi
* Escalada de privilegios

Muchos incidentes comienzan con la obtención de credenciales válidas.

---

## Errores Comunes

### Pensar que la Complejidad es Más Importante que la Longitud

La longitud suele aportar una protección significativa.

---

### Reutilizar Contraseñas

Un único incidente puede comprometer múltiples cuentas.

---

### No Utilizar MFA

Actualmente es una de las medidas más efectivas para reducir el riesgo.

---

## Conclusión

Los ataques de fuerza bruta buscan obtener acceso probando múltiples combinaciones de credenciales hasta encontrar la correcta.

Aunque son técnicas conocidas desde hace años, continúan siendo efectivas cuando se utilizan contraseñas débiles o se carece de medidas de protección adecuadas.

El uso de contraseñas robustas, autenticación multifactor y mecanismos de control de acceso reduce considerablemente el riesgo de éxito de estos ataques.
