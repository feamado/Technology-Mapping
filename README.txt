Technology Mapping Program Excursion 2
Group:
Fernando E. Amado-Pupo
Gonzalo Gonzalez
Evan Espino

Outputs minimum cost of boolean function if it were to be made with NAND-NOT gates and/or complex gates that have NAND-NOT gates from a library given by the professor.
Outputs a converted NAND-NOT gate net list using cheapest components with which it could be manufactured

Running program asks for the complete file name ex "Boolean_Netlist.txt" works.  "boolean_netlist.txt" ,or "boolean_netlist", do not work
file will only be read if it exists and the complete filename is written



Outputs in the output netlist come in the format where P is the Output variable and all other nodes are denoted by chronological variables of t(ex:t1,t2,t3....)
Min cost of a specific configuration is denoted underneath printed output of in the form
Output Netlist 3
Min cost : 28
This tells the user the minimal cost of the corresponding output configuration.

If the outputs in the netlist say

G= NOT T1  //(Output Netlist 1)
F = AND t2 t3(Output  Netlist 2)

The output of F will be printed before G but it will be denoted as input 2, corresponding to it being below the G in the input netlist.
for example this shows a hypoyhetical console output with .... representing information that would otherwise be filled in in the program, but is ommitted for simplicity in this example.
Output Netlist 2 // corresponding to F = AND t2 t3
Min cost: 12 
t1 =...
t2 = ...
t3 = ...
.....
....
...
P = .... //Output Node for output netlist always denoted by P

Output Netlist 1 // Corresponding to G = NOT T1

t1 = .....
t2 = ......
t3 = ....
t4 = ....

...

P = .....
Netlists:

Valid Sample Netlists are provided in ZIP file.
For user Netlists the following rules apply
Program is configured only for netlists in which input equations start with t and end with a number.
Ex of a viable netlist

a INPUT
b INPUT
c INPUT
D OUTPUT
E OUTPUT
F OUTPUT
t1 = OR a AND c b
t2 = AND b OR a c
D = t1
E = t2
F = NOT t1


so input equations must always be denoted with a t.


If an input netlist is incomplete, such as a case in which there are not enough inputs and say, a NAND gate is left with one or two missing arguments, the program will accommodate this error by assuming the lonely NAND
gate is pointing to an input where there is none.

If the user did not intend to put an input there they must check their configuration and fix the equation themselves so that all gates have the correct number of respective inputs.

Equals sign "=" must be placed in front  of a given equation ex. t1 = OR a AND c b

Multiple functions of the form NOT/AND/OR are allowed as long as they are properly written with each function at each step having the correct number of inputs i.e
t1 = AND a b is valid
t2 = AND a OR b c is valid
t3 = NOT a b is not valid
t4 = AND a is not valid
t5 = OR NOT A NOT B is valid
t6 = AND OR a b OR c d is valid
Multiple Outputs are allowed as in the example netlist as long as they follow all prior formatting rules
