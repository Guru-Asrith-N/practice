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
