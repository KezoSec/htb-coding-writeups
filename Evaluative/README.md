# Evaluative - HTB Coding Challenge Writeup

**Difficulty:** Very Easy
**Category:** Coding

## Summary
Evaluate a degree-8 polynomial at a given integer x using 9 coefficients provided as input.

## Vulnerability / Concept
Straightforward polynomial evaluation. Given coefficients a0 through a8 and an integer x, compute a0 + a1*x + a2*x² + ... + a8*x⁸.

## Walkthrough

The input is two lines. First line has 9 space-separated coefficients, second line is x. We use `enumerate` to pair each coefficient with its power, then sum them up.

```python
coeffs = list(map(int, input().split()))
x = int(input())

result = sum(a * x**i for i, a in enumerate(coeffs))
print(result)
```

`enumerate` gives us the index `i` which doubles as the exponent. Clean one-liner solution.

## Flag

```
HTB{eV4LuaT1nG_p0LyN0M1aL5_f0R_7H3_w1N}
```

## Takeaway
When you see a polynomial evaluation problem, `enumerate` is your friend. Index = exponent, value = coefficient. One line handles the whole thing.