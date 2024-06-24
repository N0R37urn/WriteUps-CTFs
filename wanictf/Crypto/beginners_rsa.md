# beginners_rsa
### 136pt Beginner

Do you know RSA?


# Solution

The code decrypts a message encrypted with RSA using a modulus \( n \) which is the product of five distinct prime numbers. The variables \( p, q, r, s, \) and \( a \) store these primes, and \( n \) is calculated from them. The standard public exponent \( e = 65537 \) and a specific encrypted message \( enc \) are used. The decryption exponent \( d \) is calculated from \( \phi(n) \), which is the product of \((p-1)(q-1)(r-1)(s-1)(a-1)\). Finally, the message \( enc \) is decrypted using \( d \) and converted back to text format using \( long_to_bytes \).

- Factorize n with [Factordb](http://www.factordb.com/)

```python
from Crypto.Util.number import getPrime, bytes_to_long, long_to_bytes, inverse

# Prime generation and n calculation
p = 9953162929836910171
q = 11771834931016130837
r = 12109985960354612149
s = 13079524394617385153
a = 17129880600534041513

n = 317903423385943473062528814030345176720578295695512495346444822768171649361480819163749494400347
e = 65537
enc = 127075137729897107295787718796341877071536678034322988535029776806418266591167534816788125330265

# Calculate phi(n)
phi_n = (p-1) * (q-1) * (r-1) * (s-1) * (a-1)

# Calculate the private exponent d
d = inverse(e, phi_n)

# Decrypt the message
decrypted = pow(enc, d, n)

# Convert the number to bytes to get the original message
flag = long_to_bytes(decrypted)
print(flag)
```


### FLAG{S0_3a5y_1254!!}
