# ECMAScript-101
How i would teach ECMAScript today

## What is it?
It is a Language Indipendent Scripting Language indipendent in this case refers to the fact that it runs in a virtual machine by design and that can be written in any language and is called the host or embedder often referenced under the term engine. We how ever will always call it the host the scripting host or component. 

The fundamentals of Javascript and its later evolutions like ECMAScript and Typescript as also Stealify Lang are that the language it self is Object Based.
This means everything is a Object. That allows you to implement everything in a abstract way.

This abstractions got perverted because it was so easy to create them people started taking other peoples code and simply abstracted it they call that a framework. Then they start marketing that and thats why Frameworks are more known then the fundamentals it self. Many of them do even think that they created something that is easy to use which is even a guess able conclusion. 

How ever on the long run you will find out that you read code more often then you write it. And with a lot of dependencies there come a lot of Frameworks. And thats the point where the framework concepts do break fundamental! Now you need to learn more then one framework which both use the same fundamentals. 

If you would have worked directly with only the fundamentals you would now save 2x following and maintaining frameworks. This even gets more and more complex even with the most simple module or dependencie that you bring into your project. We did not even touche licensing until this point.

But there are solutions once you know and understand them it is one of the Most nice concepts ever done when applyed right. Applying it right means to understand the right place for abstractions and how to do them without causing other developers into reading additional books for the next framework.

Theere are many ways to do usefull abstractions in place the most usefull abstractions that you will always find in good code are for example currying. 
Functional Currying is a pattern where you combine functions into functions to create hire order functions that a composed out of functions.

That is the most powerfull concept of ECMAScript driven languages that they are able to return functions which return it self a function without bloating the stack pointer in the virtual stack machine we call that correct call stack pointer. In many other implementations a call to a function that calls a function which returns a function adds a stack like fn => fn => fn => fn => result in Our case it will return each function directly on the main stack thats called the heap while a heap is a implementation of binary tree objects at the fundamental level. Many framework only coders will think when they hear the term heap that this is the memory area the code runs in while that is a guess able conclusion in reality it says not only that it also tells us how that memory is implemented it is a btree type struct. 
