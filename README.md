# Switch Statements

![Adventure Time](http://i.imgur.com/cwR0gwx.png?1)

> Bad biscuits make the baker broke, bro. -[Jake](https://en.wikipedia.org/wiki/Jake_the_Dog)

## Overview 

We'll cover switch statements and how they consider a value and compare that value to several matching patterns, and then will executee the appropriate block of code based on the pattern that matches successfully. 

## Learning Objectives 

* Compare switch statements to `if/else` statements
* Describe the syntax and structure of switch statements
* Adapt an `if/else` conditional block to a switch statement

## Switch Goodness

At this point you should feel comfortable with boolean expressions and ````if/else```` conditional clauses.  

You may have noticed that when you're chaining multiple ````if/else```` conditions together your code can start to feel a little... *hairy*; that's because while it's *possible* to chain as many ````if/else```` conditions together as you want the construct wasn't really designed for that.

The ````switch```` statement has one purpose which it is exceedingly good at: helping you write clear and correct code when you need to take more than two courses of action based upon the value of a constant, variable, or the returned value of a function.

Let's look at the following chained ````if/else````:

````Swift
if sallyDressColor == "yellow" {
	wearSomethingGreen()
} else if sallyDressColor == "blue" {
	wearSomethingPurple()
} else if sallyDressColor == "red" {
	wearSomethingOrange() 
} else if sallyDressColor == "green" {
	wearSomethingBlue()
} else ...
// that's a lot of decision-making!
````

There are two problems with code like this.  The first problem is that the repetitions of ````if sallyDressColor ==```` create a trance-like state when you're reading the code and obfuscate what you're *really* trying to understand or communicate, which is *what* color the dress is.  The ````Switch```` statement solves this problem by eliminating that code altogether and letting you just focus on what matters; it does this by taking a single value (which is what you're "switching" over) and then taking a series of possible values and related actions.

Let's see how the above Conditional chain would look if re-written as a Switch:

````Swift
switch sallyDressColor  {
	case "yellow":
		wearSomethingGreen()
		
	case "blue":
		wearSomethingPurple()
			
	case "red":
		wearSomethingOrange()
			
	case "green":
		wearSomethingBlue()
		
	default:
		wearSomethingBlack()
}
````

Take a moment to compare and contrast the ````if/else```` chain with the ````switch````; you should start seeing how the ````switch```` statement is much cleaner and clearer.

You should also see *another* important difference, namely the presence of ````default```` in the ````switch````.  This solves the second problem with the chained ````if/else````, namely forgetting to handle one or more conditions that need to be handled.

Using the ````if/else```` example above, we woudn't know what to wear if Sally was wearing a color other than yellow, blue, red or green (and let's face it: if you know Sally at all then you know she's liable to wear *any* color!).  In fact, depending on how the rest of our code was written we'd either wind up wearing a bad color or even not getting dressed at all!

The Swift compiler very helpfully makes sure that every possible value of whatever we're "switching" over is handled.  So, we could use a ````switch```` for a boolean value:

````Swift
switch 5 <= 3 {
	case true:
		print("true")
	case false:
		print("false")
	}
````

which is equivalent to:

````Swift
switch 5 <= 3 {
	case true:
		print("true")
		
	default:
		print("it ain't true")
}
````

and if we only wrote:

````Swift
switch 5 <3 {
	case true:
		print("true")
}
````
then the compiler would helpfully tell us that we weren't handling all possible values.

![non-exhaustive switch error](http://i.imgur.com/7VtpDal.png?1)

The final trick we'll cover is using ````ranges```` with ````switch````.  For example, if you want to check if a value is between 1 and 5 or 6 and 10, you *could* write:

````Swift
let x = 9

if x >= 1 && x <= 5 {
    print("x is in the range of 1-5")
} else if x >= 6 && x <= 10 {
    print("x is in the range of 6-10")
}

// prints "x is in the range of 6-10"
````

Or, you could write it like this:

````Swift
let x = 9

switch x {
case 1...5:
    print("x is within the range of 1-5")
case 6...10:
    print("x is within the range of 6-10")
default:
    print("x is greater than 10")
}

// prints "x is within the range of 6-10"
````

Which do YOU think is easier to read, write and debug?
	
But wait, there's still more!

The ````switch```` statement actually has many more features which are useful as your programs grow more complex.  While we won't cover them here (because you haven't yet had a chance to fully digest what we've just covered and also don't yet have enough context to fully appreciate the use-cases), you can look forward to learning about how the ````switch```` statement can also handle pattern matching and value binding, and especially how it really comes into its own in making stable, clear software when used in conjunction with ````Enums````.

<a href='https://learn.co/lessons/SwitchStatement' data-visibility='hidden'>View this lesson on Learn.co</a>

<p class='util--hide'>View <a href='https://learn.co/lessons/swift-switchStatement-readme'>Switch Statement </a> on Learn.co and start learning to code for free.</p>
