t = 0 : 1/1e3 : 4; % 2e3= 2000 
d = 0 : 1/5 : 4; %Total duration of each pulse 1/5= 0.2
x = 2*sin(2*pi*t); %message signal
subplot(3,1,1)
plot(x,'g','linewidth',3);
title('message');
xlabel('time');
ylabel('amplitude');
y = pulstran(t,d,'rectpuls',0.1); %0.1 = ON time, d = total duration of each pulse
subplot(3,1,2)
plot(y,'r','linewidth',3 );
title('Pulse Input ');
xlabel('time');
ylabel('amplitude');
z=x.*y; % PAM output
subplot(3,1,3)
plot(z,'k','linewidth',3);
title('PAM signal ');
xlabel('time');
ylabel('amplitude');