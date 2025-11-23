# EXP 3 : IIR-CHEBYSHEV-FITER-DESIGN

## AIM: 

 To design an IIR Chebyshev filter  using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (LPF): 
```asm
clear;

// Sampling frequency
Fs = 5000;          // Hz

// Cutoff frequency
fc = 1500;          // Hz

// Butterworth LPF order 3 coefficients (Chebyshev Type I, 1 dB ripple)
// Precomputed numerator (b) and denominator (a)
b = [0.0929 0.2787 0.2787 0.0929];   // Numerator coefficients
a = [1.0000 -0.5772 0.4218 -0.0561];  // Denominator coefficients

// Frequency response
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

// Convert normalized frequency to Hz
f = f_norm * Fs;

// Plot magnitude response in dB
clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I Low Pass Filter (Order 3)");
xgrid();

// Display coefficients
disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```


## PROGRAM (HPF): 
```asm
clear;

// Sampling frequency
Fs = 5000;          // Hz

// Cutoff frequency
fc = 1500;          // Hz

// Chebyshev HPF order 3 coefficients (Type I, 1 dB ripple)
// Precomputed numerator (b) and denominator (a)
b = [0.4218 -0.5772 0.2787 -0.0929];   // Numerator coefficients
a = [1.0000 -0.5772 0.4218 -0.0561];   // Denominator coefficients

// Frequency response
Npoints = 512;
[H, f_norm] = frmag(b, a, Npoints);

// Convert normalized frequency to Hz
f = f_norm * Fs;

// Plot magnitude response in dB
clf();
plot(f, 20*log10(H + %eps));
xlabel("Frequency (Hz)");
ylabel("Magnitude (dB)");
title("Chebyshev Type I High Pass Filter (Order 3)");
xgrid();

// Display coefficients
disp(b, "Numerator coefficients (b):");
disp(a, "Denominator coefficients (a):");
```


## OUTPUT (LPF) : 
<img width="1826" height="966" alt="Screenshot 2025-11-05 112831" src="https://github.com/user-attachments/assets/547db548-ceaa-4f75-a818-2b7872dfed7b" />


## OUTPUT (HPF) : 
<img width="1832" height="963" alt="Screenshot 2025-11-05 112900" src="https://github.com/user-attachments/assets/223d2ec7-0d64-46dc-9a1e-afd985e6a657" />

## RESULT: 
IIR CHEBYSHEV FILTER USING SCILAB IS DESIGNED.


