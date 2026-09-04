# Assignment 4: Score Analyzer

## Description

In this assignment, you will design and implement a Python program that processes a collection of numeric scores, classifies each score, maintains information about the scores as they are processed, and produces a final summary.

This assignment builds on the control-flow concepts introduced in the previous assignments and lectures. You now have multiple tools for controlling execution, including decisions, compound Boolean expressions, repetition, and exception handling.

You will **not** be told in the assignment which control structure to use for each part of the problem.

Part of the assignment is determining which programming structures best represent the required behavior. You are expected to apply the principles from the lectures and course notes when making those decisions and you will be graded on those decisions.

Your program will be evaluated not only on whether it produces the correct output, but also on whether your control-flow choices are clear, appropriate, readable, and maintainable as per course lectures.

The primary programming concepts in this assignment include:

- compound Boolean expressions;
- multi-way decision-making;
- nested decision-making where appropriate;
- repetition;
- definite and indefinite iteration;
- counters and accumulators;
- changing program state across iterations;
- numeric input conversion;
- exception handling;
- validation;
- boundary conditions;
- systematic testing; and
- incremental software development.

## Learning Objectives

By completing this assignment, you should be able to:

- analyze a problem and determine what behavior must repeat;
- select repetition structures based on the nature of the problem;
- distinguish repetition with a predetermined scope from repetition controlled by changing conditions;
- use changing state to control and reason about repetition;
- use counters and accumulators to preserve information across iterations;
- construct and evaluate compound Boolean expressions;
- organize multiple decisions clearly;
- use nesting only where it improves the structure of the program;
- handle a specific failed operation using appropriately scoped exception handling;
- reason about loop termination and boundary conditions;
- test multiple execution paths and repetition cases;
- develop software incrementally using meaningful Git commits;
- use generative AI while retaining responsibility for design and verification; and
- create and document the required files for a small software project.

## Background

Before beginning this assignment, you should have:

