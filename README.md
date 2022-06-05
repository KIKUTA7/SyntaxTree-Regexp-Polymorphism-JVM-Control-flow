Draw the syntax tree for the MiniJava program according to the MiniJava grammar from the lecture (chapter on the syntax of programming languages). Use the presentation in the slides for the syntax trees as a guide. You can leave out the boxes around the components, colors are also not required.

int c, h, n;
c = readInt();
h = readInt();
if (h >= 0 || c >= 0) {
    n = 1;
    while (h > 0) {
        n = n * c;
        h = h - 1;
    }
    write(n);
} else {
    write(0);
}
If you are interested in semantics apart from the syntax:
The MiniJava program calculates the number of leaves of a complete [tree] for two whole numbers entered by the user (https://en.wikipedia.org/wiki/Tree_(graph_theory)). The first number c is the number of branches per node, and the second number h the height, so the branching depth. The formula ch c^hc 
h
  is calculated for this, and the result will be displayed on the console at the end. 0 is output for invalid entries.

Note: Make sure that the presentation is clear and you should think twice It is best to give a rough idea of which parts of the program take up how much space in advance. You do not have to arrange all terminals on the same line as on the lecture slides.

Penguins often can be met in sequences or rows. Within these, they do not always stand one behind the other so that (looking from the side) one now and then may hide another. In the following, we are going to define a regular expression by which such series can be described to allow us to decide which series altogether are possible.

For the description, the following rules are applied:

A penguin is denoted by the word Pingu if it looks to the right, and with Ugnip if it looks to the left. In each row, only penguins occur (no polar bears, e.g.).
If a penguin is hidden by the subsequent penguin, a suffix of its word is removed. Examples:
Ping describes a right-looking penguin who is partly hidden.
Ugn describes a left-looking penguin who is severely hidden.
We are only interested in penguins of which at least one third is visible. All others are ignored. This means that the remaining portion must at least contain two characters. i.e. Pi, Pin, Ping, Pingu, Ug, Ugn, Ugni, Ugnip
A row of penguins is written by concatenating their words. Examples with two penguins in a row:
PinguPingu both penguins are fully visible.
UgniPingu the right penguin (Pingu) hides the left penguin (Ugni).
The rightmost penguin is the last in the row and therefore is fully visible.
Each row consists of at least one penguin.
Some more examples with comments following //:


Look at the following program and determine which output the respective calls generate, assuming that only one expression is commented in at a time.

In addition, justify your result by filling out a table with the following columns:

Call (the number given in the comment)
Line number (the line number of the call that is currently being handled)
Static Type (the static type of the object being invoked on)
Compatible methods (the line numbers of all methods that could be called according to the static type)
Statically selected method (the line number of the method that is statically selected)
Signature (the method signature of the statically selected method, e.g. f(B))
Reason (e.g. most specific signature or unique)
Dynamic Type (the dynamic type of the object being invoked on)
Executed at runtime (the line number of the method that will ultimately be executed)
Reason (e.g. static, no dispatch or static Type = dynamic Type)
Output (the output caused by the call)


The following MiniJava program implements the krill division with the rest: We want to split n many of the Antarctic krill caught fairly among p hardworking penguins. So we divide n by p.

The result is output digit by digit, from the most significant digit to the least significant digit. At the end, the remainder of the division is output. This remaining krill is then brought back into the Arctic Ocean because our penguins live ecologically sustainable.

 1 |  int n, p, s, q;
 2 |  n = readInt();
 3 |  p = readInt();
 4 |  s = 100;
 5 |  q = 0;
 6 |  while (s > 0) {
 7 |      if (n < p * s) {
 8 |          write(q);
 9 |          q = 0;
10 |          s = s / 10;
11 |      }
12 |      else {
13 |          n = n - p * s;
14 |          q = q + 1;
15 |      }
16 |  }
17 |  write(n);
Follow the rules from the lecture and translate the Krill Division Program into a MiniJVM Program. i.e. perform the follwing tasks:

Provide a mapping from variables to indices
Generate code of the JVM with symbolic labels
Provide a mapping from symbolic labels to the corresponding code addresses (with real numbers)
The MiniJVM commands from the lecture can be found in the following table:

Type	Command
int Operators:	NEG, ADD, SUB, MUL, DIV, MOD
boolean Operators:	NOT, AND, OR
Comparison Operators:	LESS, LEQ, EQ, NEQ
Loading of Constants:	CONST i, TRUE, FALSE
Memory Operations:	LOAD i, STORE i
Jump Instructions:	JUMP i, FJUMP i
IO-Instructions:	READ, WRITE
Allocation of memory:	ALLOC i
Termination of the Program:    	HALT


The following MiniJava program implements the krill division with the rest: We want to split n many of the Antarctic krill caught fairly among p hardworking penguins. So we divide n by p.

The result is output digit by digit, from the most significant digit to the least significant digit. At the end, the remainder of the division is output. This remaining krill is then brought back into the Arctic Ocean because our penguins live ecologically sustainable.

Draw the control-flow diagram for the krill division MiniJava program according to the rules of the lecture.

 1 |  int n, p, s, q;
 2 |  n = readInt();
 3 |  p = readInt();
 4 |  s = 100;
 5 |  q = 0;
 6 |  while (s > 0) {
 7 |      if (n < p * s) {
 8 |          write(q);
 9 |          q = 0;
10 |          s = s / 10;
11 |      }
12 |      else {
13 |          n = n - p * s;
14 |          q = q + 1;
15 |      }
16 |  }
17 |  write(n);
To the left of the |_-character are the line numbers of the code, to the right of it the actual program text.

1. State table
Prepare a table that contains the values of the variables in the associated program lines, after the respective line has been processed. You can turn to the appropriate Orientate the P task. Specify exactly those lines in the table that contain assignments (name = expr; und name = readInt(); see MiniJava grammar). Enter the number of the respective line on the left and a minus / hyphen for variables that have not yet been assigned a value.

Assume that the user input expected in line 2 has the value 1425, and the value 7 is read in for the user input expected in line 3.

Your table should be structured as follows:

Line number	n	p	s	q
...	...	...	...	...
Make sure that the krill division has successfully divided the number n by p at the end of the program execution. Under your table, note how many of the krill will be brought back into the Arctic Ocean.

Note: Make sure that the presentation is clear and you should think twice preferably in advance roughly which parts of the task take up how much space. You can submit your solution as a PDF, PNG or JPG. Make sure that the text and structure are easy to read and that your solution is correctly oriented (rotated). Otherwise we reserve the right to deduct points.



FAQ
Q: Why is the initial value of s = 100?
A: The initial value of s should be 10n,n in N010 ^ n, n \ in \ N_010 
n
 ,n in N 
0
​
 , where the number of digits in s corresponds to the maximum number of digits in the result. I. E. the given algorithm can calculate results up to 3 digits (still efficient).
 
 
 
