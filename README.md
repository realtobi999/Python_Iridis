# Iridis

This library provides functions to print styled text in the console, with support for color-coded messages and rainbow text effects.

## Color Enum

The `Color` enum defines various color codes that can be used with the functions below.

```python
from enum import Enum

class Color(Enum):
    RED = "\033[91m"
    GREEN = "\033[92m"
    YELLOW = "\033[93m"
    BLUE = "\033[94m"
    PURPLE = "\033[95m"
    # Additional colors available (e.g., BRIGHT, BG colors)
```

## Functions

### `print_with_color(*values: object, color: Color)`

Prints the given values in the specified color.

- **values**: Objects to print.
- **color**: `Color` enum specifying the text color.

#### Example

```python
print_with_color("Hello, World!", color=Color.BLUE)
```

---

### `print_error(*values: object)`

Prints the values in red to indicate an error.

- **values**: Objects representing the error message.

#### Example

```python
print_error("This is an error message.")
```

---

### `print_title(*values: object)`

Prints the values in green to indicate a title or header.

- **values**: Objects representing the title text.

#### Example

```python
print_title("Welcome to the Application")
```

---

### `print_rainbow(*values: object)`

Prints the values with a rainbow color effect.

- **values**: Objects to print with each character in a different color.

#### Example

```python
print_rainbow("This text is in rainbow colors!")
```

---

### `get_number_from_user(input_text: str, error_message: str, conditions: list) -> float`

Prompts the user for a number and validates it against optional conditions.

- **input_text**: Prompt text (default: "Vložte číslo:").
- **error_message**: Error message shown if input is invalid (default: "Špatný vstup, zkuste znova!").
- **conditions**: List of boolean lambda conditions to validate the input.

#### Example

```python
get_number_from_user("Enter a number: ", "Invalid input!", conditions=[lambda x: x > 0])
```

### `get_string_from_user(input_text: str, error_message: str, conditions: list) -> str`

Prompts the user to input a string and validates it against specified conditions.

- **input_text**: Prompt text for the user.
- **error_message**: Error message shown if input is invalid (default: "Špatný vstup, zkuste znova!").
- **conditions**: A list of callable conditions that take a string and return a boolean.

#### Example

```python
get_string_from_user(
    "Enter your name: ",
    "Invalid name!",
    conditions=[is_not_empty, is_alpha_only]
)
```

#### String Validation Functions

These utility functions validate string inputs:

- **`is_not_empty(string: str) -> bool`**: Checks if the string is not empty.
- **`is_alpha_only(string: str) -> bool`**: Ensures the string contains only alphabetic characters.
- **`has_digits(string: str) -> bool`**: Returns `True` if the string contains any digits.
- **`has_no_digits(string: str) -> bool`**: Ensures the string has no digits.
- **`has_special_characters(string: str) -> bool`**: Checks if the string contains any special characters.
- **`has_no_special_characters(string: str) -> bool`**: Ensures the string has no special characters.
- **`is_valid_utf8(string: str) -> bool`**: Checks if the string contains only valid UTF-8 characters.
