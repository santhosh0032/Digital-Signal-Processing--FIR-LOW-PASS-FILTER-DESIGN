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
clc; % clear screen
close all; % close all figure windows
wc=input('enter the value of cut off frequency');
N=input('enter the value of filter');
alpha=(N-1)/2;
eps=0.001;
%Low Pass Filter Coefficient
n=0:1:N-1;
hd=sin(wc*(n-alpha+eps))./(pi*(n-alpha+eps));
%Bartlett Window Sequence
n=0:1:N-1;
wh=1-2*abs(n-alpha)/N
hn=hd.*wh;
% Plot the Low Pass Filter with Hanning Window Technique
w=0:0.01:pi;
h=freqz(hn,1,w);
plot(w/pi,abs(h),'ms');
~~~
## OUTPUT:
<img width="694" height="517" alt="image" src="https://github.com/user-attachments/assets/17b8d678-ca77-4b55-9897-2064e765dfcb" />


## RESULT:
![WhatsApp Image 2026-03-25 at 7 32 24 PM](https://github.com/user-attachments/assets/ab525924-0af0-40f0-8faa-d8484c5a1cdf)

