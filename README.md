# NFA-to-DFA-Converter

## Introduction
 Finite Automata (FA) is the simplest state machine to recognize patterns on given input. It
takes the string of symbols as input and then changes its states accordingly to find the
pattern. It has a set of states that have rules to moving each other depending on input
symbol. When the desired pattern found the transaction occurs. Automata accepts when the
input string is proceeded successfully, and it has reached its final state (Introduction to Finite
Automata,2022). In this project, examples of Non-deterministic Automata (NFA)s, which are
used to transmit any number of states for an input, are going to be converted to
Deterministic Automata (DFA)s, which the machine goes to one state only for an input
character and does not accept any null move. In NFA, the input can be epsilon and any state
of NFA can go to multiple states on the same output. On the other hand, DFA does not
accept an input as epsilon and each state of DFA can go only one state on the same output.
Our program is going to take a text file as an input for a NFA, which does not include any
epsilon transition in this project, and produce an output in the same format of the input file
for DFA. 

## Methodology
- Program is based on a single .java file which is named Emir_Aydin_S020843.

- Before reading the input file, a public static class State has been declared outside the
main function. This class keeps the values of states which are going to be initialized
while reading input file. These values are name of the state, Boolean finaal and start as
being final or start state and a HashMap named trans which stores a pair of the
transition character and the ArrayList of next states for the transition.

- At each time when a new state is created, the state is created by the constructor named
State. There are two constructors, and both initialized 2 different pairs as trans which
one has the array of State objects as a value in “0” key, the other has the array of State
objects as a value in “1” key.

- Alongside with the getters and setters for Boolean and name variables, State class has
two important methods as “add_trans” which creates a new HashMap for different
transition character and “get_transition” which returns the transition of the State
object.

- There is a “edit_String” method outside of the main method and this method simply
sorts the given String and eliminates the duplicate character of it. Then it returns the
string.

- In our main method, a new file for input file is created. Also, a string for being updated
to be printed as output at the end and two new ArrayList for NFA and DFA states are
created. Then a Scanner named nfa is declared to read our input file of NFA.

- By using different foreach loops , input file is read by the Scanner object. For each state,
a new state object is created by the name of nfa.next() and they are added into
nfa_states which is the ArrayList of states in NFA. Final and start states are initialized by
updating their Boolean variable of them. For each transition, a new State object as a
next state is added into the ArrayList of State objects which is a pair with the given
transition character.

- After we add the start state as the first element of dfa_states, which is the ArrayList of
states in DFA, by beginning from the start state, we created new states as the union of
next states in given transition character for DFA. If they are not existed already in
dfa_states, they are added on that Arraylist and the for loop continues for these states.

- After we have added all possible states in dfa_states, we start to update dfa string
which has been initialized at the beginning. When the dfa string includes all possible
information for alphabet, states, start state, final state and transitions , it prints the
output in the same format of the input file. 
