*Codigo en C#*
``` c#
int arr[] = {1,2,3,4,5,6,7,8,9,10};
int sum = 0;

for (int j = 0; j < 10; j++) {
    sum = sum + arr[j];
}
```

*Codigo ensamblador*
``` C++
@1
D=A
@16
M=D     
@2
D=A
@17
M=D    
@3
D=A
@18
M=D      
@4
D=A
@19
M=D       
@5
D=A
@20
M=D        
@6
D=A
@21
M=D    
@7
D=A
@22
M=D        
@8
D=A
@23
M=D      
@9
D=A
@24
M=D       
@10
D=A
@25
M=D      
@0
D=A
@sum
M=D
@0
D=A
@j
M=D
    @j
    D=M
    @10
    D=D-A
    @END_LOOP
    D;JGE 
    @j
    D=M          
    @16
    A=D+A         
    D=M           
    @sum
    M=M+D   
    @j
    M=M+1
    @LOOP_START
    0;JMP
    @END_LOOP
    0;JMP        
```
