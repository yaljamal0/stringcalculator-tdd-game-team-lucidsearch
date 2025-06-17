# String Calculator TDD Kata

A simple String Calculator exercise to be used to practice Test-Driven Development (TDD) principles.

## Goal

Create a python function `add(numbers)` that returns the sum of numbers in a string, following a series of incremental requirements. This kata is designed to encourage step-by-step development and frequent refactoring.

---

## Requirements

1. The method can take 0, 1, or 2 numbers and return their sum.
   - An empty string returns 0.
2. Allow the `Add` method to handle an unknown amount of numbers.
3. Allow new lines (`\n`) as delimiters in addition to commas.
4. Support custom delimiters:
   - Format: `//[delimiter]\n[numbers]`
   - Example: `//;\n1;2` returns 3
5. Throw an exception when negative numbers are passed:
   - Message: `"negatives not allowed: -1"`
6. Numbers greater than 1000 are ignored.
7. Support delimiters of any length:
   - Example: `//[***]\n1***2***3` returns 6
8. Support multiple delimiters:
   - Example: `//[*][%]\n1*2%3` returns 6
9. Support multiple delimiters of any length:
   - Example: `//[***][##]\n1***2##3` returns 6

---

## Test Cases

| Input                     | Result | Notes                             |
|--------------------------|--------|-----------------------------------|
| `""`                     | 0      | Empty string                      |
| `"1"`                    | 1      | Single number                     |
| `"1,2"`                  | 3      | Two numbers                       |
| `"1,2,3"`                | 6      | Multiple comma-separated numbers |
| `"1\n2,3"`               | 6      | New line as delimiter             |
| `"//;\n1;2"`             | 3      | Custom delimiter                  |
| `"-1,2"`                 | Exception: `negatives not allowed: -1` |
| `"2,1001"`               | 2      | Numbers > 1000 are ignored        |
| `"//[***]\n1***2***3"`   | 6      | Delimiter of any length           |
| `"//[*][%]\n1*2%3"`      | 6      | Multiple delimiters               |
| `"//[***][##]\n1***2##3"`| 6      | Multiple long delimiters          |

---

## Tips for TDD

- Start with the simplest test case (empty string).
- Add one requirement at a time.
- Refactor after each passing test.
- Consider edge cases (e.g., invalid input, negative numbers).
- Design a clean and extensible delimiter parser.

---

## Getting Started

Fork this repository, clone your copy and run the test suite to see the kata in action.
Each requirement  introduced step-by-step in the commit history.

```bash
git clone https://github.com/<your-username>/stringcalculator-tdd.git
cd stringcalculator-tdd
# run tests
pytest
```
