print("Calculator")
print("Available operators: *, /, +, -, //, **, %")

from fractions import Fraction
import operator


decimal_ops = {
    "+": operator.add,
    "-": operator.sub,
    "*": operator.mul,
    "/": operator.truediv,
    "//": operator.floordiv,
    "%": operator.mod,
    "**": operator.pow
}

fraction_ops = {
    "+": operator.add,
    "-": operator.sub,
    "*": operator.mul,
    "/": operator.truediv,
    "**": operator.pow
}


while True:
    try:
        num1 = float(input("Enter the first number: "))
        op = input("Enter the operator: ")
        num2 = float(input("Enter the second number: "))

        num1_frac = Fraction(num1).limit_denominator()
        num2_frac = Fraction(num2).limit_denominator()

        if op not in decimal_ops:
            print("Invalid operator!")
            continue

        if op in ["/", "//", "%"] and num2 == 0:
            print("Error: Cannot divide by zero!")
            continue

        # Decimal result
        result = decimal_ops[op](num1, num2)

        # Fraction result
        if op in fraction_ops:
            fraction_result = fraction_ops[op](num1_frac, num2_frac)
        else:
            fraction_result = Fraction(result)  # // and %

        print(f"Result (Decimal): {result}")
        print(f"Result (Fraction): {fraction_result}")

        if input("Continue? (yes/no): ").strip().lower() == "no":
            break

    except ValueError:
        print("Invalid number input!")

