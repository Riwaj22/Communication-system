clc 
clear all 
close all 
x=0:.1:2*pi; 
sig1=5*square(sin(x));
L=length(sig1); 
sig2=8*triang(L); 
subplot(2,2,1) 
plot(sig1,'linewidth',2); 
title('Square Signal'); 
ylabel('Amp---------->'); 
xlabel('time----------->'); 
subplot(2,2,2); 
plot(sig2,'linewidth',2); 
title('triangular Signal'); 
ylabel('Amp---------->'); 
xlabel('time----------->'); 
subplot(2,2,3) 
stem(sig1,'linewidth',2); 
title('Discrete Sinusoidal Signal');
ylabel('Amp---------->'); 
xlabel('time----------->'); 
subplot(224); 
stem(sig2,'linewidth',2); 
title('Discrete triangular Signal'); 
ylabel('Amp---------->'); 
xlabel('time----------->'); 
L=length(sig1)
for i=1:L 
sig(1,i)=sig1(i); 
sig(2,i)=sig2(i); 
end 
tdmsig=reshape(sig,1,2*L); %convert 2L samples to 1-D
figure 
stem(tdmsig,'linewidth',4); 
title('Tdm Signal') 
ylabel('Amp---------->'); 
xlabel('time----------->'); 
de_mux=reshape(tdmsig,2,L);
for i=1:L 
sig3(i)=de_mux(1,i); %Extract First row
sig4(i)=de_mux(2,i); %Extract second row
end 
figure 
subplot(2,1,1)
plot(sig3,'linewidth',2)
title('Recovered Sinosoidal Signal');
ylabel('Amp---------->'); 
xlabel('time----------->'); 
subplot(2,1,2); 
plot(sig4,'linewidth',2); 

title('Recovered Triangular Signal'); 
ylabel('Amp---------->');