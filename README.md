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
Functional Currying is a pattern where you combine functions into functions to create higher order functions that a composed out of functions.

here is one example that i use my self often to assign styles and create a object with a single function

```js
const createEl = (tagName='div',_el) => 
  (_el = document.createElement(tagName)) && ({
  withStyle: (cssStyleDeclaration) => Object.assign(
    _el.style, cssStyleDeclaration) && _el
});

// Note: i only created the above object that returns a withStyle() function to create the api below i use private
// createEl("tag",propertys) as a helper which is not implemented in this example.
console.log(
  createEl("p")
    .withStyle({ color: "red" })
    .style.color
) // => "red"

// so we can can now call createEl(tagName).withStyle(new CSSStyleDeclartion()) to create elements withStyle
```

but please do not do the above all over and create the next framework this is only to reduce code in large projects. you should mostly prefer to use the raw api's that the Host offers to you this is a example from a browser Host as you probally already saw because we use CSS and HTML.

That is the most powerfull concept of ECMAScript driven languages that they are able to return functions which return it self a function without bloating the stack pointer in the virtual stack machine we call that correct call stack pointer. In many other implementations a call to a function that calls a function which returns a function adds a stack like fn => fn => fn => fn => result in Our case it will return each function directly on the main stack thats called the heap while a heap is a implementation of binary tree objects at the fundamental level. Many framework only coders will think when they hear the term heap that this is the memory area the code runs in while that is a guess able conclusion in reality it says not only that it also tells us how that memory is implemented it is a btree type struct. 

## How will i teach you?
We will simply create the most stared frameworks our self but even better with raw code and you will understand via comparison why we did it better and how we did so. How can i know that we are better? I did mesure it else i would not come to a valid conclusion this is not based on my feeling while it also feels good for me. I invested years of Observations and getting my hands dirty to come to this final massurements that i now want to share with you the reader. 

You need to understand what i did to see the failure. I did my self invest years into framework creation as also create frameworks to algin and unifie the apis of frameworks. I Forked over 5000 JS Projects and incremental improved adopted them. And i abandoned them all. I sayed jQuery is dead thousend times but today i would call that the most stable and fundamental framework that exists in web history. It did many things right. I would not use it if i can avoid it but if it is used and done right then it is the lessest evil that exists. And it was hard for me to say that. Because i know stuff like this

jquery-select-core.js
```ts
const $ = document.querySelectorAll
$('#my-selector')[0].innerHTML = 'My content.'
```

As you see the core of jquery is fast implemented via already existing core api's of the dom it is not a 1:1 match as this for example always returns array but you get the concept.