- completed **Assignment 1: Getting Started**;
- completed **Assignment 2: First Code**;
- completed **Assignment 3: Shipping Cost Calculator**;
- completed the **Decision-Making I** material;
- completed the **Flow Control: Decision Making Part II** material;
- completed the **Flow Control: Repetition Part I** material;
- reviewed the [Best Practices for Procedural Programming](https://katrompas.accprofessors.com/best-practice-procedural-programming);
- reviewed the course [Commenting Guidelines](https://katrompas.accprofessors.com/commenting);
- reviewed the [.gitignore guidelines](https://katrompas.accprofessors.com/gitignore-guidelines);
- reviewed the course [README Guidelines](https://katrompas.accprofessors.com/readme-guidelines); and
- reviewed the course [commit guidelines](https://katrompas.accprofessors.com/committing).

Beginning with this assignment, you are expected to make more of the development and project-organization decisions yourself.

## Starter Repository

Your repository initially contains only:

```text
ASSIGNMENT.md
ESSAY.md
main.py
```

Unlike the previous assignment, `README.md` and `.gitignore` are **not provided**.

You are responsible for creating both files and making sure they are appropriate for the project.

The supplied `main.py` contains the basic program structure:

```python
# don't forget your comment header here


def main():
    # don't forget your function header here

    # Erase the pass and write your program here
    pass


if __name__ == "__main__":
    main()
```

Write your program inside `main()` by replacing the `pass` statement.

Do not remove the supplied `main()` structure.

## Program Requirements

Write a program that analyzes a collection of course scores.

The program must:

1. begin by displaying exactly:

   ```text
   Score Analyzer
   ```

2. after displaying the program title, the program must ask how many scores will be processed;

3. reject an invalid number of scores and continue asking until a valid value is entered;

4. process exactly the requested number of scores;

5. classify each score using the grading rules below;

6. display the letter grade for each score;

7. maintain the information necessary to calculate the final summary;

8. calculate the average score;

9. report the number of passing and failing scores;

10. classify the overall performance of the collection according to the rules below; and

11. display the completed summary.

The program output must conform to the examples given below **exactly**. The design of the control flow is your responsibility.

## Number of Scores

After displaying the program title, the program must ask:

```text
How many scores will be entered:
```

The number of scores must be a **whole number greater than zero**.

If the user enters a value that cannot be interpreted as an integer, or enters an integer less than or equal to zero, display:

```text
Error: enter a whole number greater than zero.
```

Then allow the user to try again.

The program must continue until a valid number of scores has been obtained.

The prompt must contain **one space** after the colon before the user's input.

For example:

```text
Score Analyzer
How many scores will be entered: dog
Error: enter a whole number greater than zero.
How many scores will be entered: 0
Error: enter a whole number greater than zero.
How many scores will be entered: -3
Error: enter a whole number greater than zero.
How many scores will be entered: 3
```

The program must recover from the invalid entries and continue normally.

## Score Input

After a valid number of scores has been obtained, ask for exactly that many scores.

Number the prompts beginning with 1:

```text
Enter score 1:
Enter score 2:
Enter score 3:
```

and continue as necessary.

Each score prompt must contain **one space** after the colon before the user's input.

Scores may contain decimal values.

For this assignment, once the number of scores has been accepted, you may assume that each score entered is numeric and is within the valid range of **0 through 100 inclusive**.

Handling nonnumeric or out-of-range individual score values is not required for this assignment.

## Grade Classification

Each score must be classified according to the following rules:

| Score | Grade |
| --- | --- |
| 90 through 100 | A |
| 80 through less than 90 | B |
| 70 through less than 80 | C |
| 60 through less than 70 | D |
| Less than 60 | F |

After each score is entered, display its grade using exactly:

```text
Grade: A
```

with the appropriate letter substituted.

Important boundary behavior includes:

- exactly `90` is an A;
- exactly `80` is a B;
- exactly `70` is a C;
- exactly `60` is a D; and
- anything below `60` is an F.

## Passing and Failing Scores

For this assignment, a score of **70 or greater** is considered passing.

A score below 70 is considered failing.

As the scores are processed, maintain the information necessary to report the total number of passing and failing scores.

## Average

After all scores have been processed, calculate the arithmetic mean of the scores.

Display the average using exactly two digits after the decimal point.

For example:

```text
Average: 82.67
```

## Overall Performance

After all scores have been processed, classify the overall performance of the collection using the average and the number of failing scores.

### Excellent

Display:

```text
Performance: Excellent
```

when:

- the average is at least 90; **and**
- there are no failing scores.

### At Risk

Display:

```text
Performance: At Risk
```

when either:

- the average is below 70; **or**
- more than half of the scores are failing.

### Satisfactory

If neither of the previous classifications applies, display:

```text
Performance: Satisfactory
```

These rules are part of the program specification. You are responsible for translating them into clear and correct program logic.

## Final Summary

After all scores have been processed, display the final summary in this exact order:

```text
Scores processed: <number>
Average: <average>
Passing scores: <number>
Failing scores: <number>
Performance: <classification>
```

The average must contain exactly two digits after the decimal point.

For example:

```text
Scores processed: 3
Average: 79.33
Passing scores: 2
Failing scores: 1
Performance: Satisfactory
```

Do not display the final summary until all requested scores have been processed.

## Complete Example

A complete execution might look like:

```text
Score Analyzer
How many scores will be entered: 3
Enter score 1: 95
Grade: A
Enter score 2: 82
Grade: B
Enter score 3: 61
Grade: D
Scores processed: 3
Average: 79.33
Passing scores: 2
Failing scores: 1
Performance: Satisfactory
```

The required prompts, labels, capitalization, and output order are part of the program interface and should match the specification.

## Programming and Control-Flow Standards

You have now learned multiple ways to control program execution.

You are responsible for selecting structures that clearly represent the behavior of the problem.

Your program will be evaluated on whether:

- repetition structures appropriately represent the kind of repetition being performed;
- loop conditions clearly communicate why repetition continues;
- loop state is initialized and updated correctly;
- decision structures are clear and appropriately organized;
- compound conditions accurately express the required logic;
- nesting is used only when it improves clarity;
- nesting remains reasonably shallow;
- exception handling is narrow, specific, and associated with a single attempted operation; and
- the resulting program is simple enough to understand and maintain.

As discussed in class, control structures should generally not be nested more than **three or four levels deep**. If your solution requires deeper nesting, reconsider the design.

**The fact that two different control structures can be made to produce the same output does not mean that they are equally good solutions.**

Your implementation should reflect the principles discussed in the lectures and course notes.

## Exception-Handling Standards

Exception handling must follow the standards introduced in class.

A `try` block should attempt **one specific operation with one understood failure mode**.

Do not place large sections of program logic inside a `try` block.

Do not wrap the entire program, a complete loop body, or the entire `main()` function in exception handling.

Catch the specific exception associated with the operation you are attempting to handle.

Bare exception handlers such as:

```python
except:
```

should not be used.

Exception handling is not a substitute for ordinary Boolean logic.

If the program already has enough information to make an ordinary decision, use normal decision-making logic.

Python sometimes uses exceptions as part of ordinary program control in situations where other languages may not. This does **not** mean exceptions should be used whenever an `if` statement could be used. Use exception handling only where it clearly represents a failed operation that should be handled.

## Repetition Standards

Choose repetition structures based on the nature of the problem.

A loop should clearly communicate **why it continues**.

Do not use a repetition structure merely because you know how to force it to work.

Purposeful infinite loops such as:

```python
while True:
```

are not permitted in this assignment.

The following are also not permitted:

```text
break
continue
```

Do not hide the real stopping condition inside the loop body when it belongs in the loop header.

There may be legitimate uses for these techniques in software engineering, but they are outside the scope of this assignment. First master structured repetition and the underlying theory.

## Programming Constraints

Use programming concepts introduced in the course.

The following should **not** be used in this assignment:

- additional user-defined functions;
- lists;
- dictionaries;
- file input/output;
- external libraries;
- purposeful infinite loops such as `while True`;
- `break`; or
- `continue`.

Generative AI may suggest techniques outside the scope of this assignment. Do not use unfamiliar or prohibited techniques simply because AI generated them.

**You are responsible for understanding every part of the submitted program.**

## Code Quality

You will be evaluated on the readability, simplicity, structure, and quality of your code.

A program that merely produces the correct output is not necessarily a good program.

Use AI to help you examine and improve your solution, but do not accept unnecessary complexity or techniques outside the scope of the course.

Prefer clear, direct, well-structured code that accurately expresses the algorithm.

The [Best Practices for Procedural Programming](https://katrompas.accprofessors.com/best-practice-procedural-programming) apply.

## Development Process

Develop the program incrementally.

**Do not write the entire solution first and then commit the finished program.**

Your repository history must contain **at least eight meaningful student-created program-development commits** showing the program being developed incrementally.

Eight is the minimum, not the target.

A meaningful commit represents a coherent improvement to the working program.

You are responsible for:

- determining appropriate commit boundaries;
- testing your work before committing;
- writing clear, descriptive commit messages;
- pushing your work regularly;
- reviewing Classroom 50 feedback after pushes; and
- correcting problems as they are discovered.

Each meaningful commit must follow the course [commit guidelines](https://katrompas.accprofessors.com/committing).

Commits consisting only of formatting changes, arbitrary fragments of unfinished work, or changes made solely to increase the commit count are **not meaningful** development commits.

Changes made only to:

```text
README.md
ESSAY.md
.gitignore
```

do **not** count toward the eight required program-development commits.

You may make more than eight development commits. Eight is the minimum, not the target.

## Generative AI

Use of generative AI is required as part of the development process.

You may use the generative AI system of your choice as a:

- tutor;
- programming partner;
- critic;
- debugging assistant;
- source of explanations;
- testing assistant; or
- aid in reasoning about algorithms and control flow.

You may show the AI the complete assignment.

However, you are responsible for making the final engineering decisions.

In particular, do not assume that a control structure is appropriate simply because an AI generated working code that uses it.

Ask whether the resulting program reflects the principles taught in class.

You remain responsible for:

- understanding all submitted code;
- understanding why each loop eventually terminates;
- understanding why each decision follows the correct path;
- understanding the Boolean conditions used;
- verifying AI-generated logic;
- testing boundaries;
- identifying incorrect assumptions; and
- making the final programming decisions.

Your use and verification of AI will be documented in `ESSAY.md`.

## Testing

Testing is part of the development process.

Your program contains multiple control-flow paths and repeated behavior. A single successful execution is not sufficient evidence that the program is correct.

At minimum, your testing should include:

- a valid count of one score;
- a valid count of several scores;
- a nonnumeric score-count entry;
- zero as the number of scores;
- a negative number of scores;
- scores slightly below, exactly at, and slightly above the grade boundaries at 60, 70, 80, and 90;
- a set of scores producing `Excellent`;
- a set of scores producing `Satisfactory`;
- a set of scores producing `At Risk` because the average is below 70 while no more than half of the scores are failing;
- a set of scores producing `At Risk` because more than half of the scores are failing while the average is at least 70;
- decimal scores; and
- verification that the final counts and average are correct.

Think about what each test is intended to demonstrate before running it.

Classroom 50 will also test the program whenever you push your work.

The autograder score represents **tests passed, not your assignment grade**.

Passing all automated tests does not demonstrate that your code uses good control-flow structures, follows course standards, contains meaningful Git history, or demonstrates understanding. Those aspects are evaluated separately.

## Code Documentation

Your program must follow the course [Commenting Guidelines](https://katrompas.accprofessors.com/commenting).

Update `main.py` so that it contains:

- the required file comment header; and
- the required function comment header for `main()`.

Do not add comments that merely restate obvious individual lines of code.

Before submission, remove:

- debugging statements;
- commented-out code;
- temporary code; and
- unnecessary comments.

## `README.md`

Create a new file named:

```text
README.md
```

in the root of the repository.

Complete it according to the course [README Guidelines](https://katrompas.accprofessors.com/readme-guidelines).

Unlike Assignment 3, the README structure is no longer provided for you.

You are responsible for creating a professional README containing the required information and Markdown structure.

The README must accurately document the program you actually submitted.

## `.gitignore`

Create an appropriate `.gitignore` file for this Python project.

You have already worked with a `.gitignore` file in previous assignments. Use that experience to determine what this project should ignore.

The `.gitignore` file must be present in the root of the repository before submission.

## `ESSAY.md`

Complete the supplied `ESSAY.md`.

The file contains five questions concerning:

- your use of generative AI;
- your choice of repetition structures;
- how one of your loops changes state and eventually terminates;
- your use and structure of exception handling; and
- how you tested or verified your control-flow decisions.

Each question is worth **2 points**, for a total of **10 points**.

Your answers must demonstrate depth of thought, include specific examples from your work, and provide enough detail to show actual understanding and engagement with the assignment.

Short, vague, or trivial answers will not receive full credit.

## Final Review and Submission

Before submitting the assignment, verify the complete repository.

### 1. Run the program

Run the program locally and test it one final time.

```bash
python3 main.py
```

Depending on your system configuration, the command may instead be:

```bash
python main.py
```

### 2. Check repository status

Run:

```bash
git status
```

Your working tree should be clean.

### 3. Review your development history

Run:

```bash
git log --oneline
```

Verify that your history contains at least eight meaningful program-development commits and that the history reflects incremental development.

### 4. Review the project structure

Confirm that the repository contains:

```text
ASSIGNMENT.md
ESSAY.md
main.py
README.md
.gitignore
```

### 5. Review GitHub

Open the repository on GitHub and confirm that all final work has been pushed.

Review the rendered `README.md` and `ESSAY.md` and make sure both are properly formatted.

### 6. Review Classroom 50 Results in the Feedback on GitHub

Review the final Classroom 50 autograding results and Feedback pull request.

Remember:

> **Autograder points represent tests passed, not the assignment grade.**

### 7. Submit through Blackboard

Copy the normal HTTPS URL for your GitHub repository and submit that URL in the Blackboard assignment.
