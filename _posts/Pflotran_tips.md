** step1:
* Creating an input file: Input deck (simulation block, checkpoining, restarting.)
* https://www.pflotran.org/documentation/user_guide/how_to/creating_an_input_file.html#creating-an-input-deck-file

** step2:
* Place your input file within a directoy.  pflotran.in and myinputfile.in The first is default name and the second one is given a custom name.

** step3:
* Running command: mpirun -n 1 $PFLOTRAN_DIR/src/pflotran/pflotran -pflotranin myinputfile.in

** step4
* As the simulation is running, output files will be generated. By default, they will be located in the same location as your input file. 


# Reaction sandbox
* Many PFLOTRAN users have asked for a means of implementing custom kinetic rate expressions for chemistry. The reaction sandbox fulfills this purpose by isolating PFLOTRAN’s chemistry and providing a simplified reaction framework within which the researcher may quickly implement a kinetic reaction without completely learning/understanding PFLOTRAN’s reaction process model. The reaction sandbox also serves as a tool for testing kinetic reactions prior to acceptance and integration within the code.
* Steps to use the reaction sandbox
* step1: copy and rename the source file reaction_sandbox_example.F90
* step2: rename the module, reaction class, and module procedures
* step3: add variables to the reaction class as needed.
* step4: populate module procedures with code that created, reads, initializes, evaluates, and destroys the reaction class.
* step5: add the new reaction class to the reaction sandbox's linked list.

example:
1. clone the pflotran code repository from Bitbucket
2. creat a new reaction network within subrountine SimpleReact() in $PFLOTRAN_DIR/src/pflotran/reaction_sandbox_simple.F90
3. how???
4. Run a 1D column experiment: $PFLOTRAN_DIR/example_problems/reaction_sandbox_simple/pflotran.in
a. Set concentrations within the Initial and Inlet constraints.
b. Run PFLOTRAN: $PFLOTRAN_DIR/src/pflotran/pflotran
c. Plot the results in Excel or matplotlib (reaction_sandbox_simple.py).

https://www.pflotran.org/documentation/user_guide/how_to/installation/linux.html
https://www.osti.gov/servlets/purl/1645365
# Pflotran_short_course
PFLOTRAN provides conventional chemical reaction capability
* aqueous specication
* general (A+B<->C)
* Mineral precipitation-dissolution
* microbiological
* radioactive decay with daughter products
* sorption
* 
