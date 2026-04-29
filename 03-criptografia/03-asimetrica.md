# Criptografía Asimétrica

## Introducción

La **criptografía asimétrica** es un sistema de cifrado que utiliza **dos claves diferentes pero relacionadas matemáticamente**:

- **Clave pública**
- **Clave privada**

Una clave se utiliza para cifrar o verificar, y la otra para descifrar o firmar.

Es uno de los pilares de la seguridad moderna en Internet.

---

# 1. ¿Cómo funciona?

Cada usuario posee un par de claves:

- **Clave pública** → puede compartirse libremente.
- **Clave privada** → debe mantenerse secreta.

## Proceso básico

Si alguien quiere enviarte información segura:

1. Usa tu **clave pública** para cifrar el mensaje.
2. Solo tu **clave privada** podrá descifrarlo.

Proceso:

Texto plano → Cifrado con clave pública → Texto cifrado  
Texto cifrado → Descifrado con clave privada → Texto original

---

# 2. ¿Por qué se llama asimétrica?

Porque las claves son distintas:

- Una clave cifra
- Otra clave descifra

No se usa la misma clave en ambos procesos.

---

# 3. Ventajas

## Intercambio seguro

No hace falta compartir una clave secreta previa.

## Escalable

Ideal para muchos usuarios en Internet.

## Firmas digitales

Permite verificar identidad y autoría.

## Muy útil en redes abiertas

Perfecta para comunicaciones donde no existe confianza previa.

---

# 4. Desventajas

## Más lenta

Es bastante más lenta que la criptografía simétrica.

## Mayor consumo de recursos

Requiere más procesamiento.

## No ideal para grandes volúmenes

Por eso normalmente se usa junto con criptografía simétrica.

---

# 5. Ejemplo sencillo

Ana quiere recibir mensajes seguros.

Ana genera:

- Clave pública: la comparte
- Clave privada: la guarda

Carlos quiere enviar:

`HOLA ANA`

Carlos cifra el mensaje con la clave pública de Ana.

Solo Ana podrá leerlo usando su clave privada.

---

# 6. Algoritmos Asimétricos Importantes

## RSA

Uno de los más conocidos.

Usado en:

- HTTPS
- Certificados digitales
- Firma digital
- Intercambio de claves

## ECC (Elliptic Curve Cryptography)

Más moderno y eficiente.

Usado en:

- Smartphones
- TLS moderno
- Blockchain
- Dispositivos pequeños

## DSA / ElGamal

Usados en contextos específicos.

---

# 7. Uso real en HTTPS

Cuando entras a una web segura:

1. El navegador obtiene la clave pública del servidor.
2. Verifica el certificado digital.
3. Intercambia una clave de sesión segura.
4. Después se usa criptografía simétrica.

¿Por qué?

Porque asimétrica inicia la seguridad, simétrica mantiene velocidad.

---

# 8. Firma Digital

También sirve para demostrar identidad.

## Proceso

1. El emisor firma con su clave privada.
2. Otros verifican con su clave pública.

Esto permite:

- Saber quién envió el mensaje
- Detectar modificaciones
- No repudio

---

# 9. Truco para Recordar

`Pública = Compartir`

`Privada = Guardar`

`Cifrar con pública`

`Descifrar con privada`

Para firmas:

`Firmar con privada`

`Verificar con pública`

---

# 10. Comparación rápida

| Característica | Asimétrica |
|--------------|-----------|
| Número de claves | 2 |
| Velocidad | Baja |
| Uso principal | Intercambio seguro |
| Escalabilidad | Alta |
| Ejemplo | RSA |

---

# 11. Aplicación en Ciberseguridad

Se utiliza para:

- HTTPS
- Certificados SSL/TLS
- Firmas digitales
- VPN
- Correos seguros
- Tokens
- Autenticación avanzada

---

# 12. Errores Comunes

## Pensar que reemplaza la simétrica

No. Se complementan.

## Compartir la clave privada

Nunca debe compartirse.

## Pensar que pública = insegura

Puede compartirse sin problema.

---

# 13. Para Examen Memoriza

- Usa 2 claves
- Pública se comparte
- Privada se protege
- Más lenta que simétrica
- Ideal para Internet
- Ejemplo principal: RSA

---

# 14. Simétrica vs Asimétrica

| Característica | Simétrica | Asimétrica |
|--------------|----------|-----------|
| Claves | 1 | 2 |
| Velocidad | Alta | Baja |
| Uso | Datos | Intercambio |
| Ejemplo | AES | RSA |

---

# Conclusión

La criptografía asimétrica revolucionó la seguridad digital al permitir comunicaciones seguras sin compartir previamente una clave secreta.

Es esencial en Internet moderno, certificados digitales, autenticación y firmas electrónicas.
