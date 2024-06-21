# beginners_rsa
### 136pt Beginner

Do you know RSA?

[Archivo](../files/cry-beginners-rsa.zip) 

# Solución

El código realiza el descifrado de un mensaje cifrado con RSA utilizando un módulo \( n \) que es el producto de cinco números primos distintos. Las variables \( p, q, r, s, \) y \( a \) almacenan estos primos, y \( n \) es calculado a partir de ellos. Se usa el exponente público estándar \( e = 65537 \) y un mensaje cifrado específico \( enc \). Se calcula el exponente de descifrado \( d \) a partir de \( \phi(n) \), que es el producto de \((p-1)(q-1)(r-1)(s-1)(a-1)\). Finalmente, se descifra el mensaje \( enc \) usando \( d \) y se convierte de vuelta a formato de texto usando \( long_to_bytes \).

- Factorizar n con [Factordb](http://www.factordb.com/) 

```
from Crypto.Util.number import getPrime, bytes_to_long, long_to_bytes, inverse

# Generación de primos y cálculo de n 
p = 9953162929836910171
q = 11771834931016130837
r = 12109985960354612149
s = 13079524394617385153
a = 17129880600534041513

n = 317903423385943473062528814030345176720578295695512495346444822768171649361480819163749494400347
e = 65537
enc = 127075137729897107295787718796341877071536678034322988535029776806418266591167534816788125330265

# Calcula phi(n)
phi_n = (p-1) * (q-1) * (r-1) * (s-1) * (a-1)

# Calcula el exponente privado d
d = inverse(e, phi_n)

# Descifra el mensaje
decrypted = pow(enc, d, n)

# Convierte el número a bytes para obtener el mensaje original
flag = long_to_bytes(decrypted)
print(flag)
```

### FLAG{S0_3a5y_1254!!}
