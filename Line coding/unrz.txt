function [t,x] = unrz(bits, bitrate)
T = length(bits)/bitrate; % full time of bit sequence
n = 200;%number of samples used to represent each bit
N = n*length(bits); %total number of samples used to represent entire bit sequence
dt = 1/n;
t = 0:dt:T;
x = zeros(1,length(t)); % output signal

for i = 0:(length(bits)-1)
  if bits(i+1) == 1
    x(i*n+1:(i+1)*n) = 1; %i=0, x(1:200)= 1
      
  else
    x(i*n+1:(i+1)*n) = 0;
    
    %i= 1, x(1*200 +1 : (1+1)*200) = 0
    %x(201: 400)= 0;
  end
end
