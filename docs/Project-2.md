
# Project 2: Guessing

*Read through the entire project description before beginning.*

This project will consist of five parts with an opportunity to further extend functionality to earn bonus points. Your overall goal is create a guessing game with different game modes and level of difficulties. Each part will develop the game further.

In part 1, you will write a mode where the computer chooses a random number and you need to guess it. In parts 2-4, you will write various guessing algorithms where the computer takes on the role of the guesser and you the role of the number generators. In part 5, you will implement one additional feature from a suggested list and document your design process.

Each part is worth 20 points, and there +3.33 bonus points awarded for each additional feature implemented and documented.

## Collaboration Policy

Students may collaborate on the projects, meaning you're free to seek help from the professor, the internet, or your friends. Any code referenced on internet forums, Stack Overflow, tutorials, or any similar resource that is used to solve a problem should be cited in comments. If two or more students choose to solve a problem together, they are required to write code independently and note all the collaborators. Students cannot use the exact same code (for example, by dictating to each other). Students are not permitted to look at or copy each other’s code or code structure. Students are not permitted to share/send code to others. The official collaboration policy is that two students may discuss a solution together, but the code must be written separately by each student. No plagiarism or copying of solutions is allowed. Project submissions will be run against similarity software. **Violations of this policy will result in a zero on the project.**

*Cite collaboration in `README.md`. There should be no peer collaboration on part 5. Remember to only discuss problems at a high level with your peers.*

## Getting Started

A signifcant amount of starter code has been provided. It will handle the flow of the program, but it is up to you to implement the logic for the different game modes. Carefully read through the starter code to understand how the flow of the program. **You will complete the four functions in the "Student Code" section of `main.py` in parts 1 through 4.**

You are also provided with two utilty functions `validated_input` and `get_random_positive_int`. These are wrappers for the `input` and `random.randint` functions. Review their implementation in `utils.py`. You might need to write your own utility functions to complete part 5 and the bonus. Do so in `main.py` as the grader will use the initial implementation of `utils.py`.

The random number generator is seeded so that it will generate the same sequence of random numbers on every run. Feel free to change `SEED` in `utils.py` to experiment. The grader will use `SEED = 1`.

## Part 1

You will need to implement the function `play_guess_mode`. In this mode, the user will play as "the guesser" and have to guess the number the program randomly generated. Use `validated_input` to ensure the user cannot crash the program by entering invalid input. The number of guesses it takes should be tracked and shown upon success. Here is the running of a valid implementation:

``` text
How do you want to play?
1: as the guesser
2: as the number generator
> 1
Hello Guesser! I, the computer 🤖, am thinking of a number.
> 10
Too low. Try again!
> -10 
> 10.1
> 10.0
Too low. Try again!
> 140893
Too high! Try again!
> 140892
That's it! It took you 4 guess(es).
Play again?
1: Yes
2: No
```

## Part 2

You will need to complete the function `play_generator_mode_easy`. In this mode, the user will play as "the number generator". The computer should randomly guess until it guesses the number inputted by the user. The number of guesses it takes the computer should be tracked and shown upon success.

You can use the `sleep` function from the `time` module to slow down the computer. The following example shows the usage of the `sleep` function:

```python
from time import sleep, ctime
print(f"Start: {ctime()}")
sleep(5)
print(f"End: {ctime()}")
```

When the program is run, it proces the following:

``` text
Start: Mon Jan 31 19:57:44 2022
End: Mon Jan 31 19:57:49 2022
```

Here is the running of a valid implementation:

``` text
How do you want to play?
1: as the guesser
2: as the number generator
> 2
Hello Human! Select a difficulty.
1: Easy
2: Medium
3: Hard
> 1
Easy mode selected!
Enter a positive integer! I am not looking! 🙈
> 841236
🤖: 140892
🤖: 596854
🤖: 888599
🤖: 841236
🤖 wins! It took 4 guess(es).
Play again?
1: Yes
2: No
```

## Part 3

You will need to complete the function `play_generator_mode_medium`. In this mode, the user will play as "the number generator". The computer should intelligently guess in a linearly until overshooting and then reverse direction using a lower magnitude. See the output below for an example of the strategy. The number of guesses it takes the computer should be tracked and shown upon success.

