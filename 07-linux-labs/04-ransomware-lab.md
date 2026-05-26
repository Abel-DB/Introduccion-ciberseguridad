# FASE 1 — Configuración de infraestructura atacante (Kali)

## Objetivo

Configurar Kali Linux como infraestructura atacante para el laboratorio de simulación en un entorno controlado utilizando Docker.

Arquitectura inicial:

```text
EndeavourOS (Host)

└── Kali Docker
        │
        └── RansomwareSim
```

Componentes del laboratorio:

```text
Encoder.py
Decoder.py
controlpanel.py
```

Roles:

| Componente | Función |
|---|---|
| Encoder.py | Simulación de impacto |
| Decoder.py | Recuperación |
| controlpanel.py | Servidor de recuperación |

---

## Paso 1 — Iniciar Kali

Verificar contenedores:

```bash
docker ps -a
```

Iniciar Kali:

```bash
docker start -i kali
```

Verificar usuario:

```bash
whoami
```

Resultado esperado:

```text
root
```

---

## Paso 2 — Actualizar entorno

Actualizar repositorios:

```bash
apt update
```

Instalar herramientas:

```bash
apt install -y git python3 python3-pip tree nano
```

Verificar instalación:

```bash
python3 --version

git --version
```

---

## Paso 3 — Crear laboratorio

Crear directorio principal:

```bash
mkdir ~/lab_ransomware
```

Entrar al directorio:

```bash
cd ~/lab_ransomware
```

Verificar ruta:

```bash
pwd
```

Resultado esperado:

```text
/root/lab_ransomware
```

---

## Paso 4 — Clonar repositorio

Clonar proyecto:

```bash
git clone https://github.com/HalilDeniz/RansomwareSim.git
```

Entrar:

```bash
cd RansomwareSim
```

Ver estructura:

```bash
tree -L 1
```

Resultado esperado:

```text
Encoder.py
Decoder.py
controlpanel.py
requirements.txt
```

---

## Paso 5 — Instalar dependencias

Instalar:

```bash
pip install -r requirements.txt
```

Verificar librería:

```bash
python3
```

Probar:

```python
from cryptography.fernet import Fernet
```

Salir:

```python
exit()
```

---

# Adaptaciones Linux (Ubuntu víctima)

El proyecto original fue desarrollado para Windows, por lo que fue necesario adaptar cuatro componentes principales para el laboratorio utilizando Ubuntu como víctima.

## 1. Wallpaper

Implementación original:

```python
ctypes.windll.user32
```

Dependencia:

```text
Windows
```

Adaptación:

```text
visual/

└── recovery_wallpaper.png
```

Uso:

```text
Indicador visual posterior al impacto
```

---

## 2. Nota visual (README)

Implementación original:

```python
USERPROFILE/Desktop
```

Dependencia:

```text
Windows
```

Adaptación:

```text
~/Desktop/

README_RECOVERY.txt
```

Uso:

```text
Mensaje informativo del laboratorio
```

---

## 3. Extensiones objetivo

Implementación original:

```python
file_extensions = [
'.txt',
'.docx',
'.jpg'
]
```

Laboratorio:

```text
empresa/

gerencia/
pagos.xlsx

rrhh/
personal.pdf

finanzas/
presupuesto.docx
```

Extensiones utilizadas:

```text
.xlsx
.pdf
.docx
```

---

## 4. Directorio objetivo

Implementación original:

```python
directory='dosyalar/'
```

Laboratorio:

```text
lab_ransomware/

└── empresa/
```

Estructura:

```text
empresa/

├── gerencia
├── rrhh
└── finanzas
```

---

## Flujo visual del laboratorio

```text
Impacto
   ↓

empresa/

   ↓

README aparece

   ↓

Wallpaper cambia

   ↓

Recuperación
```

---

## Rol de Kali

Kali contendrá:

```text
Encoder
ControlServer
Clave recuperación
```

Arquitectura:

```text
Kali

├── Encoder
├── ControlServer
└── clave

        ↓

Ubuntu

empresa/
respaldo/
```

---

## Notas

- Entorno exclusivamente educativo.
- Laboratorio ejecutado sobre Docker.
- Ubuntu actuará como víctima.
- Kali actuará como infraestructura atacante.
- Se realizaron adaptaciones Windows → Linux.
- La fase de entrega será implementada posteriormente.
