# Lab 2: Ondřej Nesvadba

### 2-bit comparator

1. Karnaugh maps for other two functions:


   Greater than:
   
![CP02_1](https://user-images.githubusercontent.com/99417291/155342948-eb97c3bb-5810-437b-a1cc-b036083815f7.jpg)

   Less than:
   
![CP02_2](https://user-images.githubusercontent.com/99417291/155343047-49898dcf-f4e5-4f4a-a5ad-a66638ab1d3c.jpg)

2. Equations of simplified SoP (Sum of the Products) form of the "greater than" function and simplified PoS (Product of the Sums) form of the "less than" function.

![CP02_3](https://user-images.githubusercontent.com/99417291/155347711-27e44584-5941-41e2-a9bf-9ad4b4a50154.jpg)

### 4-bit comparator

1. Listing of VHDL stimulus process from testbench file (`testbench.vhd`) with at least one assert (use BCD codes of your student ID digits as input combinations). Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

   Last two digits of my student ID: **xxxx93**

```vhdl
    p_stimulus : process
    begin
        -- Report a note at the beginning of stimulus process
        report "Stimulus process started" severity note;

        -- First test case ...
        s_b <= "0000"; s_a <= "0000"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '1') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 0000, 0000 FAILED" severity error;
        
        
        -- Second test case ...
        s_b <= "0011"; s_a <= "1100"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 0011, 1100 FAILED" severity error;


        -- Third test case ...
        s_b <= "1010"; s_a <= "0101"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 1010, 0101 FAILED" severity error;


        -- Fourth test case ...
        s_b <= "0111"; s_a <= "1000"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '0') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '1'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 0111, 1000 FAILED" severity error;


        -- Fifth test case - numbers 9 and 3, last from my ID ...
        s_b <= "1001"; s_a <= "0011"; wait for 100 ns;
        -- ... and its expected outputs
        assert ((s_B_greater_A = '1') and
                (s_B_equals_A  = '0') and
                (s_B_less_A    = '0'))
        -- If false, then report an error
        -- If true, then do not report anything
        report "Input combination 1001, 0011 FAILED" severity error;
        -- WRITE OTHER TEST CASES HERE



        -- Report a note at the end of stimulus process
        report "Stimulus process finished" severity note;
        wait; -- Data generation process is suspended forever
    end process p_stimulus;
```

2. Text console screenshot during your simulation, including reports.

![CP02_4](https://user-images.githubusercontent.com/99417291/155349345-6d4903ed-f924-4286-9e3d-f55d73d4eb14.jpg)

3. Link to your public EDA Playground example:

https://www.edaplayground.com/x/V_cQ
