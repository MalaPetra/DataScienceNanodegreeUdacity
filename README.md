https://www.udacity.com/course/data-scientist-nanodegree--nd025

# Course Prerequisites

- Python programming, including common data analysis libraries (NumPy, pandas, Matplotlib).
- SQL programming
- Statistics (Descriptive and Inferential)
- Calculus
- Linear Algebra
- Experience wrangling and visualizing data

# Software

Python 3.7.

# Course Content

- Solving Data Science Problems

Learning the data science process, including how to build effective data visualizations, and how to communicate with various stakeholders.

- Software Engineering for Data Scientists

Developing software engineering skills that are essential for data scientists, such as creating unit tests and building classes.

- Data Engineering for Data Scientists

Learning to work with data through the entire data science process, from running pipelines, transforming data, building models, and deploying solutions to the cloud.

- Experiment Design and Recommendations

Learning to design experiments and analyze A/B test results. Exploring approaches for building recommendation systems.

- Data Science Projects

Leveraging the skills leant in the programme to build my own open-ended Data Science project. This project will serve as a demonstration of your valuable abilities as a Data Scientist.

# Testing before deplying package to PyPi

1) Go to the right directory containing setup file and clothing_package and type `pip install .`

2) Leave the directory and type `python`

3) from clothing_package import clothing

4) test package in terminal:
>>> shirt_one = clothing.Shirt('red', 'S', 'long-sleeve', 25, 'short')
>>> shirt_two = clothing.Shirt('red', 'S', 'short_sleeve', 50, 'long')
>>> print(shirt_two.price)
>>> shirt_one.price + shirt_two.price