You may use the provided helper function `human_responds` to inform the user if they were too high or show. Be sure to read the docstring to see how this function works. Note that the computer overshoots the guess then `abs(previous_response - current_response) == 2`.

Here is the running of a valid implementation:

``` text
How do you want to play?
1: as the guesser
2: as the number generator
> 2
Hello Human! Select a difficulty.
1: Easy
2: Medium
3: Hard
> 2
Medium mode selected!
Enter a positive integer! I am not looking! 🙈
> 168682
🤖: 140892
👨: Too low!
🤖: 150892
👨: Too low!
🤖: 160892
👨: Too low!
🤖: 170892
👨: Too High!
🤖: 169892
👨: Too High!
🤖: 168892
👨: Too High!
🤖: 167892
👨: Too low!
🤖: 167992
👨: Too low!
🤖: 168092
👨: Too low!
🤖: 168192
👨: Too low!
🤖: 168292
👨: Too low!
🤖: 168392
👨: Too low!
🤖: 168492
👨: Too low!
🤖: 168592
👨: Too low!
🤖: 168692
👨: Too High!
🤖: 168682
👨: That's it!
🤖 wins! It took 16 guess(es).
Play again?
1: Yes
2: No
```

## Part 4

You will need to complete the function `play_generator_mode_hard`. In this mode, the user will play as "the number generator". The computer should intelligently guess in a using a bisection search. See the output below for an example of the strategy. The number of guesses it takes the computer should be tracked and shown upon success.

Note that initially the computer will need to start with a linear search to find low and high values in order to begin the bisection search.

Here is the running of a valid implementation:

``` text
How do you want to play?
1: as the guesser
2: as the number generator
> 2
Hello Human! Select a difficulty.
1: Easy
2: Medium
3: Hard
> 3
Hard mode selected
Enter a positive integer! I am not looking! 🙈
> 168682
🤖: 140892
👨: Too low!
🤖: 240892
👨: Too High!
🤖: 190892
👨: Too High!
🤖: 165892
👨: Too low!
🤖: 178392
👨: Too High!
🤖: 172142
👨: Too High!
🤖: 169017
👨: Too High!
🤖: 167454
👨: Too low!
🤖: 168235
👨: Too low!
🤖: 168626
👨: Too low!
🤖: 168821
👨: Too High!
🤖: 168723
👨: Too High!
🤖: 168674
👨: Too low!
🤖: 168698
👨: Too High!
🤖: 168686
👨: Too High!
🤖: 168680
👨: Too low!
🤖: 168683
👨: Too High!
🤖: 168681
👨: Too low!
🤖: 168682
👨: That's it!
🤖 wins! It took 19 guess(es)
Play again?
1: Yes
2: No
```

Note that the (modified) linear search actually performed better in this case.

## Part 5

**No peer collaboration should take place on part 5 since there are many ways this task can be completed.** Speak to me if you are having difficulty.

You will need to implement an additional piece of functionalty and document how you implmented it in `README.md`. This is a markdown file, which is a common file format for documentation. Watch [Markdown Crash Course](https://youtu.be/HUBNt18RFbo?t=331) for a brief overview on how to format markdown document. You may choose to implement one of the following:

- Implement a ***player-vs-player** mode where one user enters a number without the other play looking, hides it, and then prompts opponent
- Implement an option where the user can limit the number of guess until the guesser loses
  - This limit should be adjustable by the user and be able to be turned on and off
- Implement an option where the user specifies a random in which the numbers will occur
  - This range should be adjustable by the user and be able to be turned on and off
- Allow float and negative values in all game modes
  - You might want to consider rounding to decimal places
  - The computer and human should both be able to set these values as the number-to-guess and guess with them.

Documentation of the feature should be at least two paragraphs explaining your thought process, what functions were modified, and how so. Include code snippets.

## Bonus

Copy and paste over the contents of `main.py` to the file named `bonus.py`. Complete the other functionalities from part 5. These should also be thoroughly documented in the README to receive full bonus points. The bonus will be graded separately, but should maintain all original functionality.

## Closing Remarks

Any edits or clarifications to the project will be announced in class and shown in the changelog below. Good luck and have fun!

### Changelog
