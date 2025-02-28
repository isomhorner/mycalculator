# mycalculator
My version of a calculator; while loop, instead of function

The code below creates a calculator, creating the 'calculator' program as a function
But the last step is: "[If no further calculation is needed for the current result, Program asks the user for a first number again, and wipes all memory of previous calculations."

The issue of the code below is: It creates an illusion of starting over by inserting 20 linebreaks...
***It isn't wiping all memory of previous calculations***
In my code, I wrote my calculator program by inserting the whole thing into an infinite 'while loop' so that it starts over, clean slate, forever


def calculator():
    should_accumulate = True
    num1 = float(input("What is the first number?: "))

    while should_accumulate:
        for symbol in operations:
            print(symbol)
        operation_symbol = input("Pick an operation: ")
        num2 = float(input("What is the next number?: "))
        answer = operations[operation_symbol](num1, num2)
        print(f"{num1} {operation_symbol} {num2} = {answer}")

        choice = input(f"Type 'y' to continue calculating with {answer}, or type 'n' to start a new calculation: ")

        if choice == 'y':
            num1 = answer
        else:
            should_accumulate = False
            print("\n" * 20)
            calculator()
