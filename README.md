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

Here are example interactions with the program:
```text
The amount of savings you possess is $5000
The bank interest rate in % is 5
The number of monthly compounding periods per year is 12
The number of years you plan to continue working is 20
The amount of savings you will have after 20 years = $13563.2
```

```text
The amount of savings you possess is $50000
The bank interest rate in % is 3
The number of monthly compounding periods per year is 6
The number of years you plan to continue working is 25
Retirement is in reach for you!
The amount of savings you will have after 20 years = $105652.38
```

```text
The amount of savings you possess is $10
The bank interest rate in % is 5
The number of monthly compounding periods per year is 12
The number of years you plan to continue working is 75
This will only work if you are an actor or the US president! No one else should work until that age :)
The number of years you plan to continue working is 30
Ouch, it looks like you have to work until you are at least 80!
The amount of savings you will have after 30 years = $44.68
```

## Code Overview

### Main Function

```python
def main():
	"""
	This function defines the mainline logic for our program.
	"""
	while True:
		try:
			savingsAmount = float(input("The amount of savings you possess is $"))
            		#Will check if initial amount is zero or less, savings should be greater than 0
			if savingsAmount < 0:
				print("Hold up! I asked for savings, not debt!")
			elif savingsAmount == 0:
				print("Hold up! You should have at least a dollar in savings!")		
			else:
				break
		except ValueError:
			print("Input must be an integer or decimal value")
			
	while True:
		try:
			interestRate = float(input("The bank interest rate in % is "))
			if interestRate < 0:
				print("Interest rate must be positive")
			else:
				break
		except ValueError:
			print("Input must be an integer or decimal value")
			
	while True:
		try:
			compoundPeriod = float(input("The number of monthly compounding periods per year is "))
			#Period should be a number of months less than a full year (12), something like 3/4/6
			if compoundPeriod > MAX_COMPOUND_PERIOD:
				print("Woah, you can only have a number up to " + str(int(MAX_COMPOUND_PERIOD)) + " months annually!")
			elif compoundPeriod < 0:
				print("Compounding period must be a positive value in the range of 0 to 12 (inclusive)")
			else:
				break	
		except ValueError:
			print("Input must be an integer or decimal value")
			
	while True:
		try:
			workingYears = float(input("The number of years you plan to continue working is "))
			#Life expectancy is around 80 years so no one should plan to work more than 60 years
			if workingYears > MAX_WORKING_YEARS:
				print("This will only work if you are an actor or the US president! No one else should work until that age :)")
			else:
				break
		except ValueError:
			print("Input must be an integer or decimal value")

	totalMoney = retirementCalculator(savingsAmount, interestRate, compoundPeriod, workingYears)
	displayResult(totalMoney, workingYears)
```

### Retirement Calculator Function

```python
def retirementCalculator(savingsAmount, interestRate, compoundPeriod, workingYears):
	"""
	Given the current savings (in $), interest (in %) and number of years, this function will
	calculate the amount of savings as a float value, then proceed to return it.

	Args:
		savingsAmount (float): Current savings.
		interestRate (float): Interest offered by the bank.
		compoundPeriod (float):Intervals of time when interest is added to account.
		workingYears (float): Number of years user will continue working.
	
	Returns:
		float: Calculation of amount (in dollars) compounded based on user inputs.
	"""
	#Compound Interest is divided by 100 to convert the % into a decimal
	retirementCalculation = savingsAmount * (1 + (interestRate / 100) / compoundPeriod) ** (compoundPeriod * workingYears)
	if savingsAmount <= MIN_TOTAL_MONEY_1:
		print("Ouch, it looks like you have to work until you are at least 80!")
	elif savingsAmount >= MIN_TOTAL_MONEY_2:
		print("Retirement is in reach for you!")
	return retirementCalculation
```

### Display Result Function

```python
def displayResult(totalMoney, workingYears):
	"""
	Given a float savings value after a certain period of time, this function will
	round it to 2 decimal places and display the result.

	Args:
		totalMoney (float): Retirement calculation amount rounded to 2 decimal places.
		workingYears (float): Number of years you will continue working.
	"""
	totalMoney = round(totalMoney, 2)
	print("The amount of savings you will have after " + str(int(workingYears)) + " years = $" + str(totalMoney))

```


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- This project was created by Matthew Moga.

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request.
