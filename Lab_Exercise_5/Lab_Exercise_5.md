
Name: Shaira Sendad  
Course and Year: BSCPE-4  

---

I. OBJECTIVES:  

In this laboratory exercise, the students are expected to:  
- Find the FFT of a given sequence.  

---

II. MATERIALS:  

- Software: MATLAB  

---

III. PROCEDURES:  

THEORY: 
DFT of a sequence 
 
  ![image](https://github.com/user-attachments/assets/77590f76-8af5-4c50-b94a-f9b6ebf38d6f)





Where N= Length of sequence. 

K= Frequency Coefficient. 

n = Samples in time domain.
 

FFT: -Fast Fourier transform. 

There are two methods. 


1. Decimation in time (DIT ) FFT. 

2. Decimation in Frequency (DIF) FFT. 

Why we need FFT? 

The no of multiplications in DFT = N2. 

The no of Additions in DFT = N (N-1). 

For FFT. 

The no of multiplication = N/2 log 2N. 

The no of additions = N log2 N.




---

Algorithm: 

Step I : Give input sequence x[n]. 

Step II : Find the length of the input sequence using length command. 

Step III : Find FFT and IFFT using matlab commands fft and ifft. 

Step IV : Plot magnitude and phase response 

Step V : Display the results

---
FLOWCHART:

![image](https://github.com/user-attachments/assets/473a54fe-f4d3-40ec-8b7e-26c9a72587db)


PROGRAM:  

```matlab
clc; 
clear all; 
close all; 
x = input('Enter the sequence: '); 
N = length(x); 
xK = fft(x, N); 
xn = ifft(xK); 
n = 0:N-1; 
subplot(2, 2, 1); 
stem(n, x); 
xlabel('n -->'); 
ylabel('Amplitude'); 
title('Input Sequence'); 
subplot(2, 2, 2); 
stem(n, abs(xK)); 
xlabel('n -->'); 
ylabel('Magnitude'); 
title('Magnitude Response'); 
subplot(2, 2, 3); 
stem(n, angle(xK)); 
xlabel('n -->'); 
ylabel('Phase'); 
title('Phase Response'); 
subplot(2, 2, 4); 
stem(n, xn); 
xlabel('n -->'); 
ylabel('Amplitude'); 
title('IFFT'); 
```

---

OUTPUT:  

Input:  
Enter the sequence: [1 2 3 4 5]  

Output:  
x = [1 2 3 4 5]  
N = 5  
xK = [15.0000, -2.5000 + 3.4410i, -2.5000 + 0.8123i, -2.5000 - 0.8123i, -2.5000 - 3.4410i]  
xn = [1 2 3 4 5]  

Output Waveforms:  
![image](https://github.com/user-attachments/assets/0e4f0c9c-96be-484d-a1f5-4c0a06e75b36)


---

QUESTIONS AND ANSWERS:  

1. Define transform. What is the need for transform?  
A transform converts a signal from one domain (e.g., time) to another domain (e.g., frequency) to simplify analysis and processing.

2. Differentiate Fourier transform and discrete Fourier transform.  
Fourier transform applies to continuous signals, while the discrete Fourier transform (DFT) is used for discrete signals.

3. Differentiate DFT and DTFT.  
DFT gives a discrete set of frequency components, while DTFT provides a continuous spectrum of a discrete-time signal.

4. What are the advantages of FFT over DFT?  
FFT reduces the number of computations, making it faster and more efficient than the direct application of DFT.

5. Differentiate DITFFT and DIFFFT algorithms.  
- DITFFT splits the input sequence into smaller time-domain sequences.  
- DIFFFT splits the sequence into smaller frequency-domain sequences.

6. What is meant by radix?  
Radix refers to the base of the numbering system used in FFT algorithms, such as radix-2 or radix-4.

7. What is meant by twiddle factor, and give its properties?  
Twiddle factor is a complex exponential term used in FFT computations. Its properties include periodicity and symmetry, which simplify calculations.

8. How is FFT useful to represent a signal?  
FFT breaks down a signal into its frequency components, enabling easier analysis and processing.

9. Compare FFT and DFT with respect to the number of calculations required.  
FFT requires fewer calculations than DFT due to its efficient recursive structure.

10. How is the original signal reconstructed from the FFT of a signal?  
The original signal is reconstructed using the inverse FFT (IFFT), which performs the reverse transformation.
