# Contraseñas Seguras

## Introducción

Las contraseñas constituyen uno de los mecanismos de autenticación más utilizados en sistemas informáticos.

Su función principal es verificar la identidad de un usuario antes de permitir el acceso a información, servicios o recursos.

A pesar de su simplicidad, continúan siendo uno de los objetivos más frecuentes de los atacantes.

Por ello, comprender cómo crear y gestionar contraseñas seguras es un aspecto fundamental de la ciberseguridad.

---

## ¿Qué es una Contraseña?

Una contraseña es una secuencia de caracteres utilizada para autenticar a un usuario.

Ejemplo:

```text id="fwvdoz"
MiClave123!
```

Cuando un usuario inicia sesión, el sistema compara la información proporcionada con los datos almacenados para verificar su identidad.

---

## Importancia de las Contraseñas

Las contraseñas protegen:

* Cuentas de correo electrónico
* Redes sociales
* Aplicaciones empresariales
* Servicios bancarios
* Sistemas corporativos
* Dispositivos personales

Una contraseña comprometida puede permitir accesos no autorizados y provocar incidentes de seguridad.

---

## Características de una Contraseña Segura

### Longitud

La longitud es uno de los factores más importantes.

Se recomienda utilizar:

```text id="rjlwmu"
12 caracteres o más
```

Preferiblemente:

```text id="z4lvh8"
16 caracteres o más
```

---

### Complejidad

Combinar distintos tipos de caracteres:

* Letras mayúsculas
* Letras minúsculas
* Números
* Símbolos

Ejemplo:

```text id="e7rx7q"
Montaña!Cafe#Luna92
```

---

### Unicidad

Cada cuenta debe tener una contraseña diferente.

La reutilización aumenta significativamente el riesgo.

---

### Imprevisibilidad

Evitar:

* Nombres propios
* Fechas de nacimiento
* Información pública
* Palabras comunes

---

## Ejemplos

### Contraseñas Débiles

```text id="axzc8f"
123456
password
admin
qwerty
Juan123
```

---

### Contraseñas Más Seguras

```text id="8um0qm"
Montaña!Cafe#Luna92
Rio-Verde!84#Sol
Libro$Nube72!Mar
```

---

## Frases de Paso (Passphrases)

Una alternativa recomendable es utilizar frases largas y fáciles de recordar.

Ejemplo:

```text id="tdh9lu"
MiPerroCorreFelizPorLaPlaya2025!
```

Ventajas:

* Mayor longitud
* Fácil memorización
* Mayor resistencia a ataques

---

## Riesgos Asociados

### Fuerza Bruta

Intentos repetidos hasta encontrar la contraseña correcta.

---

### Ataques de Diccionario

Uso de listas de contraseñas comunes.

---

### Credential Stuffing

Reutilización de credenciales obtenidas en filtraciones previas.

---

### Phishing

Engaño para que la víctima entregue voluntariamente sus credenciales.

---

### Malware

Algunas amenazas pueden robar contraseñas almacenadas o capturadas mediante keyloggers.

---

## Gestión de Contraseñas

### No Reutilizar Contraseñas

Cada servicio debe tener una contraseña única.

---

### Cambios Cuando Sea Necesario

No es obligatorio cambiar contraseñas constantemente.

Sin embargo, deben modificarse cuando:

* Exista sospecha de compromiso.
* Se produzca una filtración.
* Lo exijan políticas específicas.

---

### Utilizar Gestores de Contraseñas

Permiten:

* Generar claves seguras.
* Almacenar credenciales.
* Evitar reutilización.

Ejemplos:

* Bitwarden
* KeePass
* 1Password

---

## Autenticación Multifactor (MFA)

La autenticación multifactor añade una capa adicional de seguridad.

Combina algo que el usuario:

### Sabe

Ejemplo:

```text id="ojw9qa"
Contraseña
```

### Tiene

Ejemplo:

```text id="gnj5yl"
Aplicación de autenticación
```

### Es

Ejemplo:

```text id="v0a6iq"
Huella digital
```

Incluso si una contraseña es robada, MFA puede impedir el acceso no autorizado.

---

## Almacenamiento Seguro

Las contraseñas no deben almacenarse en texto plano.

Los sistemas modernos utilizan:

* Hashes criptográficos
* Salts
* Algoritmos especializados

Ejemplos recomendados:

* bcrypt
* scrypt
* Argon2

---

## Buenas Prácticas

* Utilizar contraseñas largas.
* No reutilizar credenciales.
* Habilitar MFA.
* Utilizar gestores de contraseñas.
* Mantener dispositivos actualizados.
* Desconfiar de correos sospechosos.
* Proteger información sensible.

---

## Errores Comunes

### Utilizar Contraseñas Simples

Ejemplo:

```text id="0wb7pn"
123456
```

---

### Reutilizar Credenciales

Un único incidente puede comprometer múltiples cuentas.

---

### Compartir Contraseñas

Las credenciales son personales y deben mantenerse privadas.

---

### Desactivar MFA

Eliminar una capa importante de protección aumenta el riesgo.

---

## Relación con Otros Temas

Las contraseñas están directamente relacionadas con:

* Phishing
* Fuerza bruta
* Malware
* Gestión de riesgos
* Autenticación
* Protección de identidades

Por ello constituyen uno de los elementos más importantes de la seguridad informática.

---

## Conclusión

Las contraseñas siguen siendo un mecanismo fundamental de autenticación en sistemas modernos.

La combinación de contraseñas robustas, gestores de credenciales y autenticación multifactor permite reducir significativamente el riesgo de accesos no autorizados y fortalecer la seguridad de usuarios y organizaciones.
