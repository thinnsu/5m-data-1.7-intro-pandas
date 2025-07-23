# Assignment

## Brief

Write the Python codes for the following questions.

## Instructions

Paste the answer as Python in the answer code section below each question.

### Question 1

Question: Select all numeric columns except float from the DataFrame `dft`.

Answer:

```python
dft = pd.DataFrame(
    {
        "A": np.random.rand(3), 
        "B": 1, 
        "C": "foo", 
        "D": pd.Timestamp("20010102"), 
        "E": pd.Series([1.0] * 3).astype("float32"), 
        "F": False, 
        "G": pd.Series([1] * 3, dtype="int8")})

dft
dft.select_dtypes(include=['number'], exclude=['float'])

```

### Question 2

Question: How do you return the last 3 rows of a DataFrame `df`?

Answer:

```python
frame = pd.DataFrame(np.random.randn(4, 3), columns=list("bde"), index=["Utah", "Ohio", "Texas", "Oregon"])
frame
frame.tail(3)
```

### Question 3

Question: Return the minimum and maximum of a Series `x` as a new Series with the index `["min", "max"]`.

Answer:

```python
frame = pd.DataFrame(np.random.randn(4, 3), columns=list("abc"),  index=["Utah", "Ohio", "Texas", "Oregon"])
frame
def f1(x):
    return pd.Series([x.min(),x.max()], index=["min", "max"])

frame.apply(f1, axis="columns")

```

### Question 4

Question: Multiply `df1` and `df2` (two DataFrames) with a `fill_value` of 1.

Answer:

```python
import numpy as np
df1 = pd.DataFrame(np.arange(12.).reshape((3, 4)), columns=list("abcd"))
df2 = pd.DataFrame(np.arange(20.).reshape((4, 5)), columns=list("abcde"))

df2.loc[1, "b"] = np.nan
df1.multiply(df2, fill_value=1)

```

### Question 5

Question: How do you create a DataFrame from a nested dictionary of dictionaries?

```python
nested_dict = {'A': {'a': 1, 'b': 2}, 'B': {'a': 3, 'b': 4}}
```

Answer:

```python
nested_dict = {'A': {'a': 1, 'b': 2}, 'B': {'a': 3, 'b': 4}}
frame = pd.DataFrame(nested_dict)
frame
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
