# Laboratorio — Simulación de recuperación en entorno controlado (Kali)

## Objetivo

Implementar un laboratorio educativo utilizando Kali Linux en Docker para representar un escenario controlado de impacto y recuperación.

Arquitectura:

```text
EndeavourOS (Host)

└── Kali Docker

        lab_ransomware/

        ├── RansomwareSim/
        │   ├── Encoder.py
        │   ├── Decoder.py
        │   └── ControlServer.py
        │
        ├── empresa/
        │   ├── finanzas/
        │   ├── rrhh/
        │   └── gerencia/
        │
        └── respaldo/
```

---

# Paso 1 — Iniciar Kali

Verificar:

```bash
docker ps -a
```

Entrar:

```bash
docker start -ai kali
```

Verificar usuario:

```bash
whoami
```

Resultado:

```text
root
```

---

# Paso 2 — Preparar entorno

Actualizar:

```bash
apt update
```

Instalar:

```bash
apt install -y \
git \
python3 \
python3-pip \
python3-venv \
tree \
neovim
```

---

# Paso 3 — Crear laboratorio

Crear:

```bash
mkdir lab_ransomware
```

Entrar:

```bash
cd lab_ransomware
```

---

# Paso 4 — Clonar repositorio

Clonar:

```bash
git clone https://github.com/HalilDeniz/RansomwareSim.git
```

Entrar:

```bash
cd RansomwareSim
```

Verificar:

```bash
tree -L 1
```

Resultado esperado:

```text
.
├── ControlServer.py
├── Decoder.py
├── Encoder.py
└── requirements.txt
```

---

# Paso 5 — Entorno virtual

Crear:

```bash
python3 -m venv lab_ransom
```

Activar:

```bash
source lab_ransom/bin/activate
```

Instalar dependencias:

```bash
pip install -r requirements.txt
```

Verificar:

```bash
pip list | grep cryptography
```

---

# Paso 6 — Crear empresa

Volver:

```bash
cd ..
```

Crear:

```bash
mkdir -p empresa/finanzas

mkdir -p empresa/rrhh

mkdir -p empresa/gerencia
```

---

## Finanzas

Entrar:

```bash
cd empresa/finanzas
```

Crear:

```bash
touch clientes.xlsx

touch pagos.pdf

touch facturas.docx
```

---

## RRHH

Entrar:

```bash
cd ../rrhh
```

Crear:

```bash
touch empleados.docx

touch contratos.pdf

touch nomina.xlsx
```

---

## Gerencia

Entrar:

```bash
cd ../gerencia
```

Crear:

```bash
touch reportes.docx

touch proyectos.pdf

touch estrategia.txt
```

---

# Paso 7 — Crear respaldo

Volver:

```bash
cd ~/lab_ransomware
```

Crear:

```bash
cp -r empresa respaldo
```

---

# Verificación

```bash
tree
```

Resultado esperado:

```text
lab_ransomware/

├── empresa
│
├── respaldo
│
└── RansomwareSim
```

---

# Adaptaciones Linux

## Wallpaper

No implementado.

La funcionalidad original fue diseñada para Windows y el laboratorio utiliza Docker sin entorno gráfico.

---

## Nota visual

Se mantiene una nota informativa mediante:

```text
/root/Readme.txt
```

---

## Extensiones

Utilizadas:

```text
.xlsx

.pdf

.docx
```

---

# Escenarios

CASO 1:

```text
Existe respaldo

→ recuperación desde respaldo
```

CASO 2:

```text
No existe respaldo

→ recuperación simulada
```
