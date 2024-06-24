# beginners_aes
### 142pt Beginner

AES is one of the most important encryption methods in our daily lives.

[Archivo](../files/cry-beginners-aes.zip)

# Solución
El script realiza un ataque de fuerza bruta para descifrar un mensaje cifrado con AES en modo CBC, probando todas las combinaciones posibles para el último byte de la clave y el vector de inicialización (IV) basados en valores base. Para cada combinación, intenta descifrar el mensaje, eliminar el padding y verifica si el contenido descifrado coincide con el formato esperado de una bandera de CTF. Este también comprueba si el hash SHA-256 del mensaje descifrado coincide con algún hash, donde podemos confirmar que la bandera descifrada sea la correcta. Si se encuentra una combinación válida, el script imprime la bandera; de lo contrario, termina sin encontrarla.

```python
from Crypto.Util.Padding import unpad
from Crypto.Cipher import AES
import hashlib

# Datos proporcionados
enc = b'\x16\x97,\xa7\xfb_\xf3\x15.\x87jKRaF&"\xb6\xc4x\xf4.K\xd77j\xe5MLI_y\xd96\xf1$\xc5\xa3\x03\x990Q^\xc0\x17M2\x18'
flag_hash = '6a96111d69e015a07e96dcd141d31e7fc81c4420dbbef75aef5201809093210e'

# Clave e IV base
base_key = b'the_enc_key_is_'
base_iv = b'my_great_iv_is_'

# Probar todas las combinaciones posibles para el byte adicional
correct_flag = None
for i in range(256):
    key = base_key + bytes([i])
    for j in range(256):
        iv = base_iv + bytes([j])
        cipher = AES.new(key, AES.MODE_CBC, iv)
        try:
            decrypted = unpad(cipher.decrypt(enc), 16)
            if decrypted.startswith(b'FLAG{') and decrypted.endswith(b'}'):
                if hashlib.sha256(decrypted).hexdigest() == flag_hash:
                    correct_flag = decrypted.decode()
                    break
        except ValueError:
            continue
    if correct_flag:
        break

print(f'The correct flag is: {correct_flag}')
```

### FLAG{7h3_f1r57_5t3p_t0_Crypt0!!}
