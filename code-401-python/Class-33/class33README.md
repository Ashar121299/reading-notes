## Custom Hooks

### 1. Introducing Hooks

Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

Completely opt-in. You can try Hooks in a few components without rewriting any existing code. But you don’t have to learn or use Hooks right now if you don’t want to
100% backwards-compatible. Hooks don’t contain any breaking changes.
Available now. Hooks are now available with the release of v16.8.0.
There are no plans to remove classes from React. You can read more about the gradual adoption strategy for Hooks in the bottom section of this page.

Hooks don’t replace your knowledge of React concepts. Instead, Hooks provide a more direct API to the React concepts you already know: props, state, context, refs, 
and lifecycle. As we will show later, Hooks also offer a new powerful way to combine them.

If you just want to start learning Hooks, feel free to jump directly to the next page! You can also keep reading this page to learn more about why we’re adding Hooks
, and how we’re going to start using them without rewriting our applications.

### 2. Hooks at a Glance

Hooks are a new addition in React 16.8. They let you use state and other React features without writing a class.

Hooks are backwards-compatible. This page provides an overview of Hooks for experienced React users.

useState is a Hook (we’ll talk about what this means in a moment). We call it inside a function component to add some local state to it. React will preserve this
state between re-renders. useState returns a pair: the current state value and a function that lets you update it. You can call this function from an event handler 
or somewhere else. It’s similar to this.setState in a class, except it doesn’t merge the old and new state together. (We’ll show an example comparing useState to 
this.state in Using the State Hook.)

The only argument to useState is the initial state. In the example above, it is 0 because our counter starts from zero. Note that unlike this.state, the state here
doesn’t have to be an object — although it can be if you want. The initial state argument is only used during the first render.



### 3. Using the State Hook

What is a Hook? A Hook is a special function that lets you “hook into” React features. For example, useState is a Hook that lets you add React state to function 
components. We’ll learn other Hooks later.

When would I use a Hook? If you write a function component and realize you need to add some state to it, previously you had to convert it to a class. Now you can
use a Hook inside the existing function component. We’re going to do that right now!

### 4. Using the Effect Hook

This snippet is based on the counter example from the previous page, but we added a new feature to it: we set the document title to a custom message including the 
number of clicks.

Data fetching, setting up a subscription, and manually changing the DOM in React components are all examples of side effects. Whether or not you’re used to calling 
these operations “side effects” (or just “effects”), you’ve likely performed them in your components before.

### 5. Rules of Hooks
Only Call Hooks at the Top Level
Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function, before any early returns. 
By following this rule, you ensure that Hooks are called in the same order each time a component renders. That’s what allows React to correctly preserve the state 
of Hooks between multiple useState and useEffect calls. (If you’re curious, we’ll explain this in depth below.)

Only Call Hooks from React Functions
Don’t call Hooks from regular JavaScript functions. Instead, you can:

✅ Call Hooks from React function components.
✅ Call Hooks from custom Hooks (we’ll learn about them on the next page).
By following this rule, you ensure that all stateful logic in a component is clearly visible from its source code.


### 6. Building Your Own Hooks

When we want to share logic between two JavaScript functions, we extract it to a third function. Both components and Hooks are functions, so this works for them 
too!

A custom Hook is a JavaScript function whose name starts with ”use” and that may call other Hooks. For example, useFriendStatus

### 7. Hooks API Reference

This page describes the APIs for the built-in Hooks in React.

If you’re new to Hooks, you might want to check out the overview first. You may also find useful information in the frequently asked questions section.

-Basic Hooks

    useState
    useEffect
    useContext
-Additional Hooks

    useReducer
    useCallback
    useMemo
    useRef
    useImperativeHandle
    useLayoutEffect
    useDebugValue
    useDeferredValue
    useTransition
    useId
-Library Hooks

    useSyncExternalStore
    useInsertionEffect

## Lifting State Up

we want these two inputs to be in sync with each other. When we update the Celsius input, the Fahrenheit input should reflect the converted temperature, and vice 
versa.

In React, sharing state is accomplished by moving it up to the closest common ancestor of the components that need it. This is called “lifting state up”. We will 
remove the local state from the TemperatureInput and move it into the Calculator instead.

If the Calculator owns the shared state, it becomes the “source of truth” for the current temperature in both inputs. It can instruct them both to have values that 
are consistent with each other. Since the props of both TemperatureInput components are coming from the same parent Calculator component, the two inputs will always
be in sync.



## Thinking in React

One of the many great parts of React is how it makes you think about apps as you build them. In this document, we’ll walk you through the thought process of
building a searchable product data table using React.


## Memoization in React

There are some times when re-rendering of the component results in performance issues. To overcome this, React provides us with a performance feature known as 
memoization.

Memoization is an optimization technique that allows an increase in the performance of a program by storing the results of some expensive function so that we don’t
need to call that function when the same inputs are given.
