# cryptography

## Cryptohack 

#### Finding Flags 

the flag was directly given so directly entered the flag     

```   
Flag - crypto{y0ur_f1rst_fl4g}   
```  

#### Great snakes   

the python file was already given   
so opened python file and ran the program   
```
Flag - crypto{z3n_0f_pyth0n}
```

#### ASCII  

wrote the following code to convert numbers to ASCII
```
a= [99, 114, 121, 112, 116, 111, 123, 65, 83, 67, 73, 73, 95, 112, 114, 49, 110>

for i in a:
        print(chr(i))
```

```
Flag - crypto{ASCII_pr1nt4bl3}
```

#### Hex 

wrote the following code to convert hex to bytes 
```
a= 63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f64685f6865785f737472696e67735f615f6c6f747d

b= bytes.fromhex(a)
print (b) 
```
keeps showing this error
```
File "/tmp/1/1.py", line 1
    a= 63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d
                 ^
SyntaxError: invalid decimal literal
```
tried changing the syntax but the same error continued   
so went back to reading python syntax to see if i made any mistakes

-----------------------------
made a mistake   
had to put the hex numbers within single quotes and make it into string then it runs  
```
Flag - crypto{You_will_be_working_with_dh_hex_strings_a_lot}
```

#### Base64 

entered the following code  
```
import base64 

a='72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf'
b=bytes.fromhex(a)
c= base64.b64encode(b)
print (c)
```

```
Flag -crypto/Base+64+Encoding+is+Web+Safe/
```

#### Bytes and big integers 

entered the following code 
```
from Crypto.Util.number import *

a=11515195063862318899931685488813747395775516287289682636499965282714637259206259206269
b=long_to_bytes(a)
print (b)
```
long_to_bytes and bytes_to_long don't work for strings   
```
Flag - crypto{3nc0d1n6_4ll_7h3_w4y_d0wn}
```


## picoCTF  

#### Caesar 

since caesar cipher limitations are small brute forced it 
the key is 22 
```
Flag - picoCTF{crossingtherubiconvfhsjkou}
```

#### No padding , No problem 

opened the challenge  
connected to given port   
showed 
```
Welcome to the Padding Oracle Challenge
This oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Good Luck!


n: 89069710841345853795772415309332012744575923744891171364171461800906667485153976314005224040328628152113894525261595709590938239427547522715759086193724129801642829315222288876639794266842655868837371340503722755387394597421081009403637374071777134992116599910372688011836802145204549915901174273329846204461
e: 65537
ciphertext: 40289183432265489491614697329610309753393559176784529956382745761068315983647722307703431535241216208548736771202383748081804882337881600002523517717556929353788739917629769063611134521500588346569398019325273309046802243285552101681889039858439959196781300607085645950667465503838404187081396112989563114817


Give me ciphertext to decrypt:
```

tried entering the same ciphertext but it didnt decode it  
tried entering different numbers and it decoded it  
tried checking what padding was  
found that you add additional bits to meet a certain number of bits for the operations to work  
searched what an oracle was  
found that it is tool that performs random mathematical operations and gives a fixed response   
while reading it found that OAEP(optimal assymetric encryption padding) was used along with RSA  
read about OAEP  
realised that the challenge didn't have OAEP padding since the challenge name is no padding  
searched no padding vulnerabilities and found that you can send data and observe the results leading to loss of confidentiality   
tried searching how this can be used  
didn't get anything   
read writeups https://github.com/Dvd848/CTFs/blob/master/2021_picoCTF/No_Padding_No_Problem.md   
found that unpadded RSA is homomorphic which means that it is possible to use operations on encrypted text directly without having to decrypt it  
so we can make encrypt 2 numbers individually and multiply them and get the same value as multiplying them and encrypting them  
by assuming one of the numbers as 2 and solving for getting m  we can get the decrypted text   
converting the message to text we get the flag    

```
Flag - picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_4005534}
```
