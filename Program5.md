To check if a number entered by the user is prime or not, you can use the following Python program. A prime number is a number greater than 1 that has no divisors other than 1 and itself.

Here’s the program:

```python
def is_prime(n):
    if n <= 1:
        return False
    elif n == 2:
        return True
    elif n % 2 == 0:
        return False
    
    # Check divisibility by all odd numbers from 3 to sqrt(n)
    for i in range(3, int(n**0.5) + 1, 2):
        if n % i == 0:
            return False
    return True

# Input from the user
try:
    number = int(input("Enter a number: "))
    if is_prime(number):
        print(f"The number {number} is a prime number.")
    else:
        print(f"The number {number} is not a prime number.")
except ValueError:
    print("Invalid input. Please enter an integer.")
```

### How It Works:
1. **Input Handling**: The program prompts the user to enter a number and attempts to convert it to an integer. If the input is not a valid integer, it catches the `ValueError` and informs the user.
2. **Prime Check Logic**:
   - **Numbers ≤ 1**: Numbers less than or equal to 1 are not prime.
   - **Number 2**: The number 2 is prime, as it is the only even prime number.
   - **Even Numbers**: Any even number greater than 2 is not prime.
   - **Odd Numbers**: For numbers greater than 2, the program checks divisibility by all odd numbers from 3 up to the square root of the number. If any divisor is found, the number is not prime.
3. **Output**: The program prints whether the entered number is prime or not.

### Example:
- If the user enters `17`, the program will output: `The number 17 is a prime number.`
- If the user enters `18`, the program will output: `The number 18 is not a prime number.`

This algorithm is efficient for checking if a number is prime, especially for large numbers, as it reduces the number of checks needed by only considering divisibility up to the square root of the number.
