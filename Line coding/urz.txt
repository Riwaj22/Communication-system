function [t,x] = urz(bits, bitrate)

T = length(bits)/bitrate; % full time of bit sequence
n = 200;%number of samples used to represent each bit
N = n*length(bits); %total number of samples used to represent entire bit sequence
dt = 1/n;
t = 0:dt:T;
x = zeros(1,length(t)); % output signal

for i = 0:length(bits)-1
  if bits(i+1) == 1
    x(i*n+1:(i+0.5)*n) = 1;
    x((i+0.5)*n+1:(i+1)*n) = 0;
  else
    x(i*n+1:(i+1)*n) = 0;
  end
end
