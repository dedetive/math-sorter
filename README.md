# Math Sorter

## Introduction

This is a set of mathematical functions written in Desmos that sorts a number in ascending or descending order, or simply reverses it.

All of these formulas were created by me, without AI assistance. While not flawless, they employ relatively complex techniques to achieve their functionality.

Since GitHub does not render LaTeX by default, screenshots are provided for visual reference. Please note that these formulas are not written in pure LaTeX—they use Desmos’ custom, LaTeX-inspired syntax.

I will not explain every part in detail, as I originally wrote them in November 2024 and no longer remember all implementation details.

## Sections

<details>
<summary><h3>reverse(n)</h3></summary>

![image](https://github.com/user-attachments/assets/153a551b-6a4b-4af5-9ee4-4feabf5b01a8)

#### Explanation

Returns the reverse of a number's digits. It's also used internally by `asc(n)` to flip a descending sort into ascending.

#### Examples

```python
reverse(10) = 1
reverse(25) = 52
reverse(52) = 25
reverse(314159265) = 562951413
```

#### Limitations

1. Does not support decimals—fractional parts are ignored and lost.
2. Leading or trailing zeros are lost (e.g., 051000 becomes 15).
3. Only works for natural numbers.

#### Notable parts

- `python ceil(log_10(n+1))` is commonly used to determine the length of the integer number. It is also possibly the reason this function breaks when using very large numbers in Desmos. It first gets the log of 10 of the input (and a helper 1), which will output a number with increasingly more decimal places and then applies ceil to get its upper integer rounding. It needs the helper 1 because log of 10 of exactly 10 would input 1, and thus its ceil would also be 1 instead of its true length. A valid, possibly more precision-friendly, equivalent alternative would be `python floor(log_10(n))`.

- ![image](https://github.com/user-attachments/assets/82d9c8b2-4146-435f-84e1-73a3d51e109b)
  - This gets the proper sum of all digits within the integer input. For example, the input 115766 would output the equivalent of 1+1+5+7+6+6, which is 26.
 
- ![image](https://github.com/user-attachments/assets/b64231af-7790-4766-acd5-75c81aa77c25)
  - This multiplies the current value held by the sum by a string of 1's with the same length categorized by the current position of the value, and plus one decimal place so the value is not 10 times higher than it should be.
 
</details>

<details>
<summary><h3>dec(n)</h3></summary>

![image](https://github.com/user-attachments/assets/fd5a4bb6-cd11-4baf-a065-296f143318fc)

#### Explanation

Sorts the digits of an integer in **descending** order.

#### Examples

```python
dec(1512) = 5211
dec(9229191) = 9992211
dec(010080) = 81000
dec(314159265) = 965543211
```

#### Limitations

1. Large numbers may produce inaccurate results due to Desmos' precision limits.
2. Leading zeroes are lost (e.g., dec(010) becomes 10, not 100).
3. Does not support decimals—fractional parts are ignored.

#### Notable parts

WIP

</details>

<details>
<summary><h3>asc(n)</h3></summary>

![image](https://github.com/user-attachments/assets/78bb9860-e125-4122-b1b3-40abcbc3b2ec)

#### Explanation

Sorts the digits of an integer in **ascending** order. Internally, it performs `reverse(dec(n))`.

#### Examples

```python
asc(1512) = 1125
asc(9229191) = 1122999
asc(010080) = 18
asc(314159265) = 112345569
```

#### Limitations

1. Large numbers may produce inaccurate results due to Desmos' precision limits.
2. Zeros are always dropped in the output.
3. Does not support decimals—fractional parts are ignored.

#### Notable parts

WIP

</details>
