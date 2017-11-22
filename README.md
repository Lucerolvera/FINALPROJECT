# FINALPROJECT
%% Proyecto Equipo 2: Los Cumpleaños y la Probabilidad.
%                               ITESM Campus Hidalgo
%%
%Limpia y cierra todas las ventanas de Matlab
clear all; close all;clc;
%Elimina todas las advertencias del desbordamiento de memoria
warning('off','all')
%Encabezados de la tabla
%Inicio de Ciclo For
for i=1:69
%Variable Auxiliar
k=i+1;
%Columna uno de la tabla con el valor de n
P(i) = k; 
%Columna dos de la tabla con el valor P(A)
P1(i) = 1 - nchoosek(366,k)*(factorial(k)/(366^k));
if P1(i)==0.5
fprintf('i=%d, k=%d\n',i,k);
end
end
%%
% *RESULTADOS*
plot(P,P1*100);
xlabel('n')
ylabel('P(A) [%]')
title('Probabilidad')
fprintf('   n        P(A)\n');
formatSpec = '%4.0f     %8.6f\n'; 
for i=21:247
fprintf(formatSpec,P(i),100*P1(i));
end
