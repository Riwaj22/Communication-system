clc
close all
clear all
f = 1;
x = [1 1 0 0 1 0 1 0]; %input bits
nx = length (x) ;
figure('name','1 1 0 0 1 0 1 0');

for i = 1:nx
    t = i:0.0001:i+1;
    if x(i) == 1
        ask = sin(2*pi*f*t);
        fsk = sin(2*pi*2*f*t);
        psk = sin(2*pi*f*t);
    else
        ask = 0;
        fsk = sin(2*pi*f*t);
        psk = sin(2*pi*f*t + pi);
    end

subplot(3,1,1)
plot(t,ask,'linewidth',3)
hold on
grid on
axis([1 nx+1 -1 1])
title('Amplitude shift keying')

subplot(3,1,2)
plot(t,fsk,'linewidth',3)
hold on
grid on
axis([1 nx+1 -1.5 1.5])
title('Frequency shift keying')

subplot(3,1,3)
plot(t,psk,'linewidth',3)
hold on
grid on
axis([1 nx+1 -1 1])
title('Phase shift keying')
end

