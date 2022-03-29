# Project 5: Analysis

In project 5, you will run four sorting programs to determine which algorithms they use.

## Instructions

On [Replit](https://replit.com/~), you are provided four programs, `sort1`, `sort2`, `sort3`, and `sort4`. Each of these programs implements a different sorting algorithm: bogosort, bubble sort, selection sort, or merge sort (though not necessarily in that order). Your task is to determine which sorting algorithm is used by each file.

- The programs are compiled C programs, so you will not be able to view the source code. To assess which sort implements which algorithm, run the programs on different lists of values.
- Multiple `.txt` files are provided. These files contain `n` values, either reversed, shuffled, or sorted.
  - For example, `reversed10000.txt` contains 10000 lines of numbers that are reversed from `10000`, while  `random10000.txt` contains 10000 lines of numbers that are in random order.
- To run the sorts on the text files, in the shell tab, run `./[program_name] [text_file.txt]`. 
  - For example, `./sort1 reversed10000.txt`.
  - If an alogrithm is taking too long to complete, you can interrupt the program by pressing `Ctrl + C` (Windows) or `Cmd + C` (macOS).
- It will be necessary to time your sorts. To do so, run `time ./[sort_file] [text_file.txt]`.
  - For example, you could run `time ./sort1 reversed10000.txt` to run `sort1` on 10000 reversed numbers. At the end of your terminal's output, you can look at thr `real` time to see how much time actually elapsed while running the program.

## Recommendations

- Consider the best and worst case running times for each algorithms.
- Consider how each algorithm performs under various conditions:
  - The list is already sorted
  - The list is reversed
  - The list is shuffled.
- It is recommend you work through the various algorithms by hand to understand how the sorting takes places.
  - [https://visualgo.net/en/sorting](https://visualgo.net/en/sorting) is a good website to run various experiments. You are able to change the initial list to and watch the program step through the algorithm.

## Submission

See [https://docs.google.com/document/d/1atdWLk4FSQvl3HZ05Lrif1qAHv3yyRSOaM7ukG1EZP4/copy](https://docs.google.com/document/d/1atdWLk4FSQvl3HZ05Lrif1qAHv3yyRSOaM7ukG1EZP4/copy). You may convert the document to LaTeX if desired.

Download and submit a PDF on MyFire.

## Grading

The `Experiments` section is worth 20 points. Full credit requires evidence of various experiments of each sorting programming with results provided in an organized manner.

The `Answers` section is worth 80 points:

- 5 points for each correctly identified algorithm
- 15 points for each justification.

A fully justified answer will use the data from the experiments, demonstrate understanding of each algorithm's implementation, use the Big-Oh and/or big-Omega running time, and explain how you arrived at your answer.

There is no bonus for this project.
