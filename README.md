# Design-of-FIR-Filters-using-hamming-window

# DESIGN OF LOW PASS FIR DIGITAL FILTER 

# AIM: 
          
  To generate design of high pass FIR digital filter using SCILAB 

# APPARATUS REQUIRED: 

  PC Installed with SCILAB 

# PROGRAM 

clc;

clear;

close;

disp('Design of High Pass FIR Digital Filter using Window Technique');

fc = 0.3;

M = 30;

N = M + 1;

n = 0:M;

alpha = M / 2;

hd = -sin(2 * %pi * fc * (n - alpha)) ./ (%pi * (n - alpha));

hd(alpha + 1) = 1 - 2 * fc; 

w = 0.54 - 0.46 * cos(2 * %pi * n / M);

h = hd .* w;

disp("FIR High Pass Filter Coefficients:");

disp(h);

subplot(3,1,1);

plot(n, hd);

title('Ideal Impulse Response hd[n]');

xlabel('n');

ylabel('Amplitude');

subplot(3,1,2);

plot(n, w);

title('Hamming Window w[n]');

xlabel('n');

ylabel('Amplitude');

subplot(3,1,3);

plot(n, h);

title('Actual FIR HPF Coefficients h[n]');

xlabel('n');

ylabel('Amplitude');

figure;

[H, f] = frmag(h, 512);

plot(f, 20*log10(H));

title('Magnitude Response of FIR High Pass Filter');

xlabel('Normalized Frequency');

ylabel('Magnitude (dB)');

# OUTPUT

<img width="1551" height="718" alt="Screenshot 2025-11-21 004206" src="https://github.com/user-attachments/assets/911904d6-7aef-4e2a-9d23-81fb982eab06" />

# RESULT

 Thus design of High pass FIR digital filter waveforms were plotted and output was verified.
