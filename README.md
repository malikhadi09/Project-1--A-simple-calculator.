# Project-2--A-simple-calculator.
A simple calculator made using Assembly Language.





# CONTENT OF PROJECT REPORT:

1.	Objective
2.	Theory
3.	Implementation
4.	Debugging test-run


# Objective:

The objective of our project is to implement a 16-bit calculator that would perform following arithmetic and trigonometric operations.

1-Addition
2-Subtraction
3-Multiplication
4-Divison
5-Square
6-Cube
7-Factorial
8-Power
9-Trigonometry.


# Theory:

An electronic calculator is typically a portable electronic device usead to perform calculations, ranging from basic arithmetic to complex mathematics. A calculator is a device that performs arithmetic operations on numbers. calculators can do only addition, subtraction, multiplication, and division which is basic.

In this project we have computed the assembly language code (8086) to do the basic functions, I have simulated the programmed in emulator software. This is a microprocessor emulator with an integrated 8086 Assembler. The emulator can run programs on a Virtual Machine, and emulate real hardware including screen, memory, and input and output devices. It helps you program in assembly language. The source code is compiled by assembler and then executed on Emulator step-by-step, allowing you to watch registers, flags and memory while your program runs.

The code we made acts like a 16 bits calculator that would perform arithmetic and trigonometric operations (Addition (+), Subtraction (-), Multiplication (*), Division (/), Square (^2), Cube (^3), Factorial (!), Power (^), Trigonometry (Sin, Cos, Tan)). This calculator can perform 16 bits arithmetic and trigonometric operations. As our calculator acts like a 16 bits calculator so it has a range from 0-65535. We can enter any number in this range. If we enter a number having range above it would hit an error.
In our calculator when we run, it displays a menu that asks us to enter a choice from (1-9).
If we enter 1, we will be able to perform addition operation.
If we enter 2, we will be able to perform multiplication operation.
If we enter 3, we will be able to perform subtraction operation.
If we enter 4, we will be able to perform division operation.
If we enter 5, we will be able to perform square operation.
If we enter 6, we will be able to perform cube operation.
If we enter 7, we will be able to perform factorial operation.
If we enter 8, we will be able to perform power operation.
If we enter 9, we will be able to perform trigonometric operation.

After selecting one of our choices, we will get to that operation, and it will ask the user to enter numbers. There are two numbers that must be entered.
It will ask the user to please enter the first number and then the second number after entering that we will get the result of that operation that we chose.

# Addition operation:

If we enter 1, we will be able to perform addition operation. Then the compiler will ask to enter the first number after entering the first number it will ask the user to enter the second number after that we will simply get our result of addition.

# Multiplication operation:

If we enter 2, we will be able to perform Multiplication operation. Then the compiler will ask to enter the first number after entering the first number it will ask the user to enter the second number after that we will simply get our result of multiplication.

# Subtraction operation:

If we enter 3, we will be able to perform subtraction operation. Then the compiler will ask to enter the first number after entering the first number it will ask the user to enter the second number after that we will simply get our result of subtraction.

# Division operation:

If we enter 4, we will be able to perform division operation. Then the compiler will ask to enter the first number after entering the first number it will ask the user to enter the second number after that we will simply get our result of division.

# Square operation:

If we enter 5, we will be able to perform square operation. Then the compiler will ask to enter the number after entering that we will simply get our result of Square.

# Cube operation:

If we enter 6, we will be able to perform cube operation. Then the compiler will ask to enter the number after entering that we will simply get our result of cube.

# Factorial operation:

If we enter 7, we will be able to perform factorial operation. Then the compiler will ask to enter the number after entering that we will simply get our result of addition.

# Power operation:

If we enter 8, we will be able to perform power operation. Then the compiler will ask to enter the power of base after entering the power of base it will ask to enter the base number after entering that we will simply get our result of power operation.

# Trigonometric operation:

