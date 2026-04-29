# Laboratorio Linux: GoPhish + MailHog  
## Simulación Controlada de Phishing — Banco Andino Digital

## Introducción

Este laboratorio muestra la creación de una **campaña de phishing controlada y autorizada** utilizando herramientas reales en entorno local. Se desarrolló con fines educativos para comprender cómo operan este tipo de ataques y cómo defenderse frente a ellos. :contentReference[oaicite:0]{index=0}

Tecnologías utilizadas:

- **GoPhish** → Plataforma profesional para simulaciones de phishing  
- **MailHog** → Servidor SMTP local de pruebas  
- **Linux** → Sistema operativo del laboratorio  
- **Go** → Lenguaje necesario para compilar e instalar herramientas

Escenario simulado:

```text
Banco Andino Digital
```

---

# Conceptos Fundamentales

## ¿Qué es Phishing?

El **phishing** es una técnica de ataque en la que un atacante suplanta una entidad confiable para engañar a una víctima y lograr que entregue:

- Credenciales
- Información bancaria
- Datos personales
- Acceso corporativo

Normalmente se realiza por:

- Correo electrónico
- SMS
- Redes sociales
- Sitios web falsos

---

## ¿Qué es Ingeniería Social?

La **ingeniería social** consiste en manipular psicológicamente a una persona para que tome decisiones inseguras.

Ejemplos comunes:

- Crear urgencia
- Simular autoridad
- Generar miedo
- Prometer recompensas
- Pedir verificación inmediata

El phishing es una forma de ingeniería social.

---

## ¿Qué es una Campaña de Phishing?

Una **campaña** es una operación organizada que incluye:

- Lista de víctimas objetivo
- Correos personalizados
- Enlaces maliciosos
- Landing pages falsas
- Captura de datos
- Seguimiento de resultados

En ciberseguridad defensiva se simulan campañas para medir riesgos humanos.

---

## ¿Qué es GoPhish?

**GoPhish** es una plataforma open source diseñada para crear campañas de phishing simuladas de forma ética y autorizada.

Permite:

- Enviar correos de prueba
- Diseñar plantillas HTML
- Crear páginas falsas controladas
- Registrar clics
- Registrar formularios enviados
- Medir comportamiento de usuarios

---

## ¿Qué es MailHog?

**MailHog** es un servidor SMTP local de pruebas.

Su función es:

- Recibir correos localmente
- No enviar correos reales a Internet
- Ver mensajes desde navegador
- Probar campañas sin riesgo externo

Ideal para laboratorios.

---

# Objetivos del Laboratorio

Aprender a configurar:

- GoPhish
- MailHog
- Perfiles SMTP
- Landing pages
- Plantillas HTML
- Grupos de usuarios
- Campañas completas
- Resultados y métricas

---

# Requisitos Previos

## Instalar Go

Verificar instalación:

```bash
go version
```

Si no está instalado (Arch / EndeavourOS):

```bash
sudo pacman -S go
```

---

# Parte I — Instalación de GoPhish

---

## 1. Descargar Código Fuente

```bash
git clone https://github.com/gophish/gophish.git
```

### Explicación

| Elemento | Función |
|--------|--------|
| `git clone` | Descarga repositorio |
| URL | Proyecto oficial |

---

## 2. Entrar al Directorio

```bash
cd gophish
```

---

## 3. Compilar Proyecto

```bash
go build
```

Esto genera el binario:

```text
gophish
```

---

## 4. Ejecutar

```bash
sudo ./gophish
```

Salida esperada:

```text
Starting admin server at https://127.0.0.1:3333
```

---

# Parte II — Instalación de MailHog

---

## 1. Instalar

```bash
go install github.com/mailhog/MailHog@latest
```

---

## 2. Verificar Binario

```bash
ls ~/go/bin/
```

Debe aparecer:

```text
MailHog
```

---

## 3. Ejecutar

```bash
~/go/bin/MailHog
```

Servicios:

| Servicio | Dirección |
|---------|----------|
| SMTP | 127.0.0.1:1025 |
| Web UI | http://127.0.0.1:8025 |

---

# Parte III — Acceso a GoPhish

Abrir navegador:

```text
https://127.0.0.1:3333
```

Ingresar con:

- Usuario administrador
- Contraseña temporal mostrada en terminal

---

# Estructura de GoPhish

GoPhish organiza campañas en este orden lógico:

1. Sending Profiles  
2. Landing Pages  
3. Email Templates  
4. Users & Groups  
5. Campaigns  

---

# 1. Sending Profiles

## ¿Qué es?

Define **cómo se enviarán los correos**.

## Configuración

| Campo | Valor |
|------|------|
| Name | mailhog_lab |
| From | seguridad@bad.com |
| Host | 127.0.0.1:1025 |
| Username | vacío |
| Password | vacío |
| Ignore Cert Errors | Activado |

