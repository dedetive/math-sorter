# Math Sorter

## Introduction

Series of math functions written in Desmos that sorts a number in ascending or descending order, or just reverse it.

These math formulas were all written by me, with no AI assistance. It is not flawless, however, and uses some relatively complex processes to achieve its functionality.

GitHub alone cannot render LaTeX, and thus screenshots will be provided. An important thing to note is that it is not directly LaTeX— but Desmos' LaTeX-inspired language.

I will not explain how every part works, as I've written that months ago (back in November, 2024) and cannot remember in full context what parts are responsible for.

## Sections

<details>
<summary><h3>reverse(n)</h3></summary>

![image](https://github.com/user-attachments/assets/153a551b-6a4b-4af5-9ee4-4feabf5b01a8)

#### Explanation

Reverse function takes an input and returns the literal reverse of the input. Here, it serves as an utility function for reversing the order from descending to ascending.

#### Examples

```python
reverse(10) = 1
reverse(25) = 52
reverse(52) = 25
reverse(314159265) = 562951413
```

#### Limitations

1. This function cannot process decimals. It will ignore all decimals and have loss of information.
2. This is more related to proper math, but any number starting or ending in 0's will lose that trail when reversing, such as 51000 -> 15.
3. Non-natural numbers do not work.

#### Notable parts

- `python ceil(log_10(n+1))` is widely used in the functions to refer to the length of the integer number. It is also possibly the reason this function breaks when using very large numbers in Desmos. It first gets the log of 10 of the input (and a helper 1), which will output a number with increasingly more decimal places and then applies ceil to get its upper integer rounding. It needs the helper 1 because log of 10 of exactly 10 would input 1, and thus its ceil would also be 1 instead of its true length. A valid equivalent alternative would be `python floor(log_10(n))`, and possibly more precision-friendly.

- ![image](https://github.com/user-attachments/assets/82d9c8b2-4146-435f-84e1-73a3d51e109b)
  - This part gets the proper sum of all digits within the integer input. For example, the input 115766 would output the equivalent of 1+1+5+7+6+6, which is 26.
 
- ![image](https://github.com/user-attachments/assets/b64231af-7790-4766-acd5-75c81aa77c25)
  - This part multiplies the current value held by the sum by a string of 1's with the same length categorized by the current position of the value, and plus one decimal place so the value is not 10 times higher than it should be.
 
</details>

<details>
<summary><h3>dec(n)</h3></summary>

![image](https://github.com/user-attachments/assets/fd5a4bb6-cd11-4baf-a065-296f143318fc)

#### Explanation

Sorts the integer input into its descending ordered state.

#### Examples

```python
dec(1512) = 5211
dec(9229191) = 9992211
dec(010080) = 81000
dec(314159265) = 965543211
```

#### Limitations

1. Large numbers may often be wrong or unreadable due to Desmos' lack of precision.
2. This is more related to proper math, but any number starting in 0's will lose that trail when order, such as dec(010) = 10 instead of 100.
3. This function cannot process decimals. It will ignore all decimals and have loss of information.

#### Notable parts

WIP

</details>

<details>
<summary><h3>asc(n)</h3></summary>

![image](https://github.com/user-attachments/assets/78bb9860-e125-4122-b1b3-40abcbc3b2ec)

#### Explanation

Sorts the integer input into its ascending ordered state. It is literally a dec() call that then passes through reverse().

#### Examples

```python
asc(1512) = 1125
asc(9229191) = 1122999
asc(010080) = 18
asc(314159265) = 112345569
```

#### Limitations

1. Large numbers may often be wrong or unreadable due to Desmos' lack of precision.
2. It will always clear all zeroes.
3. This function cannot process decimals. It will ignore all decimals and have loss of information.

#### Notable parts

WIP

</details>
