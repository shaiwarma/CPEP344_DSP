Name			:  SHAIRA SENDAD  
Course and Year	:  BSCPE-4  

---

I. OBJECTIVES:  

In this laboratory exercise, the students are expected to:  
• implement LP IIR filter for a given sequence.  

---
II. MATERIALS:  

• Software: MATLAB  

---

III. PROCEDURES:  

THEORY:  
IIR filters are digital filters with infinite impulse response. Unlike FIR filters, they have the feedback (a recursive part of a filter) and are known as recursive digital filters therefore.  
For this reason, IIR filters have much better frequency response than FIR filters of the same order. Unlike FIR filters, their phase characteristic is not linear which can cause a problem to the systems which need phase linearity. For this reason, it is not preferable to use IIR filters in digital signal processing when the phase is of the essence. Otherwise, when the linear phase characteristic is not important, the use of IIR filters is an excellent solution.  
There is one problem known as a potential instability that is typical of IIR filters only. FIR filters do not have such a problem as they do not have the feedback. For this reason, it is always necessary to check after the design process whether the resulting IIR filter is stable or not.  

IIR FILTER DESIGN  
For the given specifications to design a digital IIR filter, first, we need to design an analog filter (Butterworth or Chebyshev). The resultant analog filter is transformed to a digital filter by using either “Bilinear transformation or Impulse Invariant transformation.”  

---
Algorithm:  
Step I: Enter the passband ripple (rp) and stopband ripple (rs).  
Step II: Enter the passband frequency (wp) and stopband frequency (ws).  
Step III: Get the sampling frequency (fs).  
Step IV: Calculate normalized passband frequency and normalized stopband frequency w1 and w2 respectively.  
Step V: Make use of the following function to calculate the order of the filter:  

- Butterworth filter order: [n,wn]=buttord(w1,w2,rp,rs).  
- Chebyshev filter order: [n,wn]=cheb1ord(w1,w2,rp,rs).  

Step VI: Design an nth order digital low-pass Butterworth or Chebyshev filter using the following statements:  

- Butterworth filter: [b, a]=butter (n, wn).  
- Chebyshev filter: [b,a]=cheby1 (n, 0.5, wn).  

Step VII: Find the digital frequency response of the filter by using the ‘freqz()’ function.  
Step VIII: Calculate the magnitude of the frequency response in decibels (dB): mag=20*log10 (abs (H)).  
Step IX: Plot the magnitude response [magnitude in dB vs normalized frequency].  
Step X: Calculate the phase response using angle (H).  
Step XI: Plot the phase response [phase in radians vs normalized frequency (Hz)].  

---
Flow Chart:  
![image](https://github.com/user-attachments/assets/fff6a889-1bf5-4eed-b0b4-d97fcb775813)

PROGRAM:  
```matlab
clc;  
clear all;  
close all;  
disp('enter the IIR filter design specifications');  
rp=input('enter the passband ripple:');  
rs=input('enter the stopband ripple:');  
wp=input('enter the passband freq:');  
ws=input('enter the stopband freq:');  
fs=input('enter the sampling freq:');  
w1=2*wp/fs;w2=2*ws/fs;  
[n,wn]=buttord(w1,w2,rp,rs,'s');  
disp('Frequency response of IIR LPF is:');  
[b,a]=butter(n,wn,'low','s');  
w=0:.01:pi;  
[h,om]=freqs(b,a,w);  
m=20*log10(abs(h));  
an=angle(h);  
figure,subplot(2,1,1);plot(om/pi,m);  
title('magnitude response of IIR filter is:');  
xlabel('(a) Normalized freq. -->');  
ylabel('Gain in dB-->');  
subplot(2,1,2);plot(om/pi,an);  
title('phase response of IIR filter is:');  
xlabel('(b) Normalized freq. -->');  
ylabel('Phase in radians-->');  
```
---
Expected waveforms:  
enter the IIR filter design specifications  
enter the passband ripple:15  
enter the stopband ripple:60  
enter the passband freq:1500  
enter the stopband freq:3000  
enter the sampling freq:7000  
![image](https://github.com/user-attachments/assets/f9c57d89-c064-4dd0-935e-2f39c9deba2d)


---

VIVA QUESTIONS:  

1. List some advantages of digital filters over analog filters.  
   - Digital filters are more precise and do not suffer from component aging or temperature variations.  
   - They are more flexible in design and implementation.  
   - Adjustments can be made by changing the coefficients, unlike analog filters that require physical changes.  

2. Write some differences between FIR and IIR filters.  
   - FIR filters have a finite impulse response, whereas IIR filters have an infinite impulse response.  
   - FIR filters are inherently stable; IIR filters may be unstable due to feedback.  
   - FIR filters offer linear phase response; IIR filters generally do not.  

3. What are the different methods to design IIR filters?  
   - Bilinear transformation  
   - Impulse invariant transformation  
   - Matched z-transform method  

4. Why are IIR filters not reliable?  
   - They can become unstable due to feedback loops.  
   - They have a non-linear phase response, which is unsuitable for certain applications.  

5. What are different applications of IIR filters?  
   - Audio signal processing  
   - Communication systems  
   - Noise reduction  
   - Biomedical signal processing  

6. What are advantages of IIR filters?  
   - Require fewer coefficients compared to FIR filters for the same specifications.  
   - Efficient in terms of computation and memory usage.  
   - Provide excellent frequency response.  

7. What are disadvantages of IIR filters?  
   - Can be unstable if not properly designed.  
   - Have a non-linear phase response, which can distort signals.  

8. Differentiate Butterworth and Chebyshev approximations.  
   - Butterworth filters have a flat frequency response in the passband.  
   - Chebyshev filters allow ripples in the passband for sharper roll-off.  

9. What is meant by impulse response?  
   - The output of a filter when an impulse is applied to its input. It characterizes the filter's behavior.  

10. Difference between IIR low-pass and high-pass filters.  
   - A low-pass filter allows frequencies below a cutoff frequency to pass, attenuating higher frequencies.  
   - A high-pass filter does the opposite, allowing high frequencies to pass and attenuating lower ones.  

---
