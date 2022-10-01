## Class01
_*The main important thing of writing a code is How we can choose way to organize our information?*_ 

_* we have multiple ways that called data Structures , but it’s the logic that goes into deciding when and whether or not to use them that’s hard to wrap our head around, so that ,we’ll break them down and figure out what makes them useful, and when we might want to consider implementing them.*_


## Big O Notation 

1.firstly, Big O Notation is a way of evaluating the performance of an algorithm, means that how much time require and how much memory it need .

2.External factors can affect the time such as the speed of the processor.

3.Big O consist O (referred to as just “O” or sometimes as “order”), and a variable n, where n is the size of the input.

  . O(1) means that it doesn’t matter how many elements we have, or how huge our input is: it’ll always take the same amount of time and memory.

  .O(n) means that as our input grows the space and time that we need to run that algorithm grows linearly.

  .O(n^2) means that it takes exponentially more time and memory the more elements that we have.

![image](https://miro.medium.com/max/1400/1*FC0XX0-9Vx7yCS0dTS2Zrw.jpeg)

## What about applied Big O to linked List ?!!!

_* we can add elements and remove elements from a linked list,But we don’t need to allocate memory in advance since we won’t “run out of space” the way we might with a pre-allocated array.*_
_* So, we just need to rearrange our pointers and figure out which pointer needs to point to where.*_ >"thats it"

1.if we decide to insert element to the head of linked list it takes the same amount of time, no matter how long our list is, which is to say it has a space time complexity that is constant, or O(1).

2.if we decide to insert elemant at the end of linked list it takes time to reach to the last node specially that each node will live at a totally different “address” in memory so its O(n).

### A linked list is usually efficient when it comes to adding and removing most elements, but can be very slow to search and find a single element.
![image](https://miro.medium.com/max/720/1*cUehR5S18XSoVLaPNfNzlA.jpeg)



