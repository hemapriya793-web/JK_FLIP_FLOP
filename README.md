# JK_FLIP_FLOP

AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:
           Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

<img width="673" height="431" alt="1" src="https://github.com/user-attachments/assets/3a7cfbd9-bfeb-453a-9d39-dc7e2a450a0a" />

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

<img width="468" height="348" alt="2" src="https://github.com/user-attachments/assets/d5ade96f-1b8a-4ac8-95e2-77eca082e8d3" />

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

<img width="637" height="533" alt="3" src="https://github.com/user-attachments/assets/ab050877-ab1c-4912-aee5-a905f1184f97" />

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

<img width="640" height="254" alt="4" src="https://github.com/user-attachments/assets/fc871cbd-a357-4339-98b7-c70459bebc62" />

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

PROGRAM:
```
module jk_flip_flop (
    input  wire clk, rst, J, K,
    output reg  Q
);
    always @(posedge clk or posedge rst) begin
        if (rst)
            Q <= 1'b0;        // Reset
        else begin
            case ({J,K})
                2'b00: Q <= Q;        // Hold
                2'b01: Q <= 1'b0;     // Reset
                2'b10: Q <= 1'b1;     // Set
                2'b11: Q <= ~Q;       // Toggle
            endcase
        end
    end
endmodule
```
IMAGE: 
[EX 07 Dia.pdf](https://github.com/user-attachments/files/24149026/EX.07.Dia.pdf)

WAVEFORM: 
[Wave.bmp](https://github.com/user-attachments/files/24149050/Wave.bmp)

NAME: HEMA PRIYA

REF NO: 25017270

RESULT: 
Implementation of JK flipflop using verilog and validating their functionality using their functional tables is executed and the output is verified successfully.
