Name			      : Shaira Sendad

Course and Year	: BSCPE-4




I. OBJECTIVES:

In this laboratory exercise, the students are expected to:
    find Discrete Fourier Transform and Inverse Discrete Fourier Transform of given digital signal..



II. MATERIALS:

Software: MATLAB



III. PROCEDURE:



THEORY:

Basic equation to find the DFT of a sequence is given below.

![image](https://github.com/user-attachments/assets/3002dd03-0fe4-4c10-8794-54913b2703be)

Basic equation to find the IDFT of a sequence is given below. 

![image](https://github.com/user-attachments/assets/ade40141-6dc8-43e8-8095-f5a08eecf78c)



Algorithm: 

Step I: Get the input sequence.

Step II: Find the DFT of the input sequence using direct equation of DFT. 

Step III: Find the IDFT using the direct equation. 

Step IV: Plot DFT and IDFT of the given sequence using matlab command stem.

Step V: Display the above outputs.



Flow chart:

![image](https://github.com/user-attachments/assets/8a17ed3d-4484-43aa-ad0f-5320f3437974)

--------------------------------------------------------------------------------------------------------------------------------------

Output: 
Xn=[1 2 3 4 5] 

Xk = 15,-2.50+3.44i,-2.50+0.81i,-2.49-0.81i,-2.49-3.44i


Output Waveforms:

![waveform lab1](https://github.com/user-attachments/assets/cf50fa98-1347-4d58-a3e1-d63c081f36cb)

RESULT: 

VIVA QUESTIONS: 

1.Define signal. Give examples for 1-D, 2-D, 3-D signals.

A signal is a function that conveys information about a phenomenon. It can be represented in various dimensions. For example, a 1-D signal could be a time-series data, like an audio waveform over time. A 2-D signal might be an image, where the two dimensions represent pixel coordinates. A 3-D signal can represent a video, where two dimensions are spatial (height and width) and the third dimension is time, capturing how the image evolves over time.

2.Define transform. What is the need for transform?

A transform is a mathematical operation that converts a signal from one domain to another, typically from the time or spatial domain to the frequency domain. This is necessary because it simplifies analysis and processing of signals, making it easier to understand their characteristics, filter them, or compress data.

3.Differentiate Fourier transform and discrete Fourier transform.

The Fourier Transform (FT) is used for continuous signals and transforms them into their frequency components. In contrast, the Discrete Fourier Transform (DFT) applies to discrete signals (sampled data) and provides a finite number of frequency components. While the FT is defined over continuous frequencies, the DFT yields a discrete set of frequencies, making it suitable for digital signal processing.

4.Differentiate DFT and DTFT.

The Discrete Fourier Transform (DFT) is used for finite sequences of data and results in a finite number of frequency points. The Discrete-Time Fourier Transform (DTFT), on the other hand, applies to infinite sequences and provides a continuous spectrum. Thus, the DTFT gives a more detailed view of frequency content, while the DFT is practical for computation with limited data.

5.Explain mathematical formula for calculation of DFT.

The DFT of a sequence x[n] of length N is calculated using the formula:


![image](https://github.com/user-attachments/assets/dd4d0fd3-1ec6-42ce-8122-90203ad298ed)


where X[k] represents the DFT coefficients, j is the imaginary unit, and k indicates the frequency index.


6.Explain mathematical formula for calculation of IDFT.

The Inverse Discrete Fourier Transform (IDFT) is given by the formula:

![image](https://github.com/user-attachments/assets/84c2924c-a491-4823-8d02-5ee292233a34)



This formula reconstructs the original signal x[n] from its DFT coefficients X[k].

7.How to calculate FT for 1-D signal?

To calculate the Fourier Transform of a 1-D signal x(t, you use the formula:

![image](https://github.com/user-attachments/assets/c2877dc6-427f-4658-ae7d-04ef6f444b80)


This integral computes the contribution of each frequency f to the signal over all time.


8.What is meant by magnitude plot, phase plot, power spectrum?

A magnitude plot displays the amplitude of the frequency components of a signal, typically represented as ∣X(f)∣. A phase plot shows the phase angle of the frequency components, represented as ∠X(f). The power spectrum indicates how the power of a signal is distributed across different frequencies, often computed as ∣X(f)∣raised to two.


9.Explain the applications of DFT.

The DFT has numerous applications in digital signal processing, such as analyzing signals in the frequency domain, filtering, spectral analysis, image processing, and data compression. It’s widely used in telecommunications, audio processing, and even in algorithms for solving differential equations.

10.What are separable transforms?

Separable transforms are those that can be applied independently in each dimension of a multi-dimensional signal, effectively breaking down the transformation process. For example, in image processing, a 2-D Fourier transform can be computed as two successive 1-D transforms, first along the rows and then along the columns. This property simplifies computation and makes it efficient, especially for higher-dimensional data.
