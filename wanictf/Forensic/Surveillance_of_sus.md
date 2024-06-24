# Surveillance_of_sus
### 149pt Normal

A PC is displaying suspicious activity, possibly under the control of a malicious individual.

It appears that a cache file from this PC has been retrieved for investigation.

[Link](../files/for-Surveillance-of-sus.zip)

## Solution

1. Confirm the type of file.
2. According to the description, it is indicated that this is a PC cache file which was recovered for investigation purposes.
3. Drawing from previous CTF experience, I recalled a repository [bmc-tools](https://github.com/ANSSI-FR/bmc-tools/blob/master/bmc-tools.py) that assists in analyzing RDP bitmap cache.

4. We used the Python code to extract data:

<p align="center">
  <img src="../../Imagenes/yySkFFQ4w7.png" width="300" alt="Execution">
</p>

   Here, the `-s` parameter specifies the location of the .bin file, and `-d` indicates where the extracted information will be stored.

5. After waiting a few minutes, we obtained a large number of bmp files, which are images or snippets of images. Further investigating, we found the application [RdpCacheStitcher](https://github.com/BSI-Bund/RdpCacheStitcher/blob/main/README.md) useful for piecing these images together like a puzzle.
   
<p align="center">
  <img src="../../Imagenes/6p2AQ7bTLp.png" width="400" alt="Extracted Images">
</p>

7. We found the flag.

<p align="center">
  <img src="../../Imagenes/msrWYbN7fS.png" width="500" alt="Flag">
</p>

### FLAG{RDP_is_useful_yipeee}

