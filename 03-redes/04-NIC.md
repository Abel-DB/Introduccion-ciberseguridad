# NIC (Network Interface Card)

## Introducción

La **NIC** (Network Interface Card), también conocida como tarjeta de red, es el componente encargado de permitir que un dispositivo se conecte a una red.

Puede estar integrada en la placa base o instalarse como un dispositivo independiente.

Sin una NIC, un equipo no podría enviar ni recibir información a través de una red.

---

## ¿Qué Significa NIC?

NIC significa:

```text
Network Interface Card
```

En español:

```text
Tarjeta de Interfaz de Red
```

Su función principal es actuar como intermediaria entre el sistema operativo y la red.

---

## Función Principal

La NIC permite:

* Conectarse a una red local.
* Enviar datos.
* Recibir datos.
* Identificarse dentro de una red.
* Comunicarse con otros dispositivos.

Toda comunicación de red pasa por una interfaz de red.

---

## Cómo Funciona

Cuando una aplicación envía información:

```text
Aplicación
    ↓
Sistema Operativo
    ↓
NIC
    ↓
Red
```

La NIC convierte los datos en señales que pueden transmitirse por el medio físico o inalámbrico.

---

## Tipos de NIC

### NIC Ethernet

Permite conexiones mediante cable de red.

Utiliza conectores RJ-45.

Ejemplo:

```text
PC
 ↓
Cable Ethernet
 ↓
Switch
```

Ventajas:

* Mayor estabilidad
* Menor latencia
* Mayor velocidad

---

### NIC Inalámbrica

Permite conectarse mediante WiFi.

Utiliza ondas de radio para transmitir información.

Ejemplo:

```text
Laptop
   ↓
WiFi
   ↓
Access Point
```

Ventajas:

* Movilidad
* Facilidad de instalación
* Menor cantidad de cables

---

## Dirección MAC

Cada NIC posee una dirección física única denominada:

```text
MAC Address
```

MAC significa:

```text
Media Access Control
```

Ejemplo:

```text
00:1A:2B:3C:4D:5E
```

La dirección MAC permite identificar dispositivos dentro de una red local.

---

## Diferencia entre IP y MAC

| Característica | IP                       | MAC                  |
| -------------- | ------------------------ | -------------------- |
| Nivel          | Lógico                   | Físico               |
| Puede cambiar  | Sí                       | Normalmente no       |
| Uso            | Comunicación entre redes | Identificación local |
| Ejemplo        | 192.168.1.10             | 00:1A:2B:3C:4D:5E    |

---

## Velocidades Comunes

Las NIC modernas suelen soportar:

| Velocidad     | Uso                            |
| ------------- | ------------------------------ |
| 100 Mbps      | Equipos antiguos               |
| 1 Gbps        | Hogares y oficinas             |
| 10 Gbps       | Centros de datos               |
| 40 Gbps o más | Infraestructuras empresariales |

---

## NIC y el Modelo OSI

La NIC trabaja principalmente en:

### Capa Física

Transmite señales.

### Capa de Enlace de Datos

Gestiona direcciones MAC y tramas.

Por ello es un componente fundamental para la comunicación de red.

---

## Aplicaciones en Ciberseguridad

Las NIC tienen relevancia en:

### Análisis de Tráfico

Captura de paquetes mediante herramientas como:

* Wireshark
* tcpdump

### Monitoreo de Redes

Permiten observar actividad sospechosa.

### Forense Digital

Análisis de comunicaciones y eventos de red.

### Segmentación

Identificación y control de dispositivos conectados.

---

## Modo Promiscuo

Una NIC puede configurarse en:

```text
Promiscuous Mode
```

En este modo captura más tráfico del que normalmente recibiría.

Es utilizado por herramientas de análisis de red.

Ejemplo:

* Wireshark
* IDS
* Sistemas de monitoreo

---

## Riesgos de Seguridad

### Suplantación MAC

Un atacante puede modificar temporalmente una dirección MAC.

Esto se conoce como:

```text
MAC Spoofing
```

---

### Interfaces No Controladas

Dispositivos conectados sin autorización pueden convertirse en puntos de acceso para atacantes.

---

### Drivers Vulnerables

Controladores desactualizados pueden contener vulnerabilidades explotables.

---

## Buenas Prácticas

* Mantener drivers actualizados.
* Controlar dispositivos conectados.
* Utilizar segmentación de red.
* Monitorear actividad sospechosa.
* Deshabilitar interfaces innecesarias.

---

## Relación con los Temas Anteriores

La NIC trabaja junto con:

* Direcciones IP
* Máscaras de subred
* NAT
* Switches
* Routers

Todos estos elementos permiten la comunicación entre dispositivos y redes.

---

## Conclusión

La NIC es el componente que permite a un dispositivo conectarse y comunicarse dentro de una red.

Comprender su funcionamiento ayuda a entender cómo circula la información, cómo se identifican los equipos y cómo pueden analizarse las comunicaciones desde una perspectiva de administración y ciberseguridad.
