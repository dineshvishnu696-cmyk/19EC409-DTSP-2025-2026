# EXP 1 A : COMPUTATION OF DFT USING DIRECT AND FFT

# AIM: 

# To Obtain DFT and FFT of a given sequence in SCILAB. 

# APPARATUS REQUIRED: 
PC installed with SCILAB. 

# PROGRAM: 
// DISCRETE FOURIER TRANSFORM 
str_out = "{";
for k = 1:N
    real_part = round(real(X(k))*1000)/1000; // rounding to 3 decimals
    imag_part = round(imag(X(k))*1000)/1000;
    
    if imag_part >= 0 then
        str_out = str_out + string(real_part) + " + j" + string(imag_part);
    else
        str_out = str_out + string(real_part) + " - j" + string(abs(imag_part));
    end
    
    if k < N then
        str_out = str_out + ", ";
    else
        str_out = str_out + "}";
    end
end

disp("X(k) = " + str_out);

// Step 5: Plot magnitude and phase
freq_index = 0:N-1;

subplot(2,1,1);
plot(freq_index, abs(X), 'o-');
xlabel("Frequency index (k)");
ylabel("|X(k)|");
title("Magnitude Spectrum");


subplot(2,1,2);
plot(freq_index, atan(imag(X), real(X)), 'o-'); // phase = atan2(imag, real)
xlabel("Frequency index (k)");
ylabel("Phase (radians)");
title("Phase Spectrum");

# OUTPUT: 
![WhatsApp Image 2025-09-22 at 16 06 15_2e967e79](https://github.com/user-attachments/assets/81d42850-e0af-405e-bad4-9ead01fb2706)


# RESULT: 
The DFT of the given sequence was successfully computed using both direct computation method and FFT algorithm in SCILAB.
