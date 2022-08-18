** step1:
* Creating an input file: Input deck (simulation block, checkpoining, restarting.)
* https://www.pflotran.org/documentation/user_guide/how_to/creating_an_input_file.html#creating-an-input-deck-file

** step2:
* Place your input file within a directoy.  pflotran.in and myinputfile.in The first is default name and the second one is given a custom name.

** step3:
* Running command: mpirun -n 1 $PFLOTRAN_DIR/src/pflotran/pflotran -pflotranin myinputfile.in

** step4
* As the simulation is running, output files will be generated. By default, they will be located in the same location as your input file. 
