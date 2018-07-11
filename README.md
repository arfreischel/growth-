# growth-

%%MatLab Code
%describes exponential, monod, and logistic grwoth

%% monod

clc;clear;close all;

r=0.5;
K=100;
N0= [10:10:30];

 

 

tspan= [0 10];
[t,N]= ode45(@(t,N) popGrowth(t,N,r,K), tspan, N0);

 
size(t)
size(N)

plot(t,N,'r','LineWidth',2);


function [dNdt]=popGrowth(t,N,r,K)

 
dNdt(1,1) = r.*(K - N(1));
dNdt(2,1) = r*(K - N(2));

end
