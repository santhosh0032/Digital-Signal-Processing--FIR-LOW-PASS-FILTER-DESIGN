# Digital-Signal-Processing--FIR-LOW-PASS-FILTER-DESIGN
## AIM:
To generate design of low pass FIR digital filter using Window.
## Software Required:
MAT LAB R2012.
## Algorithm:
Step 1: Open MATLAB and Write the program.

Step 2: Read the values of cut off frequency wc.

Step 2: Read the values of Order of the filter N.

Step 3: Find out the desired impulse response of the Low Pass filter Coefficient.

Step 4: Find out the windowing sequence.

Step 5: Plot the magnitude spectrum with x-label and y-label with suitable title.

Step 6: Terminate the program.

## PROGRAM:
~~~
clc;            % Clear command window
clear all;      % Clear workspace variables
close all;      % Close all figure windows

% Input parameters
wc = input('Enter the value of cutoff frequency: ');
N  = input('Enter the order (length) of the filter: ');

alpha = (N-1)/2;
eps = 0.001;

% High Pass Filter Ideal Impulse Response
n = 0:N-1;
hd = (sin(pi*(n - alpha + eps)) - sin(wc*(n - alpha + eps))) ./ (pi*(n - alpha + eps));

% Hanning Window Sequence
wh = 0.5 - 0.5*cos((2*pi*n)/(N-1));

% Windowed Filter Coefficients
hn = hd .* wh;

% Frequency Response
w = 0:0.01:pi;
h = freqz(hn,1,w);

% Plot the Frequency Response
figure;
plot(w/pi, abs(h), 'm','LineWidth',2);
xlabel('Normalized Frequency (\times\pi rad/sample)');
ylabel('Magnitude');
title('High Pass FIR Filter using Hanning Window');
grid on;
~~~
## OUTPUT:
![WhatsApp Image 2026-04-01 at 11 39 09 AM](https://github.com/user-attachments/assets/2bdf9433-2b31-414a-9d02-c2fe8fd31371)


## RESULT:
![WhatsApp Image 2026-04-01 at 10 31 03 PM](https://github.com/user-attachments/assets/4f1bc609-be2e-439d-999d-ea96f95962b2)

