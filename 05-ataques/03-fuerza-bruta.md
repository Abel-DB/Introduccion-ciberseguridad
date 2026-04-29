# Ataque de Fuerza Bruta

## Introducción

Un **ataque de fuerza bruta** consiste en probar muchas combinaciones de contraseñas o claves hasta encontrar la correcta.

Es uno de los métodos más antiguos y conocidos para comprometer cuentas, sistemas y cifrados débiles.

Su éxito depende de:

- Contraseñas débiles
- Falta de límites de intentos
- Mala configuración
- Tiempo disponible
- Potencia de cómputo

---

## 1. ¿Cómo funciona?

El atacante automatiza intentos masivos.

Ejemplo:

123456  
password  
admin123  
qwerty  
letmein

O genera combinaciones:

aaaaaa  
aaaaab  
aaaaac  
...

Hasta acertar.

---

## 2. Objetivos Comunes

- Cuentas de correo
- Redes WiFi
- SSH
- FTP
- Paneles web
- Bases de datos
- Archivos cifrados

---

## 3. Tipos de Fuerza Bruta

### Fuerza Bruta Pura

Prueba todas las combinaciones posibles.

### Ataque de Diccionario

Usa listas de contraseñas comunes.

### Credential Stuffing

Usa usuario/contraseña filtrados en otras brechas.

### Password Spraying

Prueba una contraseña común contra muchas cuentas.

Ejemplo:

Summer2024!

### Hybrid Attack

Combina diccionario + variaciones.

Ejemplo:

Password123

---

## 4. Ejemplo Real

Login corporativo:

Usuario:

juan@empresa.com

Script prueba:

- Welcome123
- Empresa2024
- Juan1234
- Password1

Si acierta, obtiene acceso.

---

## 5. ¿Por qué funciona?

Porque muchas personas usan:

- Contraseñas cortas
- Repetidas
- Predecibles
- Datos personales
- Misma clave en varias webs

---

## 6. Tiempo de Ataque

Depende de:

- Longitud de contraseña
- Complejidad
- Rate limiting
- Hash usado
- Hardware atacante

Ejemplo:

123456 = segundos

X7!mQ9@2L# = mucho más difícil

---

## 7. Fuerza Bruta Offline

Ocurre cuando el atacante roba hashes y prueba sin límites localmente.

Muy peligroso.

Ejemplo:

- Hashes filtrados
- Base de datos comprometida

---

## 8. Fuerza Bruta Online

Se prueba directamente contra login real.

Limitado por:

- Bloqueos
- CAPTCHA
- Rate limiting
- MFA

---

## 9. Herramientas Conocidas

Usadas en laboratorios y pentesting autorizado:

- Hydra
- John the Ripper
- Hashcat
- Burp Intruder
- Medusa

---

## 10. Cómo Defenderse

- Contraseñas largas
- MFA
- Rate limiting
- Bloqueo tras intentos fallidos
- Alertas de login
- Password manager
- Hash fuerte (bcrypt, Argon2)

---

## 11. Contraseña Fuerte

Mala:

maria123

Buena:

Viento!Mesa9$Roca

Mejor si es larga y única.

---

## 12. Fuerza Bruta en WiFi

También se usa contra redes WiFi débiles.

Ejemplo:

- Captura handshake
- Prueba claves offline

---

## 13. Aplicación en Ciberseguridad

Tema clave para:

- Pentesting
- Hardening
- IAM
- Blue Team
- Red Team
- SOC

---

## 14. Truco para Memorizar

Fuerza bruta = probar hasta acertar

Contraseña débil = alto riesgo

MFA = gran defensa

Largo > solo complejo

---

## 15. Errores Comunes

### Pensar que solo importan símbolos

La longitud importa muchísimo.

### Reutilizar contraseñas

Muy peligroso.

### No usar MFA

Gran error actual.

---

## 16. Para Examen Memoriza

- Fuerza bruta = intentos masivos
- Diccionario = claves comunes
- Credential stuffing = claves filtradas
- Password spraying = una clave muchas cuentas
- MFA reduce riesgo
- Contraseñas largas ayudan

---

## 17. Cadena de Ataque

Login público  
↓  
Script automático  
↓  
Miles de intentos  
↓  
Contraseña correcta  
↓  
Acceso no autorizado

---

## Conclusión

El ataque de fuerza bruta sigue siendo efectivo porque muchos usuarios y organizaciones mantienen malas prácticas de contraseñas.

Comprender cómo funciona y cómo mitigarlo es esencial en ciberseguridad.
