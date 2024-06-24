# nc
### 118pt Beginner

Pwn challenges often require connecting to the challenge server using the nc (netcat) command. It's important to learn how to use nc.

You can connect to the challenge server by executing the following command in your shell. Solve the problem at the connection point and obtain the flag.

`nc chal-lz56g6.wanictf.org 9003`

[Link](../files/pwn-nc.zip)

# Solution

1. The connection is made using netcat, and a test is conducted to check what information it retrieves.
  
2. The `.zip` file was downloaded and the file named `main.c` was checked. In it, a section was identified that confirms the response needed to obtain the Flag.

```c
   int main(){
    init();
    int answer;
    printf("15+1=0x");
    scanf("%d", &answer);
    if(answer == 10){
        win();
    }
```

Where the answer should be 10 to obtain the Flag.

<p align="center">
  <img src="../../Imagenes/5ODq3OyeaL.png" width="500" alt="Flag">
</p>

### FLAG{th3_b3ginning_0f_th3_r0ad_to_th3_pwn_p1ay3r}