---

# 2. Landing Pages

## ¿Qué es?

Página web falsa que simula el portal legítimo.

## Configuración

| Campo | Valor |
|------|------|
| Name | andino_login |
| Capture Submitted Data | Sí |
| Capture Passwords | Sí |
| Redirect To | https://www.google.com |

---

## HTML Utilizado

```html
<div style="font-family:Arial;background:#eef2f7;padding:40px;">
  <div style="max-width:430px;margin:auto;background:white;padding:30px;border:1px solid #ddd;">

    <h2 style="color:#0A2E5D;text-align:center;">
      Banco Andino Digital
    </h2>

    <p style="text-align:center;">
      Verificación de Seguridad
    </p>

    <form method="POST">

      <p>Usuario</p>
      <input type="text" name="username" style="width:100%;padding:10px;">

      <p>Contraseña</p>
      <input type="password" name="password" style="width:100%;padding:10px;">

      <br><br>

      <button type="submit"
      style="width:100%;padding:12px;background:#0055CC;color:white;border:none;">
      Ingresar
      </button>

    </form>

  </div>
</div>
```

---

# 3. Email Templates

## ¿Qué es?

Correo falso que atraerá al usuario para hacer clic.

## Configuración

| Campo | Valor |
|------|------|
| Name | andino_alerta_seguridad |
| Subject | Verificación requerida de su cuenta Banco Andino Digital |

---

## HTML Utilizado

```html
<div style="font-family:Arial;padding:30px;background:#f4f6f8;">
  <div style="max-width:600px;margin:auto;background:white;padding:30px;border:1px solid #ddd;">

    <h2 style="color:#0A2E5D;">
      Banco Andino Digital
    </h2>

    <p>Estimado {{.FirstName}},</p>

    <p>Detectamos un acceso desde un dispositivo no habitual.</p>

    <p>Por seguridad, valide su identidad en las próximas 24 horas.</p>

    <p style="text-align:center;margin:30px 0;">
      <a href="{{.URL}}"
      style="background:#0055CC;color:white;padding:14px 24px;text-decoration:none;">
      Verificar Cuenta
      </a>
    </p>

    <p>Si reconoce esta actividad, ignore este mensaje.</p>

  </div>
</div>
```

---

## Variables Importantes

| Variable | Función |
|--------|--------|
| `{{.URL}}` | Link de campaña |
| `{{.FirstName}}` | Nombre usuario |

---

# 4. Users & Groups

## ¿Qué es?

Lista de objetivos simulados.

## Configuración

| Campo | Valor |
|------|------|
| Name | grupo_prueba |

## Targets

```text
Juan | Perez | juan@gmail.com | Cliente
Maria | Lopez | maria@gmail.com | Gerente
```

---

# 5. Campaigns

## ¿Qué es?

Une todos los componentes anteriores y ejecuta la simulación.

## Configuración

| Campo | Valor |
|------|------|
| Name | Campaña Banco Andino Digital |
| Email Template | andino_alerta_seguridad |
| Landing Page | andino_login |
| URL | http://127.0.0.1 |
| Launch Date | Now |
| Sending Profile | mailhog_lab |
| Groups | grupo_prueba |

---

# Flujo de Ataque Simulado

```text
Correo Fraudulento
        ↓
Usuario Abre Email
        ↓
Hace Clic
        ↓
Landing Page Falsa
        ↓
Envía Credenciales
        ↓
Redirección
```

---

# Resultados en GoPhish

Permite ver:

- Emails enviados
- Emails abiertos
- Clics
- Datos enviados
- Horarios
- Tasa de éxito

---

# Resultados en MailHog

Abrir:

```text
http://127.0.0.1:8025
```

Bandeja de entrada local de pruebas.

---

# Riesgos Reales que Simula

- Robo de credenciales
- Acceso inicial atacante
- Fraude bancario
- Compromiso corporativo
- Movimiento lateral

---

# Lo que Aprendes

- Ingeniería social realista
- Diseño de correos falsos
- Landing pages fraudulentas
- SMTP básico
- Concienciación de usuarios
- Métricas humanas
- Defensa organizacional

---

# Buenas Prácticas

- Solo usar entornos autorizados
- No enviar campañas reales sin permiso
- Medir resultados éticamente
- Capacitar después de pruebas
- Mejorar políticas internas

---

# Errores Comunes

## No tener Go instalado

No compila.

## SMTP mal configurado

No salen correos.

## URL incorrecta

Links rotos.

## No revisar métricas

Se pierde valor del ejercicio.

---

# Conclusión

GoPhish + MailHog permiten construir uno de los mejores laboratorios para comprender el phishing moderno desde la defensa.

No solo enseñan tecnología, también muestran que el factor humano sigue siendo una de las superficies de ataque más importantes en ciberseguridad.
