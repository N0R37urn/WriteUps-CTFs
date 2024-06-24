# beginners_aes
### 142pt Beginner

AES is one of the most important encryption methods in our daily lives.

# Solution
The script performs a brute-force attack to decrypt a message encrypted with AES in CBC mode, testing all possible combinations for the last byte of the key and the initialization vector (IV) based on base values. For each combination, it attempts to decrypt the message, remove the padding, and checks if the decrypted content matches the expected format of a CTF flag. It also verifies if the SHA-256 hash of the decrypted message matches any given hash, confirming that the decrypted flag is correct. If a valid combination is found, the script prints the flag; otherwise, it ends without finding it.

```python
from Crypto.Util.Padding import unpad
from Crypto.Cipher import AES
import hashlib

# Provided data
enc = b'\x16\x97,\xa7\xfb_\xf3\x15.\x87jKRaF&"\xb6\xc4x\xf4.K\xd77j\xe5MLI_y\xd96\xf1$\xc5\xa3\x03\x990Q^\xc0\x17M2\x18'
flag_hash = '6a96111d69e015a07e96dcd141d31e7fc81c4420dbbef75aef5201809093210e'

# Base key and IV
base_key = b'the_enc_key_is_'
base_iv = b'my_great_iv_is_'

# Test all possible combinations for the additional byte
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
