# Rust Exercises - Beginner Level

## 1. Simple Calculator

Write a console calculator app that performs basci arithmetic operations, ie.:

- addition,
- subtraction,
- multiplication,
- division

### Requirements

- Your program should prompt the user to enter two numbers and an operation
- Implement each operation as a separate function
- Handle division by zero

### Example Input/Output

```
Enter the first number: 10 
Enter the second number: 2 
Enter the operation (+, -, *, /): / 
Result: 5.0
```

## 2. Temperature Converter

Write a console app for converting a temperature from Celsius to Farenheit and vice versa.

### Requirements

- Your program should ask the user if they'd like to convert the value from Celsius to Farenheit or from Farenheit to Celsius
- Use the following formulas:
  - `F = C * 9/5 + 32`
  - `C = (F - 32) * 5/9`
- Display the conversion result

### Example Input/Output

```
Enter the temperature: 100 
Should I convert to (F)ahrenheit or (C)elsius? F 
Result: 212 F
```

## 3. Number guessing game

Create a game, where computer picks a random number from 1 to 100, and the user has to guess it.

### Requirements

- Your program should inform the user whether the given number is greater or lower than the one picked by the app
- Use the `rand` crate to generate a random value
- Use the `loop` loop, to allow the user to keep guessing until they find the right number.

### Example Input/Output

```
Guess a number (1-100): 50 
It's greater than that! 
Guess a number (1-100): 75 
It's lower than that! 
Guess a number (1-100): 62 
Correct!
```
