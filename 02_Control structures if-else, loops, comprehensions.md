# 🔥 Topic: **Control Structures – if/else, loops, comprehensions**

## 📍 **1. Why this topic is important (AI industry ke liye)?**

* Har ML pipeline, data pre-processing, NLP text filter, ya model tuning me **logic decisions** lagte hain — wo `if`, `for`, `while`, etc. se hota hai.
* Loops help in:

  * Iterating through data batches
  * Preprocessing millions of records
  * Model evaluations
* Comprehensions make code **1-liner + optimized + pythonic**, jo interviews me **impress karta hai**.

> **Production code clean hona chahiye, lekin fast bhi. Comprehensions + clean control flow is key.**

---

## 📍 **2. Real-world Use Cases**

| Feature            | Use Case                                                  |
| ------------------ | --------------------------------------------------------- |
| `if/else`          | Model tuning: “agar accuracy > threshold toh accept karo” |
| `for` loop         | Iterate over dataset rows, batch processing               |
| `while` loop       | Retry until model converges                               |
| List Comprehension | Filter invalid data from 10 lakh entries in 1 line        |
| Dict Comprehension | NLP me: `word -> count` mapping banana                    |

---

## 📍 **3. Intuition / Analogy**

### 🔄 Loops:

> Soch loop ek **washing machine** hai — har baar ek kapda daalo, wash karo, next pe jao — **jab tak sab ho jaaye**.

### 🧠 If-Else:

> Ye ek **traffic signal** jaisa hai —
> agar **light green hai**: go
> agar **red hai**: stop
> warna **wait**

### ⚡ Comprehension:

> Jaise ek **vegetable cutting machine** — ek command do: "sab onions ko chop kar ke bowl me daalo" — **ek line ka kaam, bina manual loop likhe.**

---

## 📍 **4. Key Concepts & Jargon**

| Term           | Explanation                                                                        |
| -------------- | ---------------------------------------------------------------------------------- |
| `if-elif-else` | Conditional branching                                                              |
| `for` loop     | Sequence traversal                                                                 |
| `while` loop   | Condition-based looping                                                            |
| `break`        | Loop se bahar aana                                                                 |
| `continue`     | Current iteration skip karna                                                       |
| `pass`         | Do nothing (placeholder)                                                           |
| Comprehension  | Short-form loops with return value                                                 |
| Iterable       | Kisi bhi cheez jisko `for` loop me loop kar sakte ho (`list`, `str`, `dict`, etc.) |

---

## 📍 **5. Syntax + Code (brute → optimised)**

### ✅ `if / else`

```python
x = 10

if x > 0:
    print("Positive")
elif x == 0:
    print("Zero")
else:
    print("Negative")
```

---

### ✅ `for` loop (with range)

```python
for i in range(5):
    print(i)  # 0 to 4
```

---

### ✅ `while` loop

```python
count = 0
while count < 3:
    print(count)
    count += 1
```

---

### ✅ `break` / `continue`

```python
for i in range(5):
    if i == 3:
        break
    print(i)
```

```python
for i in range(5):
    if i == 2:
        continue
    print(i)
```

---

### ✅ List Comprehension

```python
squares = [x**2 for x in range(5)]
# [0, 1, 4, 9, 16]
```

---

### ✅ Conditional Comprehension

```python
even_squares = [x**2 for x in range(10) if x % 2 == 0]
```

---

### ✅ Dictionary Comprehension

```python
word = "ashu"
freq = {ch: word.count(ch) for ch in word}
# {'a':1, 's':1, 'h':1, 'u':1}
```

---

## 📍 **6. Progressive Learning**

### ✅ **Level 1 – Beginner**

```python
n = 10
if n > 5:
    print("Greater than 5")
else:
    print("Not greater")
```

### ✅ **Level 2 – Intermediate**

```python
for char in "Ashu":
    print(char)

while n > 0:
    n -= 1
    print(n)
```

### ✅ **Level 3 – Advanced Comprehension**

```python
# Remove all None and convert to lowercase
data = ["Ashu", None, "BABY", "hello", None]
cleaned = [x.lower() for x in data if x is not None]
```

---

## 📍 **7. Edge Cases & Confusions**

| Confusion                               | Clarification                                    |
| --------------------------------------- | ------------------------------------------------ |
| `elif` vs `if`                          | `elif` is only checked if earlier `if` was False |
| `while True:`                           | Infinite loop – must `break` inside              |
| `continue`                              | skips to next iteration, doesn't exit loop       |
| List comprehension is not faster always | True for large nested logic – needs profiling    |

---

## 📍 **8. Interview Twists & Traps**

* *Q: What's the difference between `for i in range(len(arr))` and `for val in arr`?*

  * First gives index; second gives value.

* *Q: How to reverse loop?*

  ```python
  for i in reversed(range(5)):
      print(i)
  ```

* *Q: Can we break from comprehension?*
  ❌ No — comprehensions don’t support `break/continue`.

* *Q: How to use else with loop?*

```python
for x in range(3):
    if x == 5:
        break
else:
    print("Loop ended without break")
```

---

## 📍 **9. Latest Standards / Pythonic Trends**

| Style                     | Status                   |
| ------------------------- | ------------------------ |
| `for ... in ...`          | Recommended for clarity  |
| Comprehension             | Use when logic is simple |
| Match-case (Python 3.10+) | Modern switch-case like: |

```python
match val:
    case 1:
        print("One")
    case _:
        print("Other")
```

---

## 📍 **10. Mini Projects**

1. **FizzBuzz**

   * Print numbers from 1 to 100
   * If divisible by 3 → "Fizz", by 5 → "Buzz", by both → "FizzBuzz"

2. **Word Frequency Counter**

   * Input: sentence
   * Output: `{word: frequency}` using dict comprehension

3. **Even Numbers Extractor**

   * Input: list
   * Output: list of only even numbers using list comprehension

---

## 📍 **11. Common Mistakes & Best Practices**

| Mistake                               | Fix                                  |
| ------------------------------------- | ------------------------------------ |
| Writing `if x = 5`                    | Use `==` for comparison              |
| Infinite loop in `while`              | Always check exit condition          |
| Using comprehension for side-effects  | Don’t. Use loop instead.             |
| Writing long logic in 1 comprehension | Split into functions for readability |

---

## 📍 **12. Interview Questions**

### ✅ MCQ:

1. What does this print?

```python
for i in range(3):
    print(i)
else:
    print("Done")
```

✔ Output: 0 1 2 Done

2. Which one is valid list comprehension?

a. `[i*i for i in range(5)]` ✔
b. `(i*i in range(5))` ❌

---

### ✅ Coding:

```python
def is_prime(n: int) -> bool:
    if n < 2:
        return False
    for i in range(2, int(n**0.5)+1):
        if n % i == 0:
            return False
    return True

primes = [x for x in range(2, 50) if is_prime(x)]
```

---

## 📍 **13. Revision – Cheatsheet**

```python
# If-Else
if x > 0:
    ...
elif x == 0:
    ...
else:
    ...

# For loop
for i in range(n):
    ...

# While loop
while condition:
    ...

# List comprehension
[x for x in data if x > 0]

# Dict comprehension
{k: v for k, v in dict.items()}
```

---

## 📍 **14. Suggested GitHub / Reading**

* [Python List Comprehensions – RealPython](https://realpython.com/list-comprehension-python/)
* [Looping Techniques – Python Docs](https://docs.python.org/3/tutorial/datastructures.html#looping-techniques)