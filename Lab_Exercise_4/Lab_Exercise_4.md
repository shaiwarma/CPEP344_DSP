

Name			: SHAIRA SENDAD

Course and Year	: BSCPE-4



---

I. OBJECTIVES:  

In this laboratory exercise, the students are expected to:  
- Find the frequency response of a given system in differential equation form.

---

II. MATERIALS:  

- Software: MATLAB

---

III. PROCEDURES:  

THEORY:  
Systems respond differently to inputs of different frequencies. Some systems amplify components of certain frequencies and attenuate others. The relationship between the system output and input across different frequencies is called the frequency response of the system.

Amplitude Response: For each frequency, the magnitude indicates how much the system amplifies or attenuates the input signal.  

![image](https://github.com/user-attachments/assets/00e54c19-9ba9-4551-92ac-9ca9159cba8c)

Phase Response: The phase indicates how the system shifts the phase of input sinusoids. 

![image](https://github.com/user-attachments/assets/cc5aa798-948e-4998-a4d5-9a11642cec09)

The phase response, or its derivative (group delay), shows how the system delays the input signal depending on the frequency.

Given Difference Equation:  

![image](https://github.com/user-attachments/assets/ca669cb3-49ca-4105-93e8-44ba53367897)


---

Algorithm:  

1. Input the numerator coefficients of the given transfer function or difference equation.  
2. Input the denominator coefficients of the given transfer function or difference equation.  
3. Use the MATLAB command freqz to find the frequency response.  
4. Compute magnitude and phase responses using MATLAB commands abs and angle.  
5. Plot the magnitude and phase responses.

---

Flow Chart:  

![image](https://github.com/user-attachments/assets/f1a60684-2be0-4a83-bf88-7de668317a0c)


---

PROGRAM:  

```matlab
% MATLAB program to plot the frequency response (magnitude and phase response) of a given difference equation. 
clc; 
clear all; 
b = input('Enter the numerator coefficients:'); 
a = input('Enter the denominator coefficients:'); 
[h, w] = freqz(b, a); 
subplot(2, 1, 1); 
plot(w / pi, abs(h)); 
grid; 
xlabel('Normalized Frequency'); 
ylabel('Magnitude in dB'); 
title('Magnitude Response'); 
subplot(2, 1, 2); 
plot(w / pi, angle(h)); 
grid; 
xlabel('Normalized Frequency'); 
ylabel('Phase in radians'); 
title('Phase Response');
```

---

OUTPUT:  

Input:  
Enter the numerator coefficients: [1]  
Enter the denominator coefficients: [1 -1/6 -1/6]

Output Waveforms:  
![image](https://github.com/user-attachments/assets/e192f81f-66d7-4cdf-8305-91ef0c0ea90c)


---

RESULT:  
VIVA QUESTIONS:

1. Define frequency response  
Frequency response shows how a system reacts to input signals of varying frequencies. It determines how the amplitude and phase of each frequency component are modified by the system.

2. Define magnitude response  
Magnitude response indicates how much a system amplifies or attenuates an input signal for a given frequency.

3. Define phase response  
Phase response describes how the system shifts the phase of the input signal for each frequency.

4. Define transfer function  
A transfer function is a mathematical representation of the relationship between the input and output of a system in the frequency domain. It is typically expressed as a ratio of polynomials in the Laplace or z-domain.

5. State the significance of difference equations  
Difference equations are used to represent discrete-time systems. They model the relationship between input and output signals and are key to analyzing and designing digital systems.

6. What are the classifications of systems based on unit sample response  
- Causal systems: Response depends only on present and past inputs  
- Stable systems: Response does not diverge over time  
- Linear systems: Follows superposition and scaling properties  
- Time-invariant systems: Behavior does not change over time

7. What is zero input response  
Zero input response is the output of a system due to its initial conditions alone, with no external input applied.

8. Define impulse response  
Impulse response is the output of a system when the input is a unit impulse. It fully characterizes a linear time-invariant system.

9. Define system  
A system is an entity that processes input signals to produce output signals based on a specific set of rules or operations.

10. Write the mathematical formula to find the response of any given system  
The response y of a system can be calculated as the sum of the impulse response values multiplied by the corresponding input signal values.