If we enter 9, menu will appear and there will be three choices.
1-Sin theta
2-Cos theta
3-Tan theta
If we enter 1, we will be able to perform sin theta, if we enter 2, we will be able to perform cos theta and similarly if we enter 3, we will be able to perform tan theta.

# Sin theta:

After entering the choice, the compiler will ask the user to enter the value of perpendicular after entering the value of perpendicular it will ask the user to enter the value of hypotenuse after entering these values, we will get our answer of sin theta.

# Cos theta:

After entering the choice, the compiler will ask the user to enter the value of base after entering the value of base it will ask the user to enter the value of hypotenuse after entering these values, we will get our answer of cos theta.

# Tan theta:

After entering the choice, the compiler will ask the user to enter the value of perpendicular after entering the value of perpendicular it will ask the user to enter the value of base after entering these values, we will get our answer of tan theta.


# FLOW CHART OF OUR CALCULATOR:


![123](https://user-images.githubusercontent.com/92660593/193567090-d7fd5525-0119-4b38-98ed-7e0ac34908f6.PNG)



# IMPLEMENTATION:

;NAME :MALIK ABDUL HADI

include emu8086.inc
org 100h

.DATA

num1 dw ?
num2 dw ?
result dw ?
temp dw ?
perpendicular dw ?
hypotenuse dw ?
base dw ?


MAIN PROC

 .CODE

 jmp start  
    
  hey:    db      0dh,0ah,0Dh,0Ah,0Dh,0Ah,0dh,"*********************** A SIMPLE CALCULATOR *********************** ",0Dh,0Ah,0Dh,0Ah,0Dh, '$'
 Introduction1:  db  0Dh,0Ah, "GROUP MEMBERS:",0Dh,0Ah,0Dh,0Ah, "MALIK ABDUL HADI(200901053) ",0Dh,0Ah,"M.SAAD BIN SHAFIQ (200901079) " ,0Dh,0Ah,0Dh,0Ah,0Dh,0Ah,'$'
 Introduction2:  db 0Dh,0Ah,0Dh,0Ah,  "WELCOME TO OUR CALCULATOR: ",0Dh,0Ah,0Dh,0Ah,'$' 
 outlining:      db                    "________________________ ",0Dh,0Ah,0Dh,0Ah,'$'
 Option1:    db      0dh,0ah,"1 for Addition",0dh,0ah,"2 for Multiplication",0dh,0ah,"3 for Subtraction",0dh,0ah,"4 for Division", 0Dh,0Ah,"5 for taking Square",0Dh,0Ah,"6 for taking Cube",0Dh,0Ah,"7 for taking Factorial",0Dh,0Ah,"8 for taking Power of a number",0Dh,0Ah,"9 for Trigonometry ",0Dh,0Ah,'$'
 choice1:    db     0dh,0ah, "Please, enter your choice: ", 0Dh,0Ah, '$'
 choice2:    db     0dh,0ah, "You have selected Addtion: ", 0Dh,0Ah, '$'
 choice3:    db     0dh,0ah, "You have selected Multiplication: ", 0Dh,0Ah, '$'
 choice4:    db     0dh,0ah, "You have selected Subtraction: ", 0Dh,0Ah, '$'
 choice5:    db     0dh,0ah, "You have selected Division: ", 0Dh,0Ah, '$'
 choice6:    db     0dh,0ah, "You have selected Square: ", 0Dh,0Ah, '$'
 choice7:    db     0dh,0ah, "You have selected Cube: ", 0Dh,0Ah, '$'   
 choice8:    db     0dh,0ah, "You have selected Factorial: ", 0Dh,0Ah, '$'   
 choice9:    db     0dh,0ah, "You have selected Power of a number: ", 0Dh,0Ah, '$'
 choice10:    db     0dh,0ah, "You have selected Trigonometry: ", 0Dh,0Ah, '$'

 start:  
 

        
         mov ah,9
         mov dx, offset hey 
         int 21h
         
         mov ah,9
         mov dx, offset Introduction1 
         int 21h 
        
         mov ah,9
         mov dx, offset Introduction2 
         int 21h 
        
         mov ah,9
         mov dx, offset outlining 
         int 21h 
        
       
        
         mov ah,9
         mov dx, offset Option1 
         int 21h
        
        
         mov ah,9
         mov dx, offset choice1 
         int 21h
         mov ah,0                       
         int 16h
       
        cmp al,31h 
        je Addition
          
        cmp al,32h
        je Multiplication
         
         
        cmp al,33h
        je Subtraction 
        
        cmp al,34h
        je Division  
        
        cmp al,35h
        je Square
        
        cmp al,36h
        je Cube 
        
        cmp al,37h
        je Factorial   
        
        cmp al,38h
        je Power
        
        cmp al,39h
        je Trigonomtery 
        
        
        
        
        jmp start
        
        
        
 Addition:  
           
           
           mov ah,9
           mov dx, offset choice2 
           int 21h
           
           print "Please enter the first number: "
           
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           
          print "Please enter the second number: " 
          
            
           call scan_num
           print 10
           print 13
           mov num2,cx
           mov bx,num2
           add ax,bx
           mov result,ax
           
           print "So Addition of two numbers is: " 
         
           call print_num 
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))" 
                                
           ret
           hlt
            
           
 Multiplication:
  
           
           
           mov ah,9
           mov dx, offset choice3 
           int 21h
           
           print "Please enter the first number: "
           
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           
          print "Please enter the second number: " 
          
            
           call scan_num
           print 10
           print 13
           mov num2,cx
           mov bx,num2
           mul bx
           mov result,bx
           
           print "So Multiplication of two numbers is: "
         
           call print_num 
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt
                                   
                     
           
 
 Subtraction:  
           
           
           mov ah,9
           mov dx, offset choice4 
           int 21h
           
           print "Please enter the first number: "
           
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           
          print "Please enter the second number: " 
          
            
           call scan_num
           print 10
           print 13
           mov num2,cx
           mov bx,num2
           SUB ax,bx
           mov result,ax
           
           print "So Subtraction of two numbers is: "  

           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))" 
           ret
           hlt
                                
           
 Division:  
           
           
           mov ah,9
           mov dx, offset choice5 
           int 21h
           
           print "Please enter the first number: "
           
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           
          print "Please enter the second number: " 
          
            
           call scan_num
           print 10
           print 13 
           
           mov num2,cx
           mov bx,num2 
           xor dx, dx
           div bx
           mov result,bx
           
           print "So Division of two numbers is: "
               
           
            
           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt
 Square:
           
          
           mov ah,9
           mov dx, offset choice6 
           int 21h
           
           print "Please enter the number: "
           
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           
           mul ax

           
           print "So Square of the number is: " 
            
           
            
           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt  
           
  Cube:
            
           mov ah,9
           mov dx, offset choice7 
           int 21h
           
           print "Please enter the number: "     
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1 
           mov bx,ax  
           mul ax
           mul bx   
           
           print "So Cube of the number is: "  
           
           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt  
 
 Factorial:
           mov ah,9
           mov dx, offset choice8 
           int 21h
           
           print "Please enter the number: " 
           
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov ax,num1  
           mov cx,ax
           dec cx
           
           l2:
           mul cx
           loop l2
           
           print "So Factorial of the number is: "  
           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt 
 
 Power:
           mov ah,9
           mov dx, offset choice9 
           int 21h 
           
           print "Please enter the Power of Base: "
        
           call scan_num
           print 10
           print 13
           mov num1,cx
           mov dx,num1
           
           print "Now enter the Base: "
        
           call scan_num
           print 10
           print 13
           mov num2,cx
           mov bx,num2
           mov ax,1h 
           mov cx,dx 
           l3:
           mul bx
           loop l3
           
            print "So Power of the number(base) is: "  
           call print_num
           print 10
           print 13
           print 10
           print 13
           
           print "Thanks for using our calculator :)))"
           ret
           hlt
           
