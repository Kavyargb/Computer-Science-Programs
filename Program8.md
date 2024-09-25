# Write a program to print the sum of numbers from 1 to 10

Here’s a Python program to print the sum of numbers from 1 to 10:

## Code:

```python
# Function to calculate the sum of numbers from 1 to 10
def sum_of_numbers():
    total = 0
    for i in range(1, 11):
        total += i
    return total

# Call the function and print the result
print("The sum of numbers from 1 to 10 is:", sum_of_numbers())
```

## Explanation:
1. The `for` loop iterates over the numbers from 1 to 10.
2. The `total` variable accumulates the sum of these numbers.
3. The final sum is returned and printed.

We can use the formula for the sum of the first \( n \) natural numbers, which is given by:

\[
\text{sum} = \frac{n(n+1)}{2}
\]

For \( n = 10 \), the formula becomes:

\[
\text{sum} = \frac{10(10+1)}{2}
\]

### Python Code:

```python
# Function to calculate the sum using the arithmetic series formula
def sum_of_numbers(n):
    return n * (n + 1) // 2  # Integer division is used to avoid floating-point results

# Calculate and print the sum of numbers from 1 to 10
n = 10
print("The sum of numbers from 1 to 10 is:", sum_of_numbers(n))
```

### Explanation:
- The formula \( \frac{n(n+1)}{2} \) is implemented in the `sum_of_numbers()` function.
- For \( n = 10 \), the function computes the sum as \( \frac{10(10+1)}{2} = 55 \).
- The `//` operator ensures that the result is an integer.