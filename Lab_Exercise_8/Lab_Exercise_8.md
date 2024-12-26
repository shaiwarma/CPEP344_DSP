
Name: Shaira Sendad  
Course and Year: BSCPE-4  

---

I. OBJECTIVES:  

In this laboratory exercise, the students are expected to:  
• Implement HP FIR filter for a given sequence.  

---

II. MATERIALS:  

• Software: MATLAB  

---

III. PROCEDURES:  

Algorithm:  
Step I: Enter the pass band frequency (fp) and stop band frequency (fq).  
Step II: Get the sampling frequency (fs), length of window (n).  
Step III: Calculate cut-off frequency.  
Step IV: Use boxcar, hamming, Blackman Commands to design window.  
Step V: Design filter by using above parameters.  
Step VI: Find frequency response of the filter using MATLAB command freqz.  
Step VII: Plot the magnitude response and phase response of the filter.  

---

Flow Chart:  

![image](https://github.com/user-attachments/assets/e9d17dd8-9240-43b5-a826-d46fa6cf8178)
  

---

PROGRAM:  

```matlab
clc; 
clear all; 
close all; 
n=20; 
fp=300; 
fq=200; 
fs=1000; 
fn=2*fp/fs; 
window=blackman(n+1); 
b=fir1(n,fn,'high',window); 
[H W]=freqz(b,1,128); 
subplot(2,1,1); 
plot(W/pi,abs(H)); 
title('mag res of lpf'); 
ylabel('gain in db ------->'); 
xlabel('normalized frequency ----->'); 
subplot(2,1,2); 
plot(W/pi,angle(H)); 
title('phase res of lpf'); 
ylabel('angle ------ >'); 
xlabel('normalized frequency ----->'); 
```

---

Expected Waveforms:  

![image](https://github.com/user-attachments/assets/2bc2f9a4-190d-4d89-b6ac-fa72a4264bd2)


---

VIVA QUESTIONS:  

1. What is a filter?  
   A filter is a system that processes an input signal to produce an output signal by allowing certain frequencies to pass while attenuating others.  

2. Differentiate analog filter and digital filter.  
   - Analog Filter: Operates on continuous-time signals and uses electronic components like resistors and capacitors.  
   - Digital Filter: Operates on discrete-time signals and uses algorithms or computer processing.  

3. Define FIR filter.  
   FIR (Finite Impulse Response) filter is a type of digital filter that has a finite-duration impulse response and does not rely on feedback.  

4. What are the differences between recursive and non-recursive systems?  
   - Recursive Systems: Use feedback in their implementation.  
   - Non-Recursive Systems: Do not use feedback and depend only on current and past inputs.  

5. List a few applications of FIR filters.  
   - Audio processing  
   - Image processing  
   - Communication systems  
   - Biomedical signal processing  

6. Explain advantages of FIR filters over IIR filters.  
   - FIR filters are inherently stable.  
   - They can achieve a linear-phase response.  
   - Easier to implement with modern digital systems.  

7. Explain limitations of FIR filters.  
   - Higher computational complexity compared to IIR filters for the same specifications.  
   - Requires a higher filter order to meet stringent frequency specifications.  

8. What are the different methods to design FIR filters?  
   - Window method  
   - Frequency sampling method  
   - Least squares method  

9. Explain different window functions.  
   - Rectangular Window: Simplest, but causes significant side lobes.  
   - Hamming Window: Reduces side lobes at the expense of wider main lobe.  
   - Blackman Window: Offers better side lobe suppression compared to Hamming.  

10. Differentiate rectangular, triangular, and Kaiser Windows.  
   - Rectangular: Uniform weight, poor frequency selectivity.  
   - Triangular: Reduces discontinuity at edges, moderate selectivity.  
   - Kaiser: Provides a trade-off between main lobe width and side lobe suppression.  

---  
