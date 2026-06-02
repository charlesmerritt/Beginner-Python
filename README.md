# Beginner Python Projects

This repository contains small Python projects for practicing beginner Python skills:

- variables and strings
- functions
- command-line arguments
- lists and loops
- file input/output
- dictionaries / JSON-like data
- third-party packages
- Git and GitHub workflow

## Setup and installation links

If you are new to Python development, start here:

- [Install Python](https://www.python.org/downloads/)
- [Python beginner setup guide](https://docs.python.org/3/using/index.html)
- [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [Set up Git with GitHub](https://docs.github.com/en/get-started/git-basics/set-up-git)
- [Install uv](https://docs.astral.sh/uv/getting-started/installation/)
- [Install scikit-learn](https://scikit-learn.org/stable/install.html)
- [scikit-learn getting started guide](https://scikit-learn.org/stable/getting_started.html)

Useful commands:

```bash
# Check that Python is installed
python --version

# Check that Git is installed
git --version

# Check that uv is installed
uv --version
```

On some computers, you may need to use `python3` instead of `python`.

## Suggested folder structure

Each project should live in its own folder:

```text
Beginner-Python/
├── README.md
├── Names/
│   └── birthday.py
├── Wordsearch/
│   ├── solver.py
│   ├── wordpuzzle.txt
│   ├── testpuzzle.txt
│   └── wordbank.txt
└── Scikit-Learn/
    └── sklearn_intro.py
```

## Running Python files

From the main repository folder, run a Python file like this:

```bash
python Names/birthday.py
```

Or, if the program uses command-line arguments:

```bash
python Names/birthday.py Andrew 2005-04-12
```

With `uv`, you can also run:

```bash
uv run python Names/birthday.py Andrew 2005-04-12
```

---

# Project 1: Names & Birthdays

## Goal

Create a small program that takes a person's name and birthday, then prints a greeting with their age.

## Skills practiced

- variables
- strings
- f-strings
- functions
- command-line arguments
- basic date handling

## Instructions

Create a file named:

```text
Names/birthday.py
```

Your program should:

1. Read a name from the command line.
2. Read a birthday from the command line.
3. Use a function to calculate the person's age.
4. Print a message using an f-string.

Use this birthday format:

```text
YYYY-MM-DD
```

Example birthday:

```text
2005-04-12
```

## Example command

```bash
python Names/birthday.py Andrew 2005-04-12
```

## Example output

```text
Hello Andrew! You are 20 years old!
```

Your output may show a different age depending on the current date.

## Done when

- The program can be run from the command line.
- The name is stored in a variable.
- The birthday is stored in a variable.
- A function returns or calculates the age.
- The final message uses an f-string.

---

# Project 2: Wordsearch

## Goal

Given a wordsearch puzzle and a list of words, write a program that finds each word in the puzzle.

## Skills practiced

- lists
- loops
- strings
- dictionaries
- file input/output
- problem solving

## Files

The `Wordsearch/` folder contains:

```text
Wordsearch/wordpuzzle.txt
Wordsearch/testpuzzle.txt
Wordsearch/wordbank.txt
```

- `wordpuzzle.txt` contains the puzzle grid.
- `testpuzzle.txt` contains a smaller or alternate puzzle for testing.
- `wordbank.txt` contains the words to search for.

## Instructions

Create a file named:

```text
Wordsearch/solver.py
```

Try to implement this function:

```python
def solve(puzzle, wordlist):
    # Return a dictionary describing where each word was found.
    pass
```

Start with these directions first:

- left to right
- right to left
- top to bottom
- bottom to top

After those work, try the diagonals.

## Coordinate format

Use zero-based `[row, column]` coordinates.

For example, the first letter in the top-left corner is:

```python
[0, 0]
```

The second letter in the top row is:

```python
[0, 1]
```

The first letter in the second row is:

```python
[1, 0]
```

## Example return value

Your `solve` function should return a dictionary like this:

```python
{
    "CAT": {
        "positions": [[0, 6], [1, 5], [2, 4]],
        "direction": "down-left"
    },
    "RED": {
        "positions": [[2, 0], [1, 0], [0, 0]],
        "direction": "up"
    }
}
```

The exact positions above are only examples. Your program should return the real positions from the puzzle.

## Example command

```bash
python Wordsearch/solver.py
```

## Done when

- The program reads the puzzle file.
- The program reads the word bank file.
- Each word from the word bank appears in the result.
- Each result includes the word's positions.
- Each result includes the word's direction.

You can assume every word in the word bank appears somewhere in the puzzle.

This project may be challenging. Ask for help if you get stuck, but try not to use tools that give you the full solution immediately.

---

# Project 3: Scikit-learn Intro

## Goal

Complete a basic machine learning demo using the `scikit-learn` package.

## Skills practiced

- installing third-party packages
- importing libraries
- loading sample data
- training a simple model
- printing results

## Setup with uv

From the repository folder, run:

```bash
uv init
uv add scikit-learn
```

If `uv init` says the project is already initialized, that is okay.

## Instructions

Create a file named:

```text
Scikit-Learn/sklearn_intro.py
```

Your program should:

1. Load the Iris dataset from scikit-learn.
2. Split the data into training and test data.
3. Train a simple model.
4. Print the model's accuracy.

## Example starter code

```python
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier

iris = load_iris()

X_train, X_test, y_train, y_test = train_test_split(
    iris.data,
    iris.target,
    test_size=0.2,
    random_state=42,
)

model = KNeighborsClassifier(n_neighbors=3)
model.fit(X_train, y_train)

accuracy = model.score(X_test, y_test)
print(f"Accuracy: {accuracy}")
```

## Example command

```bash
uv run python Scikit-Learn/sklearn_intro.py
```

## Example output

```text
Accuracy: 1.0
```

Your accuracy may be slightly different depending on your code.

## Done when

- `scikit-learn` is installed.
- Your Python file runs without errors.
- The program trains a model.
- The program prints an accuracy score.

---

# Project 4: Git

## Goal

Practice organizing your work, committing changes, and pushing your code to GitHub.

## Skills practiced

- creating folders
- checking file status
- staging files
- committing files
- pushing to a remote repository

## Instructions

Take all of the projects you have completed and place them in their own folders.

Then commit and push your work.

## Useful Git commands

```bash
# See which files have changed
git status

# Add all changed files
git add .

# Commit your work
git commit -m "Add beginner Python projects"

# Push your commit to GitHub
git push
```

Make sure you are connected to the remote repository:

```text
https://github.com/charlesmerritt/Beginner-Python
```

You can check your remote with:

```bash
git remote -v
```

## Done when

- Each project is in its own folder.
- Each folder contains the files for that project.
- `git status` shows the files you expect.
- Your work has been committed.
- Your commit has been pushed to GitHub.
