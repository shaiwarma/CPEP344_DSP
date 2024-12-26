Name			: SHAIRA SENDAD

Course and Year	: BSCPE - 4



I.	OBJECTIVES:


In this laboratory exercise, the students are expected to:

•	obtain Linear Convolution of two finite length sequences


II.	MATERIALS:


•	Software: MATLAB


III.	PROCEDURES:


THEORY: 

Convolution is a mathematical operation used to express the relation between 

input and output of an LTI system. It relates input, output and impulse response of an LTI system as 


y(n)=x(n)∗h(n)


Where y (n) = output of LTI 


x (n) = input of LTI 


h (n) = impulse response of LTI 


Discrete Convolution 


y(n)=x(n)∗h(n)


= ![image](https://github.com/user-attachments/assets/2e2d705c-1d5c-4bb1-8902-90335f4afb56)




By using convolution we can find zero state response of the system. 


Algorithm: 

Step I: Give input sequence x[n]. 

Step II: Give impulse response sequence h(n) 

Step III: Find the convolution y[n] using the matlab command conv.

Step IV: Plot x[n],h[n],y[n]


![image](https://github.com/user-attachments/assets/6bb30e41-c6e3-41e4-b143-a3972438d2c0)


 

PROGRAM: 

clc; 

clear all; 

close all; 

x1=input('Enter the first sequence x1(n) = '); 

x2=input('Enter the second sequence x2(n) = '); 

L=length(x1); 

M=length(x2); 

N=L+M-1; 

yn=conv(x1,x2); 

disp(‘The values of yn are= ‘); 

disp(yn); 


n1=0:L-1; 

subplot(311); 

stem(n1,x1); 

grid on; 

xlabel('n1--->'); 

ylabel('amplitude--->'); 

title('First sequence'); 



n2=0:M-1; 

subplot(312); 

stem(n2,x2); 

grid on; 

xlabel('n2--->'); 

ylabel('amplitude--->');

title('Second sequence'); 


n3=0:N-1; 

subplot(313); 

stem(n3,yn); 

grid on; 

xlabel('n3--->'); 

ylabel('amplitude--->'); 

title('Convolved output'); 



Output: 

Enter the first sequence x1(n) = [1 2 3 4 5] 

Enter the second sequence x2(n) = [5 8 3 5 4 6] 

The values of yn are= 


5	18	34	55	80	81	59	59	44	30


OUTPUT WAVEFORMS:

![image](https://github.com/user-attachments/assets/ccc13f07-53f7-4aa3-9cf6-c9e0193595d2)


 

RESULT:
