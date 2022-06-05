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
