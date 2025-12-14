# JK_FLIPFLOP
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure

image
This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

image
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

PROGRAM
```
module JKflipflop (
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


RTL LOGIC FOR FLIPFLOPS:

TIMING DIGRAMS FOR FLIP FLOPS Uploading unknown.bmp…

RESULTS

We got the expected output
