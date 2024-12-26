Name			: SHAIRA SENDAD

Course and Year	:





I.	OBJECTIVES:


In this laboratory exercise, the students are expected to:

•	compute auto correlation between two sequences

II.	MATERIALS:


•	Software: MATLAB



III.	PROCEDURES:


THEORY: 


Auto Correlation Function 

Auto correlation function is a measure of similarity between a signal & its time delayed version. It is represented with R(k). 

The auto correlation function of x(n) is given by 


R11(k)=R(k)= ![image](https://github.com/user-attachments/assets/32cc254b-0fce-455b-859b-705c666c8e42)




Algorithm: 

Step I : Give input sequence x[n]. 


Step II : Give impulse response sequence h (n) 

Step III: Find auto correlation using the matlab command xcorr. 

Step IV: Plot x[n], h[n], z[n]. 

Step V: Display the results



Flow Chart: 

![image](https://github.com/user-attachments/assets/f41b607c-fbb3-47cf-a362-3a70b4e3a2df)

 

PROGRAM: 

clc; 

close all; 

clear all; 

% two input sequences 

x=input('enter input sequence') 

subplot(1,2,1); 

stem(x); 

xlabel('n'); 

ylabel('x(n)'); 

title('input sequence'); 

% auto correlation of input sequence 

z=xcorr(x,x); 

disp(‘The values of z are = ‘);disp(z); 

subplot(1,2,2); 

stem(z); 

xlabel('n'); 

ylabel('z(n)'); 

title('auto correlation of input sequence'); 



Output: 



enter input sequence [1 2 3 4]

z = [3.99, 11, 20, 30, 20, 11, 3.99]



OUTPUT WAVEFORMS:

![image](https://github.com/user-attachments/assets/162a2808-359f-4843-bc86-c8b46796e9f9)

 
RESULT: 

VIVA QUESTIONS:

1. Write the mathematical formula to find auto-correlation? 
   The formula for auto-correlation is:  
   Rxx[k] = Σ x[n] * x[n-k],  
   where x[n] is the signal and k is the lag.

2. Define auto-correlation?*
   Auto-correlation measures how similar a signal is to a delayed version of itself. It helps find repeating patterns or periodicities in the signal.

3. Define correlation.
   Correlation measures the similarity between two signals or sequences, showing how one signal relates to another in terms of shape and timing.

4. What is the difference between auto-correlation and convolution?
   Auto-correlation compares a signal with itself to find patterns, while convolution combines two signals to find their interaction or system response.

5. What is the difference between auto-correlation and cross-correlation?
   Auto-correlation compares a signal with itself, while cross-correlation compares two different signals to measure their similarity.

6. Write the mathematical formula to find cross-correlation?
   The formula for cross-correlation is:  
   Rxy[k] = Σ x[n] * y[n-k],  
   where x[n] and y[n] are the two signals being compared.

7. What is the length of the resultant sequence of auto-correlation?
   The length of the auto-correlation result is 2N - 1, where N is the length of the original signal.

8. List a few applications of correlation.
   - Signal detection and synchronization  
   - Pattern recognition in images and audio  
   - Speech and audio analysis  
   - Finding time delays between signals  

9. Give the properties of auto-correlation.
   - Symmetry: Rxx[k] = Rxx[-k]  
   - Maximum value occurs at zero lag: Rxx[0] ≥ Rxx[k] for all k  
   - Energy property: Rxx[0] represents the total energy of the signal  

10. Define cross-correlation?
    Cross-correlation measures the similarity between two signals as one is shifted in time relative to the other. It helps find time lags and align signals.

