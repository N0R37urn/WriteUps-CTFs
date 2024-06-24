# tiny_usb
### 125pt Beginner

What a small USB!

[Archivo](../files/for-tiny-usb.zip)

# Solution

We were given a .iso file (chal_tiny_usb.iso), which is likely a dump of a USB memory where the flag can be found.

1. Confirm the type of file.
2. Use `strings` to search for information that may be useful.

<p align="center">
  <img src="../../Imagenes/wkTeIFO2OK.png" width="500" alt="Initial Steps">
</p>

3. Identify that there is a possible image added to the ISO.
4. Use the `Binwalk` command to extract data from the file.
5. We found an image containing the flag.

<p align="center">
  <img src="../../Imagenes/2FdxLXUSmZ.png" width="500" alt="Flag">
</p>

### FLAG{hey_i_just_bought_a_usb}
