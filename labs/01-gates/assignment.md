# Lab 1: Ondřej Nesvadba

### De Morgan's laws

1. Equations of all three versions of logic function f(c,b,a):

![CP01_1](https://user-images.githubusercontent.com/99417291/154483889-db1cedf8-1252-420a-ac26-636d41f8234b.jpg)

2. Listing of VHDL architecture from design file (`design.vhd`) for all three functions. Always use syntax highlighting, meaningful comments, and follow VHDL guidelines:

```vhdl
architecture dataflow of demorgan is
begin
    f_org_o  <= (not(b_i) and a_i) or (not(c_i) and not(b_i));
    f_nand_o <= not(not(not(b_i) and a_i) and not(not(c_i) and not(b_i)))
    f_nor_o  <= not(b_i or not(a_i)) or not(c_i or b_i)
end architecture dataflow;
```

3. Complete table with logic functions' values:

| **c** | **b** |**a** | **f(c,b,a)_ORG** | **f(c,b,a)_NAND** | **f(c,b,a)_NOR** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 1 | 1 | 1 |
| 0 | 0 | 1 | 1 | 1 | 1 |
| 0 | 1 | 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 1 | 0 | 0 | 0 | 0 |
| 1 | 1 | 1 | 0 | 0 | 0 |

### Distributive laws

1. Screenshot with simulated time waveforms. Always display all inputs and outputs (display the inputs at the top of the image, the outputs below them) at the appropriate time scale!

   [CP01_3](https://user-images.githubusercontent.com/99417291/154487513-aa998943-5fa8-448a-99da-0cf72402c6ab.jpg)
![CP01_3](https://user-images.githubusercontent.com/99417291/154487751-0532a5ae-00a1-4b1a-8831-d65ab41d246a.jpg)


2. Link to your public EDA Playground example:

   [https://www.edaplayground.com/x/XCYT](https://www.edaplayground.com/x/XCYT)
