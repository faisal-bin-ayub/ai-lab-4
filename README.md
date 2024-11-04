Logic.py
This file establishes a framework for symbolic logic, allowing complex logical statements to be constructed, evaluated, and verified. The main purpose is to represent logical statements with symbols (like P or Q) and combine them with logical operators like NOT, AND, OR, IMPLIES, and IFF. This system can evaluate whether certain statements are true based on a model (a set of assumptions or known facts). Key components:

Basic Structure:

The Sentence class is an abstract base class that defines a structure for different types of logical sentences.
Subclasses like Symbol, Not, And, Or, Implication, and Biconditional represent different logical operations.
Evaluation:

Each logical class has an evaluate method that checks if a sentence is true or false based on a provided model (a dictionary where each symbol has a True/False value).
For instance, an And statement is only true if all its parts are true.
Model Checking:

The model_check function tests if a given knowledge base (a set of known facts) entails a query (an additional statement) by recursively exploring all possible truth assignments for the symbols. If the knowledge base implies the query in all cases, it returns True.
In short, logic.py functions as a small logic engine, helpful for simulating reasoning by checking if certain conclusions follow from known facts—important in artificial intelligence.

Clue.py
This code simulates a deduction game similar to Clue. It aims to determine a correct combination of character, room, and weapon by creating logical constraints within a knowledge base:

Setup:

Defines symbols for each character (e.g., ColMustard), room (e.g., ballroom), and weapon (e.g., knife).
Constructs a knowledge base with constraints ensuring that there is exactly one character, one room, and one weapon in the final answer, along with other initial clues that exclude certain possibilities.
Evaluation:

The check_knowledge function evaluates each symbol with model_check, outputting "YES" if a symbol is true, or "MAYBE" if it is undetermined. This reveals the symbols that satisfy the constraints, representing the possible solution.
3. Harry.py
This file implements a logical inference system to evaluate whether a given query is implied by a knowledge base:

Structure:

Defines classes for logical constructs, similar to logic.py (e.g., Symbol, Not, And).
Implements a model_check function that examines all possible truth assignments to determine if the knowledge base supports the truth of the query.
Example:

Sets up a knowledge base about rain, Hagrid, and Dumbledore, then tests if it implies that it is raining, ultimately returning a boolean result for whether the entailment holds.
4. Mastermind Solver
This code represents the logic for solving a simplified version of Mastermind with four colors (red, blue, green, yellow) and four positions:

Constraints:

Each color appears in at least one position, no color appears in more than one position, and each position is occupied by only one color.
Additional constraints prohibit specific placements, such as not allowing blue in the first position or red in the second position.
Output:

It finds the valid combination (e.g., red0, blue1, yellow2, green3) that meets all constraints, solving the puzzle.
5. House Assignment Puzzle
This code solves a logic puzzle involving four individuals—Gilderoy, Pomona, Minerva, and Horace—who must each be assigned to one of four Hogwarts houses (Gryffindor, Hufflepuff, Ravenclaw, Slytherin):

Constraints:
Ensures each person is assigned a unique house with additional specific conditions:
Gilderoy can be in Gryffindor or Ravenclaw, Pomona cannot be in Slytherin, and Minerva must be in Gryffindor.
Output:
Shows valid assignments that meet all conditions, such as Gilderoy in Ravenclaw, Pomona in Hufflepuff, Minerva in Gryffindor, and Horace in Slytherin.
