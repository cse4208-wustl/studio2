# Studio 2

## State and Operations on It

In this studio, you will explore how to represent program state using a simple `enum class` representation for two different kinds of state transition systems: days of the week and pressure. You will also implement operators over those enumerated types to print string representations to an output stream and to move from one state to another when allowed by the state transition system.

Some of the ideas and possibly some of the code from this studio may help you get started on [Lab 0](https://github.com/cse4208-wustl/lab0).

## Collaboration

You may complete this studio individually or in a small group.

## Reference

If you need a refresher on the environment setup steps from the previous studio, see [Studio 0](https://github.com/cse4208-wustl/studio0).

The pressure and weekday examples discussed in lecture are also referenced in `State_and_Operations.pptx`.

## Exercises

Record your answers in `ANSWERS.md` as you work. Include the names of everyone who worked on the studio in your first answer, and number your responses so they are easy to match to the exercises.

1. List the names of the people who worked together on this studio.

2. SSH into `shell.cec.wustl.edu` using your WUSTL Key credentials, then use `qlogin` to log into one of the Linux Lab machines and confirm that the version of `g++` there is correct, as you did in [Studio 0](https://github.com/cse4208-wustl/studio0).

   Clone your `studio2` repo and work inside that cloned directory.

   Create a header file and a source file in this repo, with the source file including the header file.

   In those files, declare an enumerated type, `enum class Weekday`, for the days-of-the-week example discussed in the lecture, and then declare and define a shift operator, `operator<<`, that:

   - takes a reference to an `ostream`
   - takes a `const` reference to a variable of that enumerated type
   - uses a `switch` statement to insert a string corresponding to the variable's value, such as `"Sun"` for Sunday, into the `ostream`
   - inserts a blank space into the `ostream`
   - returns a reference to that same `ostream`

   Define a `main` function for your program. In it, declare a variable of the `Weekday` enumerated type initialized to one of the enumerated values. Then use the shift operator to insert the variable into `cout` and return a zero value to indicate success.

   Compile and run your program. In your answers, show:

   - the code you wrote for this exercise
   - the output your program produced

3. Declare and define a **postfix** increment operator, `operator++`, for the `Weekday` enumerated type that uses a `switch` statement to change the variable's state to the next-higher value in the enumeration if there is one. If the variable already has the highest value, the operator should change it to the lowest value, looping around from highest to lowest.

   In `main`, use that operator within a `do while` loop to cycle the variable through all of its possible values, using the shift operator from the previous exercise to print a line to `cout` with each value's corresponding string appearing exactly once.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

4. Declare and define a **postfix** decrement operator, `operator--`, for the `Weekday` enumerated type that uses a `switch` statement to change the variable's state to the next-lower value in the enumeration if there is one. If the variable already has the lowest value, it should change to the highest value, looping around from lowest to highest.

   In `main`, use that operator within an additional `do while` loop to cycle the variable through the possible values in the reverse order of the previous exercise, again using the shift operator repeatedly to print a line to `cout` with each value's corresponding string appearing exactly once.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

5. Declare an enumerated type, `enum class Pressure`, for the pressure example discussed in the lecture, and then declare and define a shift operator, `operator<<`, that:

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

   In `main`, use that operator within a `for` loop to cycle a variable through its low, medium, and then high pressure values, using the shift operator from the previous exercise to print a line to `cout` with the corresponding string for each of those values, but not the string for the pop state.

   Compile and run your program. In your answers, show:

   - the new code you wrote for this exercise
   - the output your program produced

## Notes

- The original source included a posting note saying the exercise answers only need to show the new code written for each exercise rather than all code so far. That clarification has been folded directly into the instructions above.
