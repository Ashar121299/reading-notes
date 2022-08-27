## React :putting it all togather

## What is the single responsibility principle and how does it apply to components?
_*its technique that is a component should ideally only do one thing*_

## What does it mean to build a ‘static’ version of your application?
_*mean build a version that takes data model and renders the UI but has no interactivity *_

## Once you have a static application, what do you need to add? 
__*addiing interactivity requires*_

## What are the three questions you can ask to determine if something is state? 
1.Is it passed in from a parent via props? If so, it probably isn’t state.
2.Does it remain unchanged over time? If so, it probably isn’t state.
3.Can you compute it based on any other state or props in your component? If so, it isn’t state.
## How can you identify where state needs to live?
_*create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.*_

## What is a “higher-order function”?
_*function that operate on other function ,either by taking them as arguments by returning them*_

## Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?
_*its comparing between argument and number that called it and its return true if the last one is greater than number that placed argument*_

## Explain how either map or reduce operates, with regards to higher-order functions.
_*The map method transforms an array by applying a function to all of its elements and building a new array from the returned values.*_
_*The new array will have the same length as the input array, but its content will have been mapped to a new form by the function.*_
_*reduce operate its builds a value by repeatedly taking a single element from the array and combining it with the current value.*_
_*When summing numbers, we'd start with the number zero and, for each element, add that to the sum.