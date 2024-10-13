# Knights and Knaves

## Project Overview

This project is a Python-based solver for *Knights and Knaves* logic puzzles, based on the classic puzzles by Raymond Smullyan. In these puzzles, each character is either a knight, who always tells the truth, or a knave, who always lies. Given a set of statements made by the characters, the goal is to determine whether each character is a knight or a knave by representing the problem as a propositional logic formula and using an AI to deduce the solution.

The project builds upon a model-checking algorithm to solve these puzzles by encoding the puzzles' conditions into a knowledge base, which is then used to determine the truthfulness of the characters' statements.

## Puzzles Overview

The following puzzles are solved in this project:

- **Puzzle 0**: A single character, A, says: "I am both a knight and a knave."
- **Puzzle 1**: Two characters, A and B.
  - A says: "We are both knaves."
  - B says nothing.
- **Puzzle 2**: Two characters, A and B.
  - A says: "We are the same kind."
  - B says: "We are of different kinds."
- **Puzzle 3**: Three characters, A, B, and C.
  - A says either "I am a knight" or "I am a knave."
  - B says: "A said 'I am a knave.'"
  - B also says: "C is a knave."
  - C says: "A is a knight."

## Project Files

1. **logic.py**: Contains classes to represent logical connectives (e.g., `And`, `Or`, `Not`) and the `model_check` function, which recursively checks whether a logical query is entailed by the knowledge base.
   
2. **puzzle.py**: Defines the propositional symbols for each puzzle (e.g., `AKnight`, `AKnave`, `BKnight`, etc.), as well as the knowledge bases for each puzzle. The main function runs the model-checking algorithm and prints the solution to each puzzle.

## What I Did

### Step 1: Understanding the Logic Framework
I started by examining `logic.py`, which defines several logical constructs and a model-checking algorithm. This gave me an understanding of how to structure the logical expressions required to represent the puzzles.

### Step 2: Building Knowledge Bases
For each puzzle, I encoded the problem's conditions and the statements made by the characters as propositional logic expressions. I updated the knowledge bases (`knowledge0`, `knowledge1`, `knowledge2`, and `knowledge3`) in `puzzle.py` with these logical statements.

- **Puzzle 0**: I represented the logical contradiction of A claiming to be both a knight and a knave.
- **Puzzle 1**: I encoded A's statement about both characters being knaves and used B's silence to help deduce the solution.
- **Puzzle 2**: I modeled A and B's contradictory statements regarding their identities.
- **Puzzle 3**: I incorporated the multiple statements made by characters A, B, and C, including B's reference to A's previous statement.

### Step 3: Testing the Solutions
After encoding the knowledge bases, I ran `python puzzle.py` to verify that the model-checking algorithm could correctly solve each puzzle. The solutions printed out as expected, with the AI deducing whether each character was a knight or a knave based on the logical framework.

## How to Run

1. Ensure that you have Python 3.12 installed.
2. Clone the repo using: 
```bash
git clone https://github.com/musty-ess/Knights-Knaves-AI-Solver-Python.git
```
3. Run the puzzles using: 
```bash
python puzzle.py
```
