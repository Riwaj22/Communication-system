clc
clear all
close all
bits = [1 0 1 0 0 0 1 1 0];

bitrate = 1; % 1 bit per second
[a,b] = unrz(bits,bitrate);
plot(a,b,'linewidth',3);
grid on;
title(['Unipolar NRZ: [' num2str(bits) ']']);

[t,s] = urz(bits,bitrate);
figure;
plot(t,s,'LineWidth',3);
grid on;
title(['Unipolar RZ: [' num2str(bits) ']']);
[t,s] = prz(bits,bitrate);
figure;
plot(t,s,'LineWidth',3);
grid on;
title(['Polar RZ: [' num2str(bits) ']']);

[t,s] = manchester(bits,bitrate);
figure;
plot(t,s,'LineWidth',3);
%axis([0 t(end) -1.1 1.1])
grid on;
title(['Manchester: [' num2str(bits) ']']);





