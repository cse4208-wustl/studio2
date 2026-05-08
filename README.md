# Studio 2

## State and Operations on It

In this studio, you will explore program state transition with a simple `enum class` representation for two different systems: days of the week and pressure. You will also implement operators over those enumerated types to print string representations to an output stream and to move from one state to another when allowed by the state transition system.

Some of the ideas and possibly some of the code from this studio may help you get started on [Lab 0](https://github.com/cse4208-wustl/lab0).

## Collaboration

You may complete this studio individually or in a small group.

## Reference

If you need a refresher on the environment setup steps from the previous studio, see [Studio 0](https://github.com/cse4208-wustl/studio0).

The pressure and weekday examples in this studio were discussed in lecture.

## Exercises

Record your answers in `ANSWERS.md` as you work. Include the names of everyone who worked on the studio in your first answer, and number your responses so they are easy to match to the exercises.

1. List the names of the people who worked together on this studio.

2. SSH into `shell.cec.wustl.edu` using your WUSTL Key credentials, then use `qlogin` to log into one of the Linux Lab machines and confirm that the version of `g++` there is correct, as you did in [Studio 0](https://github.com/cse4208-wustl/studio0).

   Clone your `studio2` repo with SSH URL and work inside that cloned directory.

   Create a header file (`weekday.h`) and a source file (`weekday.cpp`) in this repo, with the source file including the header file.

   In he header file, declare an enumerated type, `enum class Weekday`, for the days-of-the-week example discussed in the lecture. Then declare (in the header file) and define (in the source file) a shift operator, `operator<<`, that:

   - takes a reference to an `ostream`
   - takes a `const` reference to a variable of that enumerated type
   - uses a `switch` statement to insert a string corresponding to the variable's value, such as `"Sunday"` for Sunday, into the `ostream`
   - inserts a blank space into the `ostream`
   - returns a reference to that same `ostream`

   Define a `main` function for your program. In it, declare a variable of the `Weekday` enumerated type initialized to one of the enumerated values. Then use the shift operator to insert the variable into `cout` and return a zero value to indicate success.

   Compile and run your program. In your answers, show:

   - the code you wrote for the `main` function
   - the output your program produced

3. Declare and define a **postfix** increment operator, `operator++`, for the `Weekday` enumerated type that uses a `switch` statement to change the variable's state to the next-higher value in the enumeration if there is one. If the variable already has the highest value, the operator should change it to the lowest value, looping around from highest to lowest.

   In `main`, use that operator within a `do while` loop to cycle the variable through all of its possible values, using the shift operator from the previous exercise to print a line to `cout` with each value's corresponding string appearing exactly once.

   Compile and run your program. In your answers, show:

   - the new code you added for the `main` function
   - the output your program produced
   - a note on how you ensured that your operator++ is postfix.

4. Declare and define a **postfix** decrement operator, `operator--`, for the `Weekday` enumerated type that uses a `switch` statement to change the variable's state to the next-lower value in the enumeration if there is one. If the variable already has the lowest value, it should change to the highest value, looping around from lowest to highest.

   In `main`, use that operator within an additional `do while` loop to cycle the variable through the possible values in the reverse order of the previous exercise, again using the shift operator repeatedly to print a line to `cout` with each value's corresponding string appearing exactly once.

   Compile and run your program. In your answers, show:

   - the code you added for the `main` function
   - the output your program produced

5. Create a header file (`pressure.h`) and a source file (`pressure.cpp`) in your repo, with the source file including the header file. 

   Declare an enumerated type, `enum class Pressure`, for the pressure example discussed in the lecture, and then declare and define a shift operator, `operator<<`, that:
   - takes a reference to an `ostream`
   - takes a `const` reference to a variable of that enumerated type
   - uses a `switch` statement to insert a string corresponding to the variable's value, such as `"Low"` for low pressure, into the `ostream`
   - inserts a blank space into the `ostream`
   - returns a reference to that same `ostream`

   In `main`, declare a variable of the `Pressure` enumerated type initialized to one of the enumerated values, then use the shift operator to insert the variable into `cout`.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

6. Declare and define a **prefix** increment operator, `operator++`, for the `Pressure` enumerated type that uses a `switch` statement to change the variable's state to the next-higher value in the enumeration if there is one. If the variable already has the highest value possible, the operator should leave the value unchanged.

   In `main`, use that operator within a `for` loop to cycle a variable through its low, medium, and then high pressure values, using the shift operator from the previous exercise to print a line to `cout` with the corresponding string for each of those values. Do not transition to the pop state.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

7. Declare and define a **prefix** decrement operator, `operator--`, for the `Pressure` enumerated type that uses a `switch` statement to change the variable's state to the next-lower value in the enumeration if there is one. If the variable already has the lowest value possible, theoperator should leave the value unchanged. If the state transition is not allowed (if the pressure is pop), the operator should leave the value unchanged.

   In `main`, add another `for` loop that cycles the previous pressure variable from high down to medium, low, and attempts to cyle down past low. Use the shift operator  to print a line to `cout` with the corresponding string for each of those values.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

8. Add code to the `main` function that tests your implementation of `operator--` when the variable is in the pop state. You your answers, show:
   - the new code you wrote for this exercise
   - the output your program produced
     
## Deliverables

Commit and push all modified and added files to the repo.
