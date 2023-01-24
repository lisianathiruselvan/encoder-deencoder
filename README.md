# encoder-deencoder
## Experiment-08-

## Encoders-and-decoders

AIM: To implement 8 to 3 Encoder and 3to8 Decoder using verilog and validate its outputs

HARDWARE REQUIRED: – PC, Cyclone II , USB flasher

SOFTWARE REQUIRED: Quartus prime

THEORY

Encoders

Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

Encoders – An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.
 
 As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a](https://user-images.githubusercontent.com/119389971/214297900-c44c4c2d-9f96-4e2e-afc1-bcd2ba6f3977.png)



Figure -01 3 to 8 Encoder
Implementation –

X = D4 + D5 + D6 + D7 Y = D2 +D3 + D6 + D7 Z = D1 + D3 + D5 + D7 Hence, the encoder can be realised with OR gates as follows:

![171543740-68403b82-aa93-4c98-9343-f32b14885a2e](https://user-images.githubusercontent.com/119389971/214298040-b5a39938-5d0b-4bd9-bb68-c63cc5cc893b.png)


## Figure -02 3 to 8 Encoder implenentation
## Decoders

A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder. Implementation – D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ Similarly,

D1 = X’ Y’ Z D2 = X’ Y Z’ D3 = X’ Y Z D4 = X Y’ Z’ D5 = X Y’ Z D6 = X Y Z’ D7 = X Y Z


![171543978-ee2d0671-2846-40a1-8705-507fd6287a49](https://user-images.githubusercontent.com/119389971/214298332-5068b05b-2715-4690-951e-f80c29751bbf.png)

## Figure -03 8 to 3 Decoder
![171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035](https://user-images.githubusercontent.com/119389971/214298414-f3878dd7-c114-4fde-b94c-8b0f1af6ebf4.png)


Figure -04 8 to 3 Decoder implementation

Procedure
```
Step 1: Create module encoder and decoder.
Step 2: Get inputs and outputs for encoders and decoders.
Step 3: Perform "or" operation for encoder and "and" logic for decoders.
Step 4: Perform RTL LOGIC and get waveform.
Step-5: End the module.
```
PROGRAM

Program for Endocers and Decoders and verify its truth table in quartus using Verilog programming.

Developed by: lisiana t

RegisterNumber: 22006964

ENCODER
```
module EX8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
DECODER
```
module EX8(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
input a,b,c;
output d0,d1,d2,d3,d4,d5,d6,d7;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule
```
RTL LOGIC

For ENCODER
![encoder](https://user-images.githubusercontent.com/119389971/214298602-b0d1a04e-7db7-4763-a184-143181c8f27a.png)


For 
DECODER


![decoder](https://user-images.githubusercontent.com/119389971/214298693-5c19e151-7bea-4bb3-83c0-9b00c2412a49.png)

TIMING DIGRAMS

For ENCODER

![encodert](https://user-images.githubusercontent.com/119389971/214298822-bfc0e9dc-c2ae-4799-9b7a-b7bb422c4760.png)

For DECODER

![decodert](https://user-images.githubusercontent.com/119389971/214298874-1ef768fc-9852-4e7c-86d3-ff8f52ac8007.png)


TRUTH TABLE

For ENCODER

![encodertt](https://user-images.githubusercontent.com/119389971/214298954-93f91754-bcd1-4d3f-88fc-fee5f1759991.png)


For DECODER

![decodertt](https://user-images.githubusercontent.com/119389971/214299048-3d78b8e3-e34f-4a86-9bc2-fa2962687e75.png)

RESULTS

Thus the program to implement encoder and decoder using verilog is verified.
