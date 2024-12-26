Name :  SHAIRA SENDAD  
Course and Year :  BSCPE-4  

---

I. OBJECTIVES:  

In this laboratory exercise, the students are expected to:  
• Implement an HP IIR filter for a given sequence.  

---
II. MATERIALS:  

• Software: MATLAB  

---
III. PROCEDURES:  

THEORY:  
IIR filters are digital filters with infinite impulse response. Unlike FIR filters, they have feedback (a recursive part of the filter) and are known as recursive digital filters. For this reason, IIR filters provide a much better frequency response than FIR filters of the same order. Unlike FIR filters, their phase characteristic is not linear, which can cause issues in systems requiring phase linearity. Thus, IIR filters are not preferred in digital signal processing where phase accuracy is critical. Otherwise, when phase linearity is not a priority, IIR filters are an excellent choice.

One issue unique to IIR filters is potential instability, which is not present in FIR filters as they lack feedback. After designing an IIR filter, it is essential to check its stability.

IIR FILTER DESIGN:  
For the given specifications, to design a digital IIR filter, an analog filter (Butterworth or Chebyshev) is designed first. The resultant analog filter is transformed to a digital filter using either the “Bilinear Transformation” or “Impulse Invariant Transformation.”  

---
Algorithm:  
Step I: Enter the passband ripple (rp) and stopband ripple (rs).  
Step II: Enter the passband frequency (wp) and stopband frequency (ws).  
Step III: Get the sampling frequency (fs).  
Step IV: Calculate normalized passband and stopband frequencies w1 and w2, respectively:  
  w1 = 2 * wp / fs  
  w2 = 2 * ws / fs  

Step V: Use the following functions to calculate the filter order:  
- Butterworth filter: [n, wn] = buttord(w1, w2, rp, rs)  
- Chebyshev filter: [n, wn] = cheb1ord(w1, w2, rp, rs)  

Step VI: Design an nth-order digital high-pass Butterworth or Chebyshev filter:  
- Butterworth filter: [b, a] = butter(n, wn, 'high')  
- Chebyshev filter: [b, a] = cheby1(n, 0.5, wn, 'high')  

Step VII: Find the digital frequency response using the ‘freqz()’ function.  
Step VIII: Calculate the magnitude response in decibels (dB):  
  mag = 20 * log10(abs(H))  
Step IX: Plot the magnitude response (magnitude in dB vs. normalized frequency).  
Step X: Calculate the phase response using angle(H).  
Step XI: Plot the phase response (phase in radians vs. normalized frequency in Hz).

---
Flow Chart:  
![image](https://github.com/user-attachments/assets/366f80e9-bd47-48f0-9836-31bf02a35342)

PROGRAM:  
```matlab
clc;  
clear all;  
close all;

disp('Enter the IIR filter design specifications:');  
rp = input('Enter the passband ripple: ');  
rs = input('Enter the stopband ripple: ');  
wp = input('Enter the passband frequency: ');  
ws = input('Enter the stopband frequency: ');  
fs = input('Enter the sampling frequency: ');  

w1 = 2 * wp / fs;  
w2 = 2 * ws / fs;  
[n, wn] = buttord(w1, w2, rp, rs, 's');

disp('Frequency response of IIR HPF is:');  
[b, a] = butter(n, wn, 'high', 's');

w = 0:0.01:pi;  
[h, om] = freqs(b, a, w);  

m = 20 * log10(abs(h));  
an = angle(h);  

figure;
subplot(2, 1, 1); plot(om / pi, m);  
title('Magnitude Response of IIR Filter');  
xlabel('Normalized Frequency');  
ylabel('Gain (dB)');  

subplot(2, 1, 2); plot(om / pi, an);  
title('Phase Response of IIR Filter');  
xlabel('Normalized Frequency');  
ylabel('Phase (radians)');
```
---
 
Input:  
- Passband ripple: 15  
- Stopband ripple: 60  
- Passband frequency: 1500 Hz  
- Stopband frequency: 3000 Hz  
- Sampling frequency: 7000 Hz
  
Expected waveforms: 
![image](https://github.com/user-attachments/assets/c1223349-54e5-4736-bd29-91c0a2d31bc1)

---

VIVA QUESTIONS:  

1. What are the filter specifications required to design analog filters?  
   - Passband ripple (rp)  
   - Stopband ripple (rs)  
   - Passband frequency (wp)  
   - Stopband frequency (ws)  
   - Sampling frequency (fs)  

2. What is meant by frequency response of a filter?  
   The frequency response describes the gain and phase shift introduced by the filter for different input frequencies.  

3. What is meant by magnitude response?  
   The magnitude response represents the filter's gain or attenuation as a function of frequency.  

4. What is meant by phase response?  
   The phase response represents the phase shift introduced by the filter for each input frequency.  

5. Differentiate ideal and practical filter responses.  
   - Ideal filters have sharp transitions and no ripples.  
   - Practical filters have gradual transitions and may exhibit ripples or imperfections.  

6. What are the types of analog filter approximations?  
   - Butterworth  
   - Chebyshev  
   - Elliptic  
   - Bessel  

7. Define the order of the filter and explain its importance.  
   The filter order determines the steepness of the transition band. Higher-order filters have sharper transitions but are more complex.  

8. Explain the advantages and disadvantages of Butterworth filters.  
   - Advantages: Flat response in the passband, simple design.  
   - Disadvantages: Less steep roll-off compared to Chebyshev filters.  

9. Explain the advantages and disadvantages of Chebyshev filters.  
   - Advantages: Sharper roll-off than Butterworth filters for the same order.  
   - Disadvantages: Ripple in the passband (Type I) or stopband (Type II).  

10. Why is Chebyshev better than Butterworth in some cases?  
    Chebyshev filters provide a sharper transition between passband and stopband for the same filter order, making them more efficient in applications where roll-off steepness is critical.

