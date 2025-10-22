# Python CI Lab

A simple Python calculator project demonstrating Continuous Integration (CI) with GitHub Actions.

## 📋 Project Overview

This project contains a basic calculator module with mathematical operations and corresponding unit tests. It's designed to demonstrate best practices for Python development with automated testing and continuous integration.

## 🚀 Features

- **Basic Calculator Operations**:
  - Addition
  - Subtraction
  - Multiplication
  - Division (with zero-division protection)

- **Automated Testing**: Comprehensive unit tests using pytest
- **Continuous Integration**: GitHub Actions workflow for automated testing
- **Code Quality**: Proper Python code formatting and structure

## 📁 Project Structure

```
python-ci-labb/
├── .github/
│   └── workflows/
│       └── python-test.yml    # GitHub Actions CI workflow
├── calculator.py              # Main calculator module
├── test_calculator.py         # Unit tests
├── .gitignore                # Git ignore file for Python
├── .venv/                    # Virtual environment (ignored by git)
└── README.md                 # This file
```

## 🛠️ Setup

### Prerequisites
- Python 3.10 or higher
- Git

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/fofysalman/python-ci-labb.git
   cd python-ci-labb
   ```

2. **Create and activate virtual environment**:
   ```bash
   python -m venv .venv
   
   # On Windows
   .venv\Scripts\activate
   
   # On macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install pytest
   ```

## 🧪 Running Tests

### Local Testing

Run all tests:
```bash
pytest
```

Run tests with verbose output:
```bash
pytest -v
```

Run tests with coverage:
```bash
pytest --cov=calculator
```

### Expected Test Output
```
================ test session starts ================
platform win32 -- Python 3.11.9, pytest-8.4.2
collected 4 tests

test_calculator.py::test_add PASSED      [ 25%]
test_calculator.py::test_subtract PASSED [ 50%]
test_calculator.py::test_multiply PASSED [ 75%]
test_calculator.py::test_divide PASSED   [100%]

================ 4 passed in 0.05s ==================
```

## 🔄 Continuous Integration

This project uses GitHub Actions for automated testing. The CI workflow:

- **Triggers**: On push or pull request to `main` branch
- **Environment**: Ubuntu latest with Python 3.10
- **Steps**:
  1. Checkout repository
  2. Set up Python environment
  3. Install dependencies
  4. Run tests with pytest

### CI Status
![CI Status](https://github.com/fofysalman/python-ci-labb/workflows/Python%20CI/badge.svg)

## 📖 Usage

### Import and Use Calculator Functions

```python
from calculator import add, subtract, multiply, divide

# Basic operations
result_add = add(5, 3)          # Returns: 8
result_sub = subtract(10, 4)    # Returns: 6
result_mul = multiply(3, 7)     # Returns: 21
result_div = divide(15, 3)      # Returns: 5.0

# Division by zero handling
try:
    result = divide(10, 0)
except ValueError as e:
    print(f"Error: {e}")  # Prints: Error: Division by zero!
```

## 🧾 Available Functions

| Function | Description | Parameters | Returns | Raises |
|----------|-------------|------------|---------|---------|
| `add(a, b)` | Addition | Two numbers | Sum | - |
| `subtract(a, b)` | Subtraction | Two numbers | Difference | - |
| `multiply(a, b)` | Multiplication | Two numbers | Product | - |
| `divide(a, b)` | Division | Two numbers | Quotient | `ValueError` if b=0 |

## 🔧 Development

### Adding New Features

1. Create a new function in `calculator.py`
2. Add corresponding tests in `test_calculator.py`
3. Run tests locally to ensure they pass
4. Commit and push changes (CI will run automatically)

### Example: Adding a Power Function

1. **Add to calculator.py**:
   ```python
   def power(a, b):
       return a ** b
   ```

2. **Add test to test_calculator.py**:
   ```python
   def test_power():
       assert power(2, 3) == 8
       assert power(5, 2) == 25
   ```






---

*This project demonstrates Python development best practices including testing, CI/CD, and version control.*