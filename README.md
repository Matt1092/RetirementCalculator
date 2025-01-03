# Retirement Calculator

This Python program calculates the amount of savings a user will have at the time of retirement based on the following input parameters:
- Current savings (in dollars)
- Interest rate offered by the bank (will compound with the number of years)
- Number of monthly compounding periods per year
- Number of years the user will continue working

## Features

- **Input Validation**: Ensures that all user inputs are valid and within expected ranges.
- **Compound Interest Calculation**: Uses the compound interest formula to calculate future savings.
- **User-Friendly Messages**: Provides informative messages based on user inputs and results.

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/Matt1092/RetirementCalculator.git
    cd RetirementCalculator
    ```

2. **Ensure you have Python installed**:
    This program requires Python 3.x. You can check your Python version with:
    ```bash
    python --version
    ```

## Usage

1. **Run the program**:
    ```bash
    python retirementCalculator.py
    ```

2. **Follow the prompts**:
    The program will ask for the following inputs:
    - The amount of savings you possess (in dollars)
    - The bank interest rate (in percentage)
    - The number of monthly compounding periods per year
    - The number of years you plan to continue working

3. **View the results**:
    The program will display the amount of savings you will have after the specified period.

## Example

Here is an example interaction with the program:
```txt
The amount of savings you possess is $5000
The bank interest rate in % is 5
The number of monthly compounding periods per year is 12
The number of years you plan to continue working is 20
Retirement is in reach for you!
The amount of savings you will have after 20 years = $13593.95
```

## Code Overview

### Main Function

```python
def main():
    # Mainline logic for the program
```

### Retirement Calculator Function

```python
def retirementCalculator(savingsAmount, interestRate, compoundPeriod, workingYears):
    # Calculates the amount of savings based on user inputs
```

### Display Result Function

```python
def displayResult(totalMoney, workingYears):
    # Rounds and displays the result
```


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- This project was created by Matthew Moga.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.
