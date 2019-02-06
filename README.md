# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
* Use `getBalance` to check that the machine has a record of the amount inserted.
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.

### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?

0

### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
	
		Yes
	* What happens if you insert too much money into the machine – do you receive any refund?
	
		No
	* What happens if you do not insert enough and then try to print a ticket?
	
		It prints a ticket

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?
	
		Yes, the ticket includes the price in cents

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.

	public class Student {}
	public class LabClass {}

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?

	Yes, the latter isn't valid

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
	
		Yes
	* What error message do you get when you now press the compile button?
	
		<identifier> expected
	* Do you think this message clearly explains what is wrong?
	
		With some googleing, it makes some amount of sense

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.

	It compiles and seems to run correctly.

### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.
	
Fields: -price
	-balance
	-total
Constructors: -public TicketMachine(int ticketCost){}
Methods: -getPrice()
	 -getBalance()
	 -insertMoney()
	 -printTicket()

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?

It's called immediately upon TicketMachine's creation.

### Exercise 2.11
* What do you think is the type of each of the following fields?

```java
private int count;
private Student representative;
private Server host;
```

integer
Student
Server

### Exercise 2.12
* What are the names of the following fields?

```java
private boolean alive;
private Person tutor;
private Game game;
```

alive
tutor
game
### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?

Yes
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?

Yes
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!

### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?

Yes
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.


### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.

private int status;

### Exercise 2.16
* To what class does the following constructor belong?
```
public Student(String name)
```

Student

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
```
public Book(String title, double price)
```

2, types String and double
### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?

Strings
* Can you assume anything about the names of its fields?

They'll be lower case

Work all Exercises from 2.19 to 2.58 that are **NOT** marked *Challenge exercise*.
READ upto and INCLUDING section 2.15 of this chapter.

Exercise 2.19 
Suppose that the class Pet has a field called name that is of type String. Write an assignment statement in the body of the following constructor so that the name field will be initialized with the value of the constructor’s parameter.

	public Pet(String petsName)
	{
		String name = petsName;
	}

Exercise 2.21 Compare the getBalance method with the getPrice method. What are the differences between them?

	The method getPrice returns the field price which remains the same after the constructor is called and getBalance returns the Balance which changes.

Exercise 2.22 If a call to getPrice can be characterized as ‘What do tickets cost?’, how would you characterize a call to getBalance?

	'How much money is currently in the machine?'

Exercise 2.23 If the name of getBalance is changed to getAmount, does the return statement in the body of the method need to be changed, too? Try it out within BlueJ.

	No

Exercise 2.24 Define an accessor method, getTotal, that returns the value of the total field.

    /**
     * Return the amount of total money ever inserted in
     * the machine.
     */
    public int getTotal()
    {
        return total;
    }

Exercise 2.25 Try removing the return statement from the body of getPrice. What error message do you see now when you try compiling the class?

	"missing return statement"

Exercise 2.26 Compare the method signatures of getPrice and printTicket in Code 2.1. Apart from their names, what is the main difference between them?

	The method printTicket doesn't return anything. The method getPrice does

Exercise 2.27 Do the insertMoney and printTicket methods have return statements? 

	No
	
Why do you think this might be? 

	Because they're not accessor methods.
	
Do you notice anything about their headers that might suggest why they do not require return statements?

	"void"
	
Exercise 2.29 How can we tell from just its header that setPrice is a method and not a constructor?
public void setPrice(int ticketCost)

	"void" and conventionally constructors share a name with their class.
Exercise 2.30 Complete the body of the setPrice method so that it assigns the value of its parameter to the price field.

	public void setPrice(int ticketCost)
   	{
        	price = ticketCost;
    	}
	
Exercise 2.31 Complete the body of the following method, whose purpose is to add the value of its parameter to a field named score.

	/**
	* Increase score by the given number of points.
	*/
	private int score;
	public void increase(int points)
	{
		score = score + points;
	}
	
Exercise 2.32 Can you complete the following method, whose purpose is to sub- tract the value of its parameter from a field named price?

	/**
	* Reduce price by the given amount.
	*/
	private int price;
	public void discount(int amount)
	{
		price = price - amount;
	}
	
Exercise 2.33 Add a method called prompt to the TicketMachine class. This should have a void return type and take no parameters. The body of the method should print something like:
 Please insert the correct amount of money.
 
    public void prompt() 
    {
        System.out.print("Please insert the correct amount of    money");
    }
    
Exercise 2.34 Add a showPrice method to the TicketMachine class. This should have a void return type and take no parameters. The body of the method should print something like:
The price of a ticket is xyz cents.
where xyz should be replaced by the value held in the price field when the method is called.

    public void showPrice()
    {
        System.out.print("The tickets cost" + price);
    }

Exercise 2.35 Create two ticket machines with differently priced tickets. Do calls to their showPrice methods show the same output, or different? How do you explain this effect?

	Different because different values are passed into the 	price field by the constructor. 

Exercise 2.36 What do you think would be printed if you altered the fourth statement of printTicket so that price also has quotes around it, as follows?
  System.out.println("# " + "price" + " cents.");
  
	# price cents.

Exercise 2.37 What about the following version? System.out.println("# price cents.");

	# price cents.

Exercise 2.38 Could either of the previous two versions be used to show the price of tickets in different ticket machines? Explain your answer.

	No they could not because the price field is private, 	so it can only be accessed by its own ticket machine.

Exercise 2.39 Modify the constructor of TicketMachine so that it no longer has a parameter. Instead, the price of tickets should be fixed at 1000 cents. What effect does this have when you construct ticket machine objects within BlueJ?

	BlueJ no longer prompts user input for the ticket price
Exercise 2.40 Implement a method, empty, that simulates the effect of removing all money from the machine. This method should have a void return type, and its body should simply set the total field to zero. 
	
	public void empty() 
	{
		this.total = 0;
	}
Does this method need to take any parameters? 

	No	
Test your method by creating a machine, inserting some money, printing some tickets, checking the total, and then emptying the machine. Is this method a mutator or an accessor?
	mutator
	
Exercise 2.41 Implement a method, setPrice, that is able to set the price of tickets to a new value. The new price is passed in as a parameter value to the method. Test your method by creating a machine, showing the price of tickets, changing the price, and then showing the new price. 

	public void setPrice(int newValue)
	{
		this.price = newValue;
	}
	
Is this method a mutator?

	Yes
	
Exercise 2.42 Give the class two constructors. One should take a single parameter that specifies the price, and the other should take no parameter and set the price to be a default value of your choosing. Test your implementation by creating machines via the two different constructors.
	
	BlueJ asks to select which constructor should be used. 
