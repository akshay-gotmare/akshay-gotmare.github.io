Some basic & personal javascript notes.

Important JS concepts and functioning.

<!-- | Syntax      | Description | new |
| ----------- | ----------- | --- |
| Header      | Title       | new |
| Paragraph   | Text        | new | -->

**Javascript topics:**
 |Lexial scope| Block scope | let, const, var | Closures | Function constructor |
 |------------|-------------|-----------------|----------|----------------------|
 | Yet to be added | Yet to be added | Yet to be added | Yet to be added | Yet to be added |
 
<!-- ### 1. Lexial scope
### 2. Block scope
### 3. let, const, var
### 4. Closures
### 5. Function constructor -->
### 6. Difference b/w 
### i. Anonymous functions:
 | _Function without any **name** or without **identity**, which can be used for function expression._ |
 |---|
  
     var a = function() {
       console.log("Anonymous function");
     }
  
  ### ii. High order functions
  | _Higher-order functions are functions that return a function or take in a function as an argument._|
  |---|
    
  ### iii. Arrow functions:
  
	  const arrowFunction = () => {
	    console.log("Arrow function");
	  }
	
  ### iv. Callback functions:
  _Functions those are passed inside **high-order functions** or other functions._
    
  ## v. First Class Functions OR First Class Citizens:
  _First-class functions are JavaScript functions that can behave like variables. They can also be passed as arguments to higher-order functions.
  The ability of functions to be used as values& passed as arguments to another funtions and could be returned from functions is called "FIRST CLASS FUNCTIONS"._
		
	 var a = function (param) {
	   console.log(param);
	 }
	 a(function() {
	     console.log("Arguement");
	 })
   Output: 
                                              
	function() {
	  console.log("Arguement");
	}
	
	
## 7. Function Statement vs Function Expression vs Function Declaration:
> _Function statement OR Function Declaration:_
	
	function a() { 
	  console.log("Function statement OR Function Declaration.");
	}
	
> _Function Expression:_

	var b = function () {
	  console.log("Function Expression");
	}
		
Difference b/w them is hoisting.
	Function Statement is allocated memory and executed.
	Function Expression is allocated with "undefined".

8. Web API's:
	======Answers:======
	|setTimeout()
	|DOM API's
	|Fetch()
	|console()

9. Micro-task Queue:
	======Answers:=======
	|All the callback functions coming through promises 
		will go to the "Micro-task Queue".

10. Callback Queue AKA Task Queue(sometimes):
	======Answers:=======
	|Callbacks other than those coming through promises 
		will go to "Callback Queue".
				+++++ Priority +++++
			Micro-task Queue >> Callback Queue
			++++++++++++++++++++++++++++++++++

11. ""Event Loop:""
	======Answers:=======
	> Event loop continuously keeps checking if the 
	  CALL STACK is empty.
	> Once the call stack is empty, "Event Loop" prioritizes
	  the functions "Micro-task Queue" and pushes it in
	  the "call stack" and gets executed immediately.
	> Once the "Micro-task Queue" and "Call stack" is empty
	  the functions in the "Callback Queue" gets pushed to
	  the "call stack" and gets executed immediately.

12. Q.? Starvation of task inside callback queue?
	======Answers:=======
	> If a Micro-task in Micro-task Queue creates another
	  micro-task and keeps going, the task inside Callback
	  Queue will never get a chance to get executed, 
	  that is called "Starvation of task/s inside Callback
	  Queue.   *** READ MORE ON GOOGLE***

	Q.? Promises and Mutation observer?
	Q.? Mark & Sweep algorithm?

13. Concurrency Model:
	======Answers:=======
	Tasks in callback queue have to wait for time until the 
	call stack gets empty irrespective of the fact that the 
	task is ready to be executed in the call stack.

14. > First-class functions are JavaScript functions that 
	  can behave like variables. They can also be passed 
	  as arguments to higher-order functions.

	> Higher-order functions are functions that return a 
	  function or take in a function as an argument.	
	
15. || [].map(), [].filter(), [].reduce() 
	|| are Higher-order functions.
	
16. let name = {
	  firstName: "Akshay",
	  lastName: "Gotmare",
	  printFullName: () => {
		console.log(this.firstName + " " + this.lastName)
	  }
	}
	name.printFullName()
	
	#### here the "this" refers to the "name" variable.
	#### So, we can call "this.firstName" & "this.lastName"
---------------------------------------

		const users = [
		  {name:"akshay", age:25},
		  {name:"john", age:31},
		  {name:"Binod", age:25},
		  {name:"Jay", age:50}
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
