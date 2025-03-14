# DAY-43_100_DAYS_OF_RTL
// CELSIUS TO FAHRENHEIT CONVERTER

module CelsiusToFahrenheit (
    input  [7:0] celsius,  // Input Celsius temperature (8-bit)
    output [15:0] fahrenheit // Output Fahrenheit temperature (16-bit)
);
    
    // Formula: Fahrenheit = (Celsius * 9/5) + 32
    assign fahrenheit = (celsius * 9 / 5) + 32;
    
endmodule

//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

// Testbench for Celsius to Fahrenheit Converter
module tb_CelsiusToFahrenheit;
    
    reg signed [7:0] celsius;  // Test input
    wire signed [15:0] fahrenheit;  // Test output
    
    // Instantiate the module
    CelsiusToFahrenheit uut (
        .celsius(celsius),
        .fahrenheit(fahrenheit)
    );
    
    initial begin
        // Test cases with sample Celsius values
        celsius = 0; #10;  // Freezing point of water
        $display("Celsius: %d -> Fahrenheit: %d", celsius, fahrenheit);
        
        celsius = 25; #10;  // Room temperature
        $display("Celsius: %d -> Fahrenheit: %d", celsius, fahrenheit);
        
        celsius = -40; #10;  // Point where Celsius and Fahrenheit are equal
        $display("Celsius: %d -> Fahrenheit: %d", celsius, fahrenheit);
        
        celsius = 100; #10;  // Boiling point of water
        $display("Celsius: %d -> Fahrenheit: %d", celsius, fahrenheit);
        
        celsius = -10; #10;  // Sub-zero test case
        $display("Celsius: %d -> Fahrenheit: %d", celsius, fahrenheit);
        
        $stop;  // Stop simulation
    end
    
endmodule
