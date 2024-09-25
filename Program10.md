# Program to print the factors of a number entered by the user
Here’s a Python program to print the factors of a number entered by the user:

### Code:

```python
# Function to find the factors of a number
def find_factors(n):
    factors = []
    for i in range(1, n + 1):
        if n % i == 0:
            factors.append(i)
    return factors

# Input from the user
number = int(input("Enter a number: "))

# Call the function and print the factors
factors = find_factors(number)
print(f"The factors of {number} are: {factors}")
```

### Explanation:
1. **find_factors()**: 
   - The function iterates through all numbers from 1 to `n` (inclusive) and checks if the current number divides `n` without a remainder (i.e., `n % i == 0`).
   - If it does, the number is added to the `factors` list.

2. **User Input**: The user is prompted to enter a number, and the function returns and prints all its factors.

### Example:
If the user enters `12`, the output will be:

```
The factors of 12 are: [1, 2, 3, 4, 6, 12]
```
We can optimize the process of finding factors by using a mathematical approach. Instead of checking all numbers from 1 to `n`, We only need to check up to \( \sqrt{n} \). This works because factors come in pairs. For example, if \( d \) is a divisor of \( n \), then \( \frac{n}{d} \) is also a divisor. Here's a Python program using this approach:

### Optimized Code:

```python
import math

# Function to find factors using mathematical optimization
def find_factors(n):
    factors = set()  # Use a set to avoid duplicate factors
    for i in range(1, math.isqrt(n) + 1):
        if n % i == 0:
            factors.add(i)           # Add the divisor
            factors.add(n // i)      # Add the corresponding pair divisor
    return sorted(factors)           # Return sorted list of factors

# Input from the user
number = int(input("Enter a number: "))

# Call the function and print the factors
factors = find_factors(number)
print(f"The factors of {number} are: {factors}")
```

### Explanation:
1. **Mathematical Formula**:
   - Instead of checking all numbers up to `n`, the loop runs up to \( \sqrt{n} \).
   - For each divisor `i`, both `i` and \( \frac{n}{i} \) are added as factors, ensuring both divisors of a pair are included.

2. **Efficiency**:
   - This reduces the number of iterations, especially for large numbers.
   - The `math.isqrt(n)` is used to compute the integer square root, providing a more efficient check.

### Example:
For input `36`, the output would be:

```
The factors of 36 are: [1, 2, 3, 4, 6, 9, 12, 18, 36]
```