# Pseudo-Noise-PN-sequence-using-a-Linear-Feedback-Shift-Register-LFSR-with-feedback-defined-by-3-1-

A Pseudo-Noise (PN) sequence is a deterministic binary sequence that exhibits properties similar 
to random noise. Despite its deterministic nature, the sequence appears random and uncorrelated 
over short periods, making it ideal for various applications in communication and digital systems. 
PN sequences are widely used in applications like spread-spectrum communication, cryptography, 
and pseudo-random number generation. 

The sequence is generated using a fixed algorithm, ensuring repeatability for a given initial state. For an n-bit Linear Feedback Shift Register (LFSR), the length of a PN sequence is 2^n−1, which is the maximal length achievable for n bits. The sequence does not include an all-zero state. 

The sequence appears random but follows a predictable pattern. It satisfies the balance property 
(equal number of ones and zeros in a period), the run-length property (distribution of consecutive 
bits), and the autocorrelation property (low cross-correlation). 


# C CODE : 
#include <stdio.h> 
#define N 7   

void generatePNSequence(); 

int main() { 
generatePNSequence(); 
return 0; 
} 
void generatePNSequence() { 
int lfsr[3] = {1, 0, 1};  
int pnSequence[N]; 
int feedback, i, j; 
printf("Initial LFSR state: "); 
for (i = 0; i < 3; i++) { 
printf("%d ", lfsr[i]); 
} 
printf("\n"); 
for (i = 0; i < N; i++) { 
pnSequence[i] = lfsr[2];  
feedback = lfsr[2] ^ lfsr[0]; 
for (j = 2; j > 0; j--) { 
lfsr[j] = lfsr[j - 1]; 
} 
lfsr[0] = feedback;  
} 
printf("Generated PN sequence:\n"); 
for (i = 0; i < N; i++) { 
printf("%d ", pnSequence[i]); 
} 
printf("\n");  
}

# MANUAL CALCULATION: 
• For (3, 1) 
Where 3=no of flip flops, 
1s= the output of the flip flop 1 is connected  
as intermediate 
• Length =2^n-1 
=2^3-1 
=7 

# CONCLUSIONS: 
The experiment successfully demonstrated the generation of a PN sequence using an LFSR with 
feedback defined by (3,1). The simulation output matched the theoretical expectations, validating the properties of the PN sequence. PN sequences are indispensable in communication systems,cryptography, and digital signal processing, offering deterministic yet random-like properties. 

Their efficient generation through simple hardware circuits like the LFSR ensures their relevance across diverse applications.

