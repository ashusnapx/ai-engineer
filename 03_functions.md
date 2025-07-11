# 🚀 Topic: **Functions, Lambda Functions, and Decorators**

## 📍 **1. Why this topic is important (AI industry ke liye)?**

* AI pipeline mein har cheez ek function hoti hai: `clean_data()`, `train_model()`, `predict_output()`
* Lambdas se tu **1-liner preprocessing steps** likh sakta hai
* Decorators se tu code mein **logging, validation, access control** jese advanced patterns daal sakta hai — bina core logic touch kiye

> Interviews mein yeh topic favorite hai — because it shows **code architecture samajh hai ya nahi**.

---

## 📍 **2. Real-world Use-Cases**

| Feature        | Use Case                                                                   |
| -------------- | -------------------------------------------------------------------------- |
| **Functions**  | Data cleaning, model training                                              |
| **Lambda**     | Preprocessing, sorting, filtering                                          |
| **Decorators** | Logging, caching, timing functions, validating input/output, authorization |

---

## 📍 **3. Simple Intuition / Analogy**

### 🧠 Functions:

> Soch le function ek **mixer grinder** hai. Har baar usme kuch daal, process kar, result nikal —
> har kaam baar-baar likhne ki zarurat nahi.

### ⚡ Lambda:

> Ek chhota **instant masala grinder** — jisme tu ek simple kaam ek line mein kar sakta hai.

### 🎁 Decorators:

> Ek **gift wrap** jaisa — tu ek existing function pe kuch extra features wrap kar deta hai — jaise logging ya timing — bina us function ko chhede.

---

## 📍 **4. Core Concepts + Jargon**

| Term                 | Meaning                                           |
| -------------------- | ------------------------------------------------- |
| `def`                | Function define karne ka keyword                  |
| `return`             | Output dene ke liye                               |
| Lambda               | Anonymous one-liner function                      |
| `*args` / `**kwargs` | Variable number of arguments                      |
| Decorator            | Ek function jo dusre function ko modify karta hai |
| `@decorator`         | Python ka syntax to apply a decorator             |

---

## 📍 **5. Code Examples + Outputs**

### ✅ Regular Function

```python
def greet(name):
    return f"Hello, {name}"

print(greet("Ashu"))
```

💡 **Output:**

```
Hello, Ashu
```

---

### ✅ Function with default + keyword arguments

```python
def power(base, exponent=2):
    return base ** exponent

print(power(3))
print(power(3, 3))
```

💡 **Output:**

```
9
27
```

---

### ✅ `*args` and `**kwargs`

```python
def show_args(*args, **kwargs):
    print("Args:", args)
    print("Kwargs:", kwargs)

show_args(1, 2, 3, name="Ashu", age=25)
```

💡 **Output:**

```
Args: (1, 2, 3)
Kwargs: {'name': 'Ashu', 'age': 25}
```

---

### ✅ Lambda Function (Anonymous function)

```python
square = lambda x: x ** 2
print(square(5))
```

💡 **Output:**

```
25
```

---

### ✅ Lambda in Sorting

```python
names = ["ashu", "baby", "coder"]
names.sort(key=lambda x: len(x))
print(names)
```

💡 **Output:**

```
['ashu', 'baby', 'coder']
```

---

### ✅ Lambda with `map()`

```python
nums = [1, 2, 3]
squared = list(map(lambda x: x**2, nums))
print(squared)
```

💡 **Output:**

```
[1, 4, 9]
```

---

### ✅ Basic Decorator

```python
def my_decorator(func):
    def wrapper():
        print("Before the function runs")
        func()
        print("After the function runs")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

💡 **Output:**

```
Before the function runs
Hello!
After the function runs
```

---

### ✅ Decorator with arguments

```python
def repeat(func):
    def wrapper(*args, **kwargs):
        func(*args, **kwargs)
        func(*args, **kwargs)
    return wrapper