Trigonomtery:

mov ah,9
mov dx, offset choice10 
int 21h
print 10
print 13
print 10
print 13
print "Menu :"
print 10
print 13 
print "______"
print 10
print 13
print 10
print 13
print "1- Sin theta"
print 10
print 13
print 10
print 13
print "2- Cos theta" 
print 10
print 13
print 10
print 13
print "3- Tan theta"
print 10
print 13
print 10
print 13

mov ah,9
mov dx, offset choice1 
int 21h
mov ah,0                       
int 16h 

cmp al,31h 
je Sin 

cmp al,32h
je Cos

cmp al,33h
je Tan


Sin:

print "You have selected Sin theta: "
print 10
print 13
print 10
print 13
print " Sin theta = Perpendicular/hypotenuse "
print 10
print 13
print 10
print 13
print "Please enter the value of Perpendicular: "
call scan_num
mov perpendicular,cx
mov ax,perpendicular
print 10
print 13
print 10
print 13
print "Please enter the value of hypotenuse: "
call scan_num
mov hypotenuse,cx
mov bx,hypotenuse
print 10
print 13
print 10
print 13
xor dx, dx
div bx
mov result,bx
print "So the answer of Sin theta is : "
call print_num
print 10
print 13
print 10
print 13        
print "Thanks for using our calculator :)))"
ret
hlt 

