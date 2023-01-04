## What is Global State

### State traveling down

State traveling down through the hierarchy is best managed using the mutable state at the highest level to determine immutable properties that define the lower-level 
components. Even when these properties are updated, the lower-level component is updated rather than fully recreated.

As a result, the state tracked by the lower-level component will persist unless the component disappears (as could happen with conditional rendering). The following is
how the change in a higher-level component is reflected in the lower-level components.

### State traveling up

You need to pass down a callback function for a higher-level component to know the state. In the following version, we add a global state to count the total number of 
button presses and update this state with a callback function called pushed, which is called whenever a button is pushed.

### State traveling sideways

Various sub-components need to communicate updates between them. This can be achieved by passing state, using callback, up to a common parent component, and then 
passing it back down.

## Context API in React 

In a typical React application, data is passed top-down (parent to child) via props, but such usage can be cumbersome for certain types of props (e.g. locale 
preference, UI theme) that are required by many components within an application. Context provides a way to share values like these between components without having 
to explicitly pass a prop through every level of the tree.

## Context API vs Redux JS

The simplest way to pass data from a parent to a child in a React Application is by passing it on to the child's props. But an issue arises when a deeply nested child
requires data from a component higher up in the tree. If we pass on the data through the props, every single one of the children would be required to accept the data 
and pass it on to its child, leading to prop drilling, a terrible practice in the world of React.

To solve the prop drilling issue, we have State Management Solutions like Context API and Redux. But which one of them is best suited for your application? Today we
are going to answer this age-old question!

### What is Redux?

Redux is a predictable state container for JavaScript apps.

It helps you write applications that behave consistently, run in different environments (client, server, and native), and are easy to test. On top of that, it 
provides a great developer experience, such as live code editing combined with a time-traveling debugger.

You can use Redux together with React, or with any other view library. It is tiny (2kB, including dependencies), but has a large ecosystem of addons available.
