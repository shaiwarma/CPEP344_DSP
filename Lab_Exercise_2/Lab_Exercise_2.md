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


-----------------------------------------------------------------------------------------------------------------------------------------------------------------

Output: 

Enter the first sequence x1(n) = [1 2 3 4 5] 

Enter the second sequence x2(n) = [5 8 3 5 4 6] 

The values of yn are= 


5	18	34	55	80	81	59	59	44	30


OUTPUT WAVEFORMS:

![image](https://github.com/user-attachments/assets/ccc13f07-53f7-4aa3-9cf6-c9e0193595d2)


 

RESULT:

VIVA QUESTIONS: 
1. Explain the significance of convolution. 

Convolution helps us understand how a system reacts to an input signal.
It's widely used in signal processing, image processing,
and communication systems to analyze how signals interact with systems.

2. Define linear convolution. 

Linear convolution is a mathematical way to combine two signals, showing how one signal modifies the other. 
It’s like blending two sequences to see their combined effect.

3. Why linear convolution is called as a periodic convolution? 

Actually, linear convolution and periodic convolution are different. 
Periodic convolution happens in systems with repeating signals, like in Fourier series. 
Linear convolution deals with signals that don’t repeat.


4. Why zero padding is used in linear convolution? 

Zero padding is used to ensure the output of convolution matches the desired length. 
It helps in avoiding overlap when signals are being processed.

5. What are the four steps to find linear convolution? 

- Reverse one of the signals.
  
- Shift it relative to the other signal.

- Multiply the overlapping points.

- Sum the results for each shift.
  

6. What is the length of the resultant sequence in linear convolution? 

The length of the output sequence is the sum of the lengths of the two input 
sequences, minus one. For signals of length 𝑀 and 𝑁, the result is 𝑀+𝑁−1.

7. How linear convolution will be used in calculation of LTI system response? 

Linear convolution is key for finding the output of an LTI system. 
By convolving the input signal with the system’s impulse response, 
we can predict how the system will behave.

8. List few applications of linear convolution in LTI system design. 

It's used in signal filtering, system analysis, audio processing, 
image processing, and communication systems to model and design responses.

9. Give the properties of linear convolution. 

![image](https://github.com/user-attachments/assets/a920d27f-0597-4a8b-b0a2-4f786cc160b9)


10. How the linear convolution will be used to calculate the DFT of a signal?

By performing zero padding and using the overlap-save or overlap-add methods, 
linear convolution can be computed efficiently in the frequency domain 
using the Discrete Fourier Transform (DFT).