@repeat
def say(name):
    print(f"Hi {name}!")

say("Ashu")
```

💡 **Output:**

```
Hi Ashu!
Hi Ashu!
```

---

## 📍 **6. Progressive Learning**

### ✅ Level 1 – Beginner

```python
def add(a, b):
    return a + b
```

---

### ✅ Level 2 – Intermediate

```python
# Lambda with filter
nums = [1, 2, 3, 4, 5]
even = list(filter(lambda x: x % 2 == 0, nums))
print(even)
```

💡 **Output:**

```
[2, 4]
```

---

### ✅ Level 3 – Advanced

```python
from functools import wraps

def authorize(func):
    @wraps(func)
    def wrapper(user):
        if user != "admin":
            print("Access Denied")
        else:
            return func(user)
    return wrapper

@authorize
def view_dashboard(user):
    print(f"{user} is viewing dashboard")

view_dashboard("guest")
view_dashboard("admin")
```

💡 **Output:**

```
Access Denied
admin is viewing dashboard
```

---

## 📍 **7. Edge Cases & Confusing Parts**

| Confusion                          | Clarification                                 |
| ---------------------------------- | --------------------------------------------- |
| Lambda ka naam kaise dete hain?    | `x = lambda a: a+1` (lambda returns function) |
| Decorators mein `@` kya karta hai? | Wo `func = decorator(func)` ka short form hai |
| Can lambda have multiple lines?    | ❌ No — sirf 1 expression allowed              |
| Lambdas return value hi hoti hai   | No statement body, just return                |

---

## 📍 **8. Interview Twists**

* ❓ *Can you return a function from another function?*

  ```python
  def outer():
      def inner():
          print("Inside inner")
      return inner

  x = outer()
  x()
  ```

  💡 Output:

  ```
  Inside inner
  ```

* ❓ *Write a decorator that measures execution time*

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        res = func(*args, **kwargs)
        end = time.time()
        print(f"Time: {end - start:.2f}s")
        return res
    return wrapper

@timer
def slow():
    time.sleep(1)
    print("Done")

slow()
```

💡 Output:

```
Done
Time: 1.00s
```

---

## 📍 **9. Latest Trends / Standards**

* Python 3.9+ allows type hints in `lambda`
* Use `@wraps()` from `functools` in decorators to preserve function metadata (important in real-world code)

---

## 📍 **10. Mini Projects**

1. **Logger Decorator**

   * Decorator jo function call + args + output log kare

2. **Filter Even using Lambda**

   * Given list of numbers → extract all even numbers using `filter` + `lambda`

3. **Cache Decorator**

   * Store previous function results to avoid recomputation

---

## 📍 **11. Common Mistakes & Best Practices**

| Mistake                         | Solution                                 |
| ------------------------------- | ---------------------------------------- |
| Forgetting return in decorator  | Always `return wrapper`                  |
| Writing big logic in lambda     | Use named function                       |
| Not using `@wraps` in decorator | Use `@wraps(func)` to preserve name/docs |

---

## 📍 **12. Interview Questions**

### ✅ MCQ

1. What is the output?

```python
x = lambda a: a + 10
print(x(5))
```

✔ Output: `15`

2. Which one is correct syntax?

a. `lambda x: return x+1` ❌
b. `lambda x: x+1` ✔

---

### ✅ Coding

* **Write a decorator to log every time a function runs**

---

## 📍 **13. Revision Section**

```python
# Function
def fn(x): return x+1

# Lambda
lambda x: x+1

# Decorator
def deco(func):
    def wrapper():
        print("Before"); func(); print("After")
    return wrapper

@deco
def say(): print("hello")
```

---

## 📍 **14. Suggested Repos / Reading**

* RealPython – [Python Decorators](https://realpython.com/primer-on-python-decorators/)
* [Python Lambda Functions – Official Docs](https://docs.python.org/3/tutorial/controlflow.html#lambda-expressions)