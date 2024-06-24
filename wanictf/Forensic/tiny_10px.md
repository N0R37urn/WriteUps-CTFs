# tiny_10px
### 218pt Normal

What a small world!

[Link](../files/for-tiny-10px.zip)

# Solution

1. Initially, I utilized several common tools in steganography and metadata analysis, such as ExifTool, Binwalk, and Steghide. Unfortunately, these tools did not directly reveal any useful information.

2. Since the challenge statement mentioned the word "small," I decided to specifically investigate the dimensions of JPEG images. I found a very informative blog at [cyberhacktics](https://cyberhacktics.com/hiding-information-by-changing-an-images-height/) detailing how information can be hidden by altering the dimensions of an image in the hexadecimal data.

<p align="center">
  <img src="../../Imagenes/QqYQV8zLEx.png" width="600" alt="Explanation">
</p>

3. I used the online tool [Hexed](https://hexed.it/) to examine the hexadecimal data of the image. This analysis allowed me to identify the values corresponding to the dimensions of the image.

<p align="center">
  <img src="../../Imagenes/7gsGgAt0hk.png" width="700" alt="Modification">
</p>

4. With this information obtained, I proceeded to modify the size values in the image header, choosing random values that I thought might help reveal something more.

5. After downloading and viewing the modified image, I noticed some letters appearing throughout the image, which suggested that the flag could be hidden in an altered format.

<p align="center">
  <img src="../../Imagenes/3.jpg" width="500" alt="Image">
</p>

6. With the help of a simple graphic editor like Paint, I managed to rearrange and align the letters to form the expected flag.

<p align="center">
  <img src="../../Imagenes/CBHIA2OEKD.png" width="300" alt="Flag">
</p>

### FLAG{b1g_en0ugh}
