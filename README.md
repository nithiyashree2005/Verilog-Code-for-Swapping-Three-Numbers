# Verilog-Code-for-Swapping-Three-Numbers

## Aim:

To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

## Apparatus Required:

Vivado 2023.1 or equivalent Verilog simulation tool.

## Procedure:

1.Launch Vivado 2023.1:
2.Open Vivado and create a new project.
3.Write the Verilog Code for Swapping:
  Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
4.Create the Testbench:
  Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
5.Add the Verilog Files:
  Add the Verilog module and the testbench file to the Vivado project.
6.Run Simulation:
  Run the behavioral simulation in Vivado to verify the swapping operation.
7.Observe the Waveforms:
  Examine the waveform to confirm that the values of the three numbers are swapped as expected.
8.Save and Document Results:
  Capture the waveform output and include the results in your report for verification.

## Verilog Code:

```
// swap_three_numbers.v
module swap_three_numbers (
    input wire [7:0] a_in,
    input wire [7:0] b_in,
    input wire [7:0] c_in,
    output reg [7:0] a_out,
    output reg [7:0] b_out,
    output reg [7:0] c_out
);
    always @(*) begin
        a_out = b_in; // Swap: a = b
        b_out = c_in; // Swap: b = c
        c_out = a_in; // Swap: c = a
    end
endmodule

```

## Output:

![exp 1 3](https://github.com/user-attachments/assets/73329d46-ebe4-4f55-b6d2-9173a152be87)

## Testbench for Swapping Three Numbers:

```

// swap_three_numbers_tb.v
`timescale 1ns / 1ps

module swap_three_numbers_tb;

    // Inputs
    reg [7:0] a;
    reg [7:0] b;
    reg [7:0] c;

    // Outputs
    wire [7:0] a_out;
    wire [7:0] b_out;
    wire [7:0] c_out;

    // Instantiate the Unit Under Test (UUT)
    swap_three_numbers uut (
        .a_in(a),
        .b_in(b),
        .c_in(c),
        .a_out(a_out),
        .b_out(b_out),
        .c_out(c_out)
    );

    // Test procedure
    initial begin
        // Initialize inputs
        a = 8'd10; // Assign 10 to a
        b = 8'd20; // Assign 20 to b
        c = 8'd30; // Assign 30 to c

        // Wait for 10 ns to observe swap
        #10;

        // Display results
        $display("Before Swap: a = %d, b = %d, c = %d", a, b, c);
        #10;
        $display("After Swap: a = %d, b = %d, c = %d", a_out, b_out, c_out);
        
        // Stop the simulation
        #10 $stop;
    end
endmodule
```

## Output:

![exp 1 2](https://github.com/user-attachments/assets/3802fad6-d3a6-49ae-9a6b-1f16573e897d)


## Conclusion:

In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
