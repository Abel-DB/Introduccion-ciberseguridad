# Laboratorio Linux: GoPhish + MailHog  
## Simulación Controlada de Phishing — Banco Andino Digital

## Introducción

En este laboratorio se configuró una campaña educativa y controlada de phishing utilizando:

- **GoPhish** → Plataforma para campañas simuladas  
- **MailHog** → Servidor SMTP local para pruebas  
- **Linux** → Sistema operativo de trabajo  

Escenario utilizado:

```text
Banco Andino Digital
```

El objetivo es comprender cómo funcionan campañas de phishing desde una perspectiva defensiva y académica.

---

# Objetivos

Aprender a configurar:

- Instalación de GoPhish
- Instalación de MailHog
- Perfil SMTP
- Landing Page falsa controlada
- Plantilla de correo
- Grupo de usuarios
- Lanzamiento de campaña
- Resultados y métricas

---

# Requisitos Previos

## Tener instalado Go

Tanto GoPhish compilado desde código fuente como MailHog requieren Go instalado.

Verificar:

```bash
go version
```

Si muestra versión, está listo y si no.

Instalar:

EndeavourOS

```bash
sudo pacman -S go
```

---

# Parte I — Instalación de GoPhish

---

## 1. Descargar repositorio oficial

```bash
git clone https://github.com/gophish/gophish.git
```

Enlace: https://github.com/gophish/gophish

### Explicación

| Elemento | Función |
|--------|--------|
| `git clone` | Descarga repositorio |
| URL | Proyecto oficial |

---

## 2. Entrar a carpeta

```bash
cd gophish
```

### Explicación

| Comando | Función |
|--------|--------|
| `cd` | Cambiar directorio |

---

## 3. Compilar

```bash
go build
```

### Explicación

Compila el proyecto y genera el ejecutable:

```text
gophish
```

---

## 4. Ejecutar GoPhish

```bash
sudo ./gophish
```

### Resultado esperado

```text
Starting admin server at https://127.0.0.1:3333
```

---

# Parte II — Instalación de MailHog

---

## 1. Instalar MailHog

```bash
go install github.com/mailhog/MailHog@latest
```

Enlace: https://github.com/mailhog/mailhog

### Explicación

Descarga y compila MailHog usando Go.

---

## 2. Verificar binario

```bash
ls ~/go/bin/
```

Debe aparecer:

```text
MailHog
```

---

## 3. Ejecutar MailHog

```bash
~/go/bin/MailHog
```

### Servicios normales

| Servicio | Dirección |
|---------|----------|
| SMTP | 127.0.0.1:1025 |
| Web UI | http://127.0.0.1:8025 |

---

# ¿Qué es MailHog?

Servidor de correo falso para pruebas.

Permite:

- Recibir emails localmente
- No enviar correos reales
- Ver bandeja de entrada de pruebas
- Simular campañas seguras

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

# Configuración de Campaña

---

# 1️⃣ Sending Profiles

## New Profile

| Campo | Valor |
|------|------|
| Name | mailhog_lab |
| From | seguridad@bad.com |
| Host | 127.0.0.1:1025 |
| Username | vacío |
| Password | vacío |
| Ignore Cert Errors | Activado |

---

## Explicación

MailHog usa SMTP:

```text
127.0.0.1:1025
```

No requiere autenticación real.

---

# 2️⃣ Landing Pages

## New Landing Page

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
                🏦 Banco Andino Digital
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

                <button type="submit" style="width:100%;padding:12px;background:#0055CC;color:white;border:none;">
                    Ingresar
                </button>
            </form>

        </div>
</div>
```

---

# 3️⃣ Email Templates

## New Template

| Campo | Valor |
|------|------|
| Name | andino_alerta_seguridad |
| Subject | Verificación requerida de su cuenta Banco Andino Digital |

---

## HTML Utilizado

```html

<div style="font-family:Arial;padding:30px;background:#f4f6f8;">
    <div style="max-width:600px;margin:auto;background:white;padding:30px;border:1px solid #ddd;">

        <h2 style="color:#0A2E5D;">🏦 Banco Andino Digital</h2>

        <p>Estimado {{.FirstName}},</p>

        <p>Detectamos un acceso desde un dispositivo no habitual.</p>

        <p>Por seguridad, valide su identidad en las próximas 24 horas.</p>

        <p style="text-align:center;margin:30px 0;">
            <a href="{{.URL}}" style="background:#0055CC;color:white;padding:14px 24px;text-decoration:none;">
                Verificar Cuenta
            </a>
        </p>

        <p>Si reconoce esta actividad, ignore este mensaje.</p>

    </div>
</div>
```

---

## Explicación

```text
{{.URL}}
```

Variable automática de GoPhish que inserta el enlace de campaña.

---

# 4️⃣ Users & Groups

## New Group

| Campo | Valor |
|------|------|
| Name | grupo_prueba |

## Targets

```text
Juan | Perez | juan@gmail.com | Cliente
Maria | Lopez | maria@gmail.com | Gerente
```

También puedes usar solo tu correo.

---

# 5️⃣ Campaigns

## New Campaign

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

## Ejemplo URL

```text
http://192.168.1.15
```

---

# Flujo de la Simulación

```text
Correo Banco Andino
        ↓
Usuario hace clic
        ↓
Landing Page falsa
        ↓
Captura de datos
        ↓
Redirección Google
```

---

# Resultados en GoPhish

Puedes visualizar:

- Emails enviados
- Emails abiertos
- Clics realizados
- Formularios enviados
- Hora exacta

---

# Resultados en MailHog

Abrir:

```text
http://127.0.0.1:8025
```

Verás los correos recibidos.

---

# Comandos Utilizados

| Comando | Función |
|--------|--------|
| `git clone` | Descargar código |
| `cd` | Entrar carpeta |
| `go build` | Compilar |
| `sudo ./gophish` | Ejecutar |
| `go install` | Instalar MailHog |
| `ls` | Ver archivos |

---

# Errores Comunes

## No tener Go instalado

No compila.

## URL incorrecta

Links rotos.

## No abrir MailHog

No llegan correos visibles.

## No cambiar clave admin

Mala práctica.

---

# Buenas Prácticas

- Solo laboratorios autorizados
- Correos propios de prueba
- Medir resultados
- Formar usuarios luego
- Mejorar awareness

---

# Lo que Aprendes

- Funcionamiento real phishing
- SMTP básico
- Landing pages
- Ingeniería social
- Métricas humanas
- Seguridad ofensiva ética

---

# Conclusión

GoPhish + MailHog forman un laboratorio excelente para aprender phishing de forma segura y profesional.

Permiten comprender cómo operan campañas reales y cómo defender mejor a usuarios y organizaciones.
