JavaScript Closures

In this lesson, we will apply our knowledge of JavaScript Closures, to create a simple Todo manager.

To revise what we have learned about javascript closures, 
Closures are functions encapsulated with the references of the surrounding state. In Java script closure,  The closure can access the parent scope even though the parent scope is closed.
We will learn more about closures by creating a simple to-do manager.

We will divide the entire process into three,
1. Creating a parent todo-list Function
2. Defining two child functions, add and markAsComplete inside todoList.
3. todoList function should return a list of all todos along with the add and mmarkAsComplete functions.
 
In this lesson, we will make use of the Node.js REPL. 

So, What is Node.js REPL?

Node.js REPL (Read - Evaluate - Print - Loop) shell allows the user to enter javascript directly into a shell prompt and have the results evaluated by the node.js engine immediately. This is extremely useful for testing, debugging, or experimenting with new features to understand how they work. 
The REPL is bundled with every Node.js installation and allows you to quickly test and explore JavaScript code within the Node environment without having to store it in a file.

Prerequisites:
To understand this lesson,
•	Node.js should be installed beforehand. To install this on macOS or Ubuntu 18.04, follow the steps in How to Install Node.js and Create a Local Development Environment on macOS or the “Installing Using a PPA” section of How To Install Node.js on Ubuntu 18.04.
•	Once the  node is installed, Node.js REPL will also be available. To start it, simply enter node in your command line shell.
Now, Open the terminal and run with the node command to go inside the REPL mode.

So, let's get started.

I.	First, we will define the todoList function.

const todoList = () =>

all = []

The “all” array will be holding all the todo list items.

A Todo list , will be having three properties:
1.	Title (The title of the work you need to do)
2.	Due Date (The deadline for the work completion)
3.	Completed (Whether the work is completed or not in the Boolean form). 
And inside the “all” array, we will store Todos as an object. 
For ex. { title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }

II.	Defining the add() function.
const todoList = () => 

{

all = []

const add = (todoTask) =>

{

all.push(todoTask)

console.log(all)

}

The add() function takes a todoTask as argument and pushes into the all array.

Similarly, we will define the markAsComplete() function.

const todoList = () => 

{

all = []

const add = (todoTask) => 

{

all.push(todoTask)

console.log(all)

}

const markAsComplete = (index) => 

{

all[index].completed = true

console.log(all)

}

Here, the markAsComplete() function takes an argument called index. It updates all array using the index and marks that specific Todo as completed.

III. To complete the todo-list function, we will return the all array and add markAsComplete functions.

const todoList = () => 

{

all = []

const add = (todoTask) => 

{

all.push(todoTask)

console.log(all)

}

const markAsComplete = (index) =>

{

all[index].completed = true

console.log(all)

}

return { all, add, markAsComplete };

}

Let's test it out
First, in the terminal, we will call the todoList() function.

> const todos = todoList()
> 
> Now, you will be able to see the list of all todos by:

> todos.all
> 
> [] // It will return an empty array
> 
> To add a new Todo:

> todos.add({ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }] // Output
> todos.add({ title: 'Have to buy potato', dueDate: '22-06-2022', completed: false })
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> todos.all
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: false }] // Output
> To mark a Todo as complete

> todos.markAsComplete(1) // Here 1 is the array index
> [{ title: 'I need to go to gym', dueDate: '22-06-2022', completed: false }, { title: 'Have to buy potato', dueDate: '22-06-2022', completed: true }] // Output
>
> So, it's working!
> Yes! We go the perfect output.
As we've learned before, in this example, the two functions add and markAsComplete had preserved the legacy variable all when the todoList() function was executed, and continued to preserve (closure) it.
So in this lesson, we learned about, JavaScript Closures and Node.js REPL with an example code of todo list.



