# Math Sorter

## Introduction

Series of math functions written in Desmos that sorts a number in ascending or descending order, or just reverse it.

These math formulas were all written by me, with no AI assistance. It is not flawless, however, and uses some relatively complex processes to achieve its functionality.

GitHub alone cannot render LaTeX, and thus screenshots will be provided. An important thing to note is that it is not directly LaTeX— but Desmos' LaTeX-inspired language.

I will not explain how every part works, as I've written that months ago (back in November, 2024) and cannot remember in full context what parts are responsible for.

## Sections

### reverse

![image](https://github.com/user-attachments/assets/a8ff2f43-4ced-481e-91ff-8f0c73640f80)

#### Explanation

Reverse function takes an input and returns the literal reverse of the input.

#### Examples

```python
reverse(10) = 1
reverse(25) = 52
reverse(52) = 25
reverse(314159265) = 562951413
```

#### Limitations

1. This function cannot process decimals. It will ignore all decimals and have loss of information.
2. This is more related to proper math, but any number ending in 0's will lose that trail when reversing, such as 51000 -> 15
3. When inputting integer powers of 10, for some reason it returns 0.1 instead of 1. This can be avoided by placing non-zero decimals, since those are not processed.
