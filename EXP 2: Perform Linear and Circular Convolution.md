# EXP 1 : Linear and Circular Convolution

## AIM: 

 To perform Linear and Circular Convolution for two given sequence using SCILAB. 

## APPARATUS REQUIRED: 
PC installed with SCILAB. 

## PROGRAM (Linear Convolution): 

// Linear Convolution
SURYAP2006 19EC409-DTSP-2025-2026
Code Pull requests Actions Projects Wiki Security Insights
19EC409-DTSP-2025-2026 / EXP 2: Perform Linear and Circular Convolution.md
EXP 1 : Linear and Circular Convolution
AIM:
APPARATUS REQUIRED:
PROGRAM (Linear Convolution):
// Linear Convolution in Scilab
// Input sequences
x = [1 2 3 4]; // Example input signal
h = [1 1 1]; // Example impulse response
// Perform linear convolution
y = conv(x, h);
// Display results
disp("Input sequence x(n) = " + string(x));
disp("Impulse response h(n) = " + string(h));
disp("Linear Convolution y(n) = " + string(y));
// --- Plot signals ---
// Plot x(n)
Preview Code Blame Raw
// Circular Convolution
subplot(3,1,1);
n1 = 0:length(x)-1;
plot2d3(n1, x);
xtitle("Input Sequence x(n)");
// Plot h(n)
subplot(3,1,2);
n2 = 0:length(h)-1;
plot2d3(n2, h);
xtitle("Impulse Response h(n)");
// Plot y(n)
subplot(3,1,3);
n3 = 0:length(y)-1;
plot2d3(n3, y);
xtitle("Linear Convolution y(n)");


## PROGRAM (Circular Convolution): 

// Circular Convolution

clc;
clear;
// ------------------------------
// Input Sequences
// ------------------------------
x = [1 1 1 1];
h = [1 2 3];
// Lengths
N1 = length(x);
N2 = length(h);
N = max(N1, N2); // Length for circular convolution
// ------------------------------
// Zero-Padding to Equal Length
// ------------------------------
if N1 > N2 then
h = [h, zeros(1, N1-N2)];
elseif N2 > N1 then
x = [x, zeros(1, N2-N1)];
end
disp(x, "Padded x(n) = ");
disp(h, "Padded h(n) = ");
// ------------------------------
// Circular Convolution Computation
// ------------------------------
y = zeros(1, N);
for n = 1:N
sum = 0;
for i = 1:N
j = n - i + 1;
if j <= 0 then
j = N + j;
end
sum = sum + x(i) * h(j);
end
y(n) = sum;
end
disp(y, "Circular Convolution Result y(n) = ");
// ------------------------------
// Plotting Discrete-Time Signals
// ------------------------------
// Input sequence x(n)
n1 = 0:N1-1;
subplot(3,1,1);
plot2d3(n1, x(1:N1), -4); // stem plot
xlabel("n");
ylabel("x(n)");
title("Input Sequence x(n)");
// Impulse response h(n)
n2 = 0:N2-1;
subplot(3,1,2);
plot2d3(n2, h(1:N2), -4); // stem plot
xlabel("n");
ylabel("h(n)");
title("Impulse Response h(n)");
// Circular convolution result y(n)
n = 0:N-1;
subplot(3,1,3);
plot2d3(n, y, -4); // stem plot
xlabel("n");
ylabel("y(n)");
title("Circular Convolution y(n)");
## OUTPUT (Linear Convolution): 

<img width="802" height="447" alt="LINEAR CONVOLUTION OUTPUT2025-09-22 162836" src="https://github.com/user-attachments/assets/13401e9b-8e22-4391-b738-5498ce36b907" />

## OUTPUT (Circular Convolution): 
<img width="772" height="430" alt="CIRCULAR CONVOLUTION OUTPUT 2025-09-22 163007" src="https://github.com/user-attachments/assets/e6b15e4e-248f-46f1-ba2b-909c881e6e74" />

## RESULT: 
The linear and circular convolution of the given sequences were successfully computed
using SCILAB.
