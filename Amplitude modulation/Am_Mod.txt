clc;
clear all;
close all;
t=0:.0001:1;
Am=input('message amplitude, Am=  ');
Ac=input('carrier amplitude, Ac=  ');
Fm=input('message frequency, Fm=  ');
Fc=input('carrier frequency, Fc=  ');

%Message signal is: 
Mt = Am*cos(2*pi*Fm*t);
subplot(3,1,1);
plot(t, Mt,'linewidth',3);
grid on
xlabel('time')
ylabel('amplitude')
title('message signal')
grid on;

Ct =Ac*cos(2*pi*Fc*t);
subplot(3,1,2)
plot(t,Ct,'r','linewidth',2)
xlabel('time')
ylabel('amplitude')
title('carrier signal')
grid on;

%Modulation index is:
Ma = Am/Ac;

%Amplitude sensitivity of modulation is:

Ka = Ma/Am;
s= Ac*(1 + Ka.*Mt).*cos(2*pi*Fc*t);


subplot(3,1,3)
plot(t,s,'g','linewidth',2)
xlabel('time');
ylabel('amplitude')
title('am signal');
grid on;
