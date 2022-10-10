## Classes and Objects

_*Classes are essentially a template to create your objects.*_
_*Objects are an encapsulation of variables and functions into a single entity. Objects get their variables and functions from classes.*_

## Thinking Recursively
_*recursive function. A recursive function is a function defined in terms of itself via self-referential expressions.This means that the function will continue to call itself and repeat its behavior until some condition is met to return a result.*_
#### All recursive functions share a common structure made up of two parts: base case and recursive case.

Behind the scenes, each recursive call adds a stack frame (containing its execution context) to the call stack until we reach the base case. Then, the stack begins to unwind as each call returns its results:
![image](https://files.realpython.com/media/stack.9c4ba62929cf.gif)


### Recursive Data Structures in Python

_*A data structure is recursive if it can be deﬁned in terms of a smaller version of itself. A list is an example of a recursive data structure*_
Recursive data structures and recursive functions go together like bread and butter. The recursive function’s structure can often be modeled after the definition of the recursive data structure it takes as an input. 

## Pytest Fixtures and Coverage

### Fixtures

_*When we're writing tests, we're going to write an entire "test suite", with each test aiming to check a different path through our code. In many cases, this means we'll have a few tests with similar characteristics, something that pytest handles with "parametrized tests"*_.
_*But in other cases, things are a bit more complex. we'll want to have some objects available to all of our tests. Those objects might contain data we want to share across tests, or they might involve the network or filesystem. These are often known as "fixtures" in the testing world, and they take a variety of different forms,In pytest, you define fixtures using a combination of the pytest.fixture decorator, along with a function definition.*_

### Coverage


_*if you've ever done any testing, you know there's always the question of how thoroughly you have tested your code. After all, let's say you've written five functions, and that you've written tests for all of them. Can you be sure you've actually tested all of the possible paths through those functions?*_
#### but There are ways in which the function could give a totally different result.
#### 100% code coverage doesn't mean that your code is perfect or that it lacks bugs. But it does give you a greater degree of confidence in the code and the fact that it has been run at least once.

_*It turns out that there's a package called pytest-cov on PyPI that we can download and install. Once that's done,we can invoke pytest with the --cov option.then  we'll get a coverage report for every part of the Python library that our program used, so we strongly suggest we provide an argument to --cov, specifying which program(s) we want to test. And, we should indicate the directory into which the report should be written.*_


