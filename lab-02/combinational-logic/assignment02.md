# Lab 2: Samuel Vadovic

### 2-bit comparator

1. Karnaugh maps for other two functions:

   Greater than:

   ![K-maps](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/lab-02/Greater.png)

   Less than:

   ![K-maps](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/lab-02/lesser.png)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

   ![Logic functions](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/lab-02/equations.png)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **35**

```vhdl
   p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case ...
        s_b <= "0101"; s_a <= "0011"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combinations are not equal" severity error;



        -- WRITE OTHER TEST CASES HERE



        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait; -- Data generation process is suspended forever
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

   ![your figure](https://github.com/VadovicSamuel/Digital-Electronics-1/blob/main/lab-02/Report.png)

3. Link to your public EDA Playground example:

   [EDA Playground](https://www.edaplayground.com/x/gjTy)
