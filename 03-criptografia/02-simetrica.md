# Criptografía Simétrica

## Introducción

La **criptografía simétrica** es un método de cifrado en el que se utiliza **la misma clave** tanto para cifrar como para descifrar la información.

Es uno de los sistemas criptográficos más antiguos y sigue siendo ampliamente utilizado en la actualidad por su velocidad y eficiencia.

---

# 1. ¿Cómo funciona?

El emisor y el receptor comparten una **clave secreta**.

Proceso:

Texto plano → Cifrado con clave → Texto cifrado  
Texto cifrado → Descifrado con la misma clave → Texto original

Ejemplo:

Mensaje: `HOLA`

Clave: `1234`

Ambas partes deben conocer esa clave.

---

# 2. ¿Por qué se llama simétrica?

Porque se usa la **misma clave** en ambos lados:

- Para proteger la información
- Para recuperarla

No existe separación entre clave pública y privada.

---

# 3. Ventajas

## Alta velocidad

Es mucho más rápida que la criptografía asimétrica.

## Menor consumo de recursos

Ideal para cifrar grandes volúmenes de datos.

## Muy usada en tiempo real

Perfecta para:

- VPN
- WiFi
- Archivos
- Bases de datos
- HTTPS

---

# 4. Desventajas

## Intercambio de clave

El mayor problema es cómo compartir la clave de forma segura.

Si un atacante roba la clave, podrá leer toda la información.

## Escalabilidad

En sistemas con muchos usuarios se necesitan muchas claves.

---

# 5. Ejemplo sencillo

Supongamos:

Mensaje: `SECRETO`

Clave: `ABC123`

Resultado cifrado:

`X7P91LQ`

Luego el receptor usa la misma clave para recuperar:

`SECRETO`

---

# 6. Algoritmos Simétricos Importantes

## AES

Es el estándar moderno más utilizado.

Versiones:

- AES-128
- AES-192
- AES-256

Usado en:

- WiFi WPA2 / WPA3
- VPN
- HTTPS
- Discos cifrados

## DES

Antiguo algoritmo hoy inseguro.

## 3DES

Versión mejorada de DES, actualmente en desuso.

## ChaCha20

Muy rápido y moderno.

---

# 7. AES explicado fácil

AES trabaja con bloques de datos y varias rondas matemáticas.

Solo recuerda:

`AES = rápido + seguro + estándar actual`

---

# 8. ¿Dónde se usa en la vida real?

- Contraseñas protegidas
- Archivos ZIP
- BitLocker
- VeraCrypt
- WiFi doméstico
- VPN
- Comunicación segura web

---

# 9. En HTTPS también se usa

Cuando entras a una web segura:

1. Se usa criptografía asimétrica para intercambiar claves
2. Luego se usa simétrica para cifrar la sesión

¿Por qué?

Porque es mucho más rápida.

---

# 10. Truco para Recordar

`Simétrica = Misma clave`

- Rápida = Sí
- Segura = Sí
- Problema = Compartir clave

---

# 11. Comparación rápida

| Característica | Simétrica |
|--------------|----------|
| Número de claves | 1 |
| Velocidad | Alta |
| Uso principal | Cifrado de datos |
| Escalabilidad | Media |
| Ejemplo | AES |

---

# 12. Aplicación en Ciberseguridad

Se utiliza para:

- Cifrar discos duros
- Proteger backups
- VPN corporativas
- Archivos sensibles
- Bases de datos
- Comunicaciones internas

---

# 13. Errores Comunes

## Pensar que antigua = mala

No. Sigue siendo fundamental.

## Pensar que AES y RSA compiten

No. Se complementan.

## Guardar mal la clave

El algoritmo puede ser fuerte, pero si roban la clave no sirve.

---

# 14. Para Examen Memoriza

- Usa 1 clave
- Misma clave cifra y descifra
- Muy rápida
- Problema principal: intercambio seguro
- Algoritmo más importante: AES

---

# Conclusión

La criptografía simétrica es uno de los pilares de la seguridad moderna. Su velocidad y eficiencia la convierten en la opción ideal para proteger grandes cantidades de información.

Aunque tiene el reto de compartir la clave de forma segura, sigue siendo esencial en redes, sistemas y aplicaciones actuales.
