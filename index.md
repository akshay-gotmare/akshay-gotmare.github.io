Some basic & personal javascript notes.

Important JS concepts and functioning.

<!-- | Syntax      | Description | new |
| ----------- | ----------- | --- |
| Header      | Title       | new |
| Paragraph   | Text        | new | -->

**Javascript topics:**

|1. Lexial scope|2. Block scope|3. let, const, var|4. Closures|5. Function constructor
 
<!-- ### 1. Lexial scope
### 2. Block scope
### 3. let, const, var
### 4. Closures
### 5. Function constructor -->
## Anonymous functions:
Function without any **name** or without **identity**, which can be used for function expression.
  
     var a = function() {
       console.log("Anonymous function");
     }
  
## High order functions
Higher-order functions are functions that **_return_ a function** or take in a **function as an _argument_**.

## Arrow functions:
  
	  const arrowFunction = () => {
	    console.log("Arrow function");
	  }
	
## Callback functions:
Functions those are passed inside **high-order functions** or other functions.

### First Class Functions OR First Class Citizens:
First-class functions are JavaScript functions that can behave like variables.

They can also be passed as arguments to higher-order functions.

> The ability of functions to be **used as _variables_** & **passed as _arguments_** to another funtions and could be **_returned_ from functions** is called "First Class Functions".
		
	 var a = function (param) {
	   console.log(param);
	 }
	 a(function() {
	     console.log("Arguement");
	 })
	 
> Output: 
                                              
	function() {
	  console.log("Arguement");
	}
	
	
## Function Statement vs Function Expression vs Function Declaration:
> **Function Statement OR Function Declaration:**
	
	function a() { 
	  console.log("Function statement OR Function Declaration.");
	}
	
> **Function Expression:**

	var b = function () {
	  console.log("Function Expression");
	}
		
Difference between them is **hoisting**.

Function Statement is allocated memory and executed.

Function Expression is allocated with "undefined". 

## Web API's:

|setTimeout()|DOM API|fetch()|console()

## Micro-task Queue:
All the callback functions coming through _**promises**_ will go to the **"Micro-task Queue"**.

## Callback Queue AKA Task Queue(sometimes):
Callbacks other than those coming through promises will go to **"Callback Queue"**.


`Event Loop Priority/Precedence:`

> 🥇**Micro-task Queue**

> 🥈**Callback Queue**

## Event Loop:
Event loop continuously **keeps checking** if the CALL STACK is **empty**.

Once the call stack is **empty**, "Event Loop" **prioritizes** the functions/tasks in **"Micro-task Queue"** and pushes it in the **"call stack"** and gets executed **immediately**.

Once the "Micro-task Queue" and "Call stack" is empty the functions in the "Callback Queue" gets pushed to the "call stack" and gets executed **immediately**.

## Starvation of task inside callback queue:
If a Micro-task in Micro-task Queue creates another micro-task and keeps going, the task inside Callback Queue will **never** get a chance to get executed, that is called "Starvation of task/s inside CallbackQueue".   
> ** READ MORE ON GOOGLE**
	
	Need to check::
	Q.? Promises and Mutation observer?
	Q.? Mark & Sweep algorithm?

## Concurrency Model:
Tasks in callback queue have to wait for time u**ntil the call stack gets empty** irrespective of the fact that the task is ready to be executed in the call stack.

## Map, Filter & Reduce:

|[].map()|[].filter()|[].reduce() 
are "Higher-order functions".
	
#### i. [].map():
	-- to get all the numbers in array twiced
	let arr = [1, 2, 3, 4, 5]
	let output = arr.map(x => x * 2)
	console.log(output)
	
> Output:

	[2, 4, 6, 8, 10]
	
#### ii. [].filter():
	
	let arr = [1, 2, 3, 4, 5]
	let output = arr.filter(x => x > 3)
	console.log(output)
	
>Output:

	[4, 5]

#### iii. [].reduce():
	
	const users = [
		  {name:"akshay", age:25},
		  {name:"john", age:31},
		  {name:"binod", age:25},
		  {name:"jay", age:50}
		]

		const output = users.reduce((acc, curr) => {
		  if(acc[curr.age]){
		    acc[curr.age] = ++acc[curr.age]
		  }
		  else{
		    acc[curr.age] = 1
		  }
		  return acc
		}, {})
		console.log(output)
		
> Output:
	
	{25:2, 31:1, 50:1}
		
#### Example snippets:

	let name = {
		  firstName: "Akshay",
		  lastName: "Gotmare",
		  printFullName: () => {
			console.log(this.firstName + " " + this.lastName)
		  }
		}
		name.printFullName()
		
> Output:

	"Akshay Gotmare"
		
	
> Here the "**this**" refers to the "**name**" variable.

> So, we can call "**this.firstName**" & "**this.lastName**"
