---
type: PostLayout
title: 'Python Series: List Comprehension'
date: '2024-07-11'
excerpt: >-
  List comprehensions provide a concise way to create lists in Python. They are
  a syntactic construct that allows for the generation of a new list by applying
  an expression to each item in an existing iterable (like a list, tuple, or
  range). 
featuredImage:
  type: ImageBlock
  url: 'https://assets.stackbit.com/components/images/default/post-4.jpeg'
  altText: Post thumbnail image
  caption: Caption of the image
  elementId: ''
media:
  type: ImageBlock
  url: 'https://assets.stackbit.com/components/images/default/post-4.jpeg'
  altText: Post image
  caption: Caption of the image
  elementId: ''
addTitleSuffix: true
colors: colors-a
backgroundImage:
  type: BackgroundImage
  url: /images/bg2.jpg
  backgroundSize: cover
  backgroundPosition: center
  backgroundRepeat: no-repeat
  opacity: 100
metaDescription: ' Learn how to use list comprehensions to efficiently manipulate healthcare data, including filtering, transforming, and computing derived metrics like BMI.'
metaTags:
  - type: MetaTag
    property: 'og:title'
    content: ''
---
### Tutorial: List Comprehensions with Healthcare Data

#### 1. Introduction to List Comprehensions

List comprehensions provide a compact way to generate lists. The syntax is:

```python
[expression for item in iterable if condition]
```



*   `expression` is the member itself, a call to a method, or any other valid expression that returns a value.

*   `item` is the object or value in the list or iterable.

*   `iterable` is a collection of objects (e.g., list, tuple, set).

*   `condition` is an optional filter that only includes items for which the condition is true.

#### 2. Basic Example

Let's start with a simple example. Suppose we have a list of patient ages and we want to create a new list with ages incremented by one year.

```python
ages = [25, 30, 35, 40, 45]
incremented_ages = [age + 1 for age in ages]
print(incremented_ages)
```



Output:

```python
[26, 31, 36, 41, 46]
```



#### 3. Filtering Data

Now, let's filter out patients who are younger than 30 years old.

```python
ages = [25, 30, 35, 40, 45]
filtered_ages = [age for age in ages if age >= 30]
print(filtered_ages)
```



Output:

```python
[30, 35, 40, 45]
```



#### 4. Nested List Comprehensions

Suppose we have a list of lists where each sublist contains patient data: `[age, height, weight]`. We want to extract only the ages.

```python
patients = [
    [25, 175, 70],
    [30, 180, 80],
    [35, 165, 60],
    [40, 170, 75]
]
ages = [patient[0] for patient in patients]
print(ages)
```



Output:

```python
[25, 30, 35, 40]
```



#### 5. Complex Expressions

Let's say we want to calculate the Body Mass Index (BMI) for each patient and store it in a new list. The formula for BMI is `weight / (height/100)^2`.

```python
patients = [
    [25, 175, 70],
    [30, 180, 80],
    [35, 165, 60],
    [40, 170, 75]
]
bmis = [(weight / (height/100)**2) for age, height, weight in patients]
print(bmis)
```



Output:

```python
[22.857142857142858, 24.691358024691358, 22.03856749311295, 25.95155709342561]
```



#### 6. Combining Multiple Conditions

Suppose we want to filter patients who are older than 30 and have a BMI greater than 24.

```python
patients = [
    [25, 175, 70],
    [30, 180, 80],
    [35, 165, 60],
    [40, 170, 75]
]
filtered_patients = [
    patient for patient in patients 
    if patient[0] > 30 and (patient[2] / (patient[1]/100)**2) > 24
]
print(filtered_patients)
```



Output:

```python
[[40, 170, 75]]
```



#### 7. Using Functions in List Comprehensions

We can also use functions within list comprehensions. Let's define a function to calculate BMI and use it in our list comprehension.

```python
def calculate_bmi(height, weight):
    return weight / (height/100)**2
patients = [
    [25, 175, 70],
    [30, 180, 80],
    [35, 165, 60],
    [40, 170, 75]
]
bmis = [calculate_bmi(height, weight) for age, height, weight in patients]
print(bmis)
```



Output:

```python
[22.857142857142858, 24.691358024691358, 22.03856749311295, 25.95155709342561]
```



### Conclusion

List comprehensions are a powerful tool for data manipulation and can make your code more readable and concise. In healthcare data analysis, they can be used to filter data, apply transformations, and compute derived metrics like BMI efficiently. By mastering list comprehensions, you can streamline your data processing tasks and focus on deriving insights from the data.

