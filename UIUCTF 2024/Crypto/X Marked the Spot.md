# X Marked the Spot

A perfect first challenge for beginners. Who said pirates can't ride trains...

[Files](../files)

# Solution

To decrypt the 'ct' file, the script uses the known flag structure uiuctf{}. It reads the ciphertext, finds key fragments by XORing known parts of the plaintext with the ciphertext, and iterates through possible middle key values. If the decrypted text matches the flag format, it prints the key and flag. Here’s the script:

```python
from itertools import cycle

# Leer el archivo cifrado 'ct'
with open('ct', 'rb') as f:
    ct = f.read()

# Suponiendo que ya sabemos la estructura de la flag y parte del texto plano (uiuctf{})
known_plaintext_start = b'uiuctf{'
known_plaintext_end = b'}'
key_length = 8

# Encontrar la clave usando el texto conocido
key_start = bytes(ct[i] ^ known_plaintext_start[i] for i in range(len(known_plaintext_start)))
key_end = bytes(ct[-1] ^ known_plaintext_end[-1])

# Ahora buscamos la clave completa
for i in range(256):
    key_middle = key_start + bytes([i]) + key_end
    key = (key_middle * (key_length // len(key_middle) + 1))[:key_length]
    flag = bytes(x ^ y for x, y in zip(ct, cycle(key)))

    if flag.endswith(b'}') and flag.startswith(b'uiuctf{'):
        print("Clave encontrada:", key)
        print("Flag descifrada:", flag.decode())
        break
```

# uiuctf{n0t_ju5t_th3_st4rt_but_4l50_th3_3nd!!!!!}