Cos:

print "You have selected Cos theta: "
print 10
print 13 
print 10
print 13
print " Cos theta = Base/hypotenuse "
print 10
print 13
print 10
print 13
print "Please enter the value of Base: "
call scan_num
mov base,cx
mov ax,base
print 10
print 13
print 10
print 13
print "Please enter the value of hypotenuse: "
call scan_num
mov hypotenuse,cx
mov bx,hypotenuse
print 10
print 13
print 10
print 13
xor dx, dx
div bx
mov result,bx
print "So the answer of Cos theta is : "
call print_num
print 10
print 13
print 10
print 13        
print "Thanks for using our calculator :)))"
ret
hlt 

Tan:

print "You have selected Tan theta: "
print 10
print 13
print 10
print 13
print " Tan theta = Perpendicular/Base "
print 10
print 13
print 10
print 13
print "Please enter the value of Perpendicular: "
call scan_num
mov perpendicular,cx
mov ax,perpendicular
print 10
print 13
print 10
print 13
print "Please enter the value of Base: "
call scan_num
mov base,cx
mov bx,base
print 10
print 13
print 10
print 13
xor dx, dx
div bx
mov result,bx
print "So the answer of Tan theta is : "
call print_num
print 10
print 13
print 10
print 13        
print "Thanks for using our calculator :)))"
ret
hlt 
       
 DEFINE_SCAN_NUM
 DEFINE_PRINT_NUM
 DEFINE_PRINT_NUM_UNS           

ENDP
 END MAIN




















# Debugging test-run:


 ![6](https://user-images.githubusercontent.com/92660593/193567663-e10a9729-3531-4613-9a0d-1db4a3f245ca.PNG)
![1](https://user-images.githubusercontent.com/92660593/193567666-2cfd32c6-ca65-4024-964e-d89aeb0e951b.PNG)
![2](https://user-images.githubusercontent.com/92660593/193567670-615235aa-b4aa-4274-b139-993774126cff.PNG)
![3](https://user-images.githubusercontent.com/92660593/193567672-695d27cd-9ada-446e-93de-a91dec957971.PNG)
![4](https://user-images.githubusercontent.com/92660593/193567675-f035c87f-2c2a-47c1-aa84-a7143984e3af.PNG)
![5](https://user-images.githubusercontent.com/92660593/193567677-39d84243-21ad-46e6-8a77-550d9443fed7.PNG)

         


