# Ruby Learnig Doc
## Run Ruby file
```
ruby file .rb
```
## Numbers in Ruby
* Ruby's definition of the modulo (%) operator differs from that of C and Java. In Ruby, -7%3 is 2. In C and Java, the result is -1 instead. In Ruby, the sign of the result (for % operator) is always the same as the sign of the second operand.
## Fun with Strings
* If puts is passed an object that is not a string, puts calls the to_s method of that object and prints the string returned by that method.
* In Ruby, strings are mutable. They can expand as needed, without using much time and memory. Ruby stores a string as a sequence of characters.
## Variables and Assignment
* To store a number or a string in your computer's memory for use later in your program, you need to give the number or string a name. Programmers often refer to this process as assignment and they call the names variables. A variable springs into existence as soon as the interpreter sees an assignment to that variable.
* A local variable springs into existence as soon as the interpreter sees an assignment to that variable. It is a good practice to assign nil to a local variable initially. A runtime error will be generated if the local variable is used without being assigned a value.
* Local variables must start with either a lowercase letter or the underscore character (_), and they must consist entirely of letters, numbers, and underscores. Examples: india, _usa, some_var
## Scope
* Avoid using Global scope and Global Variables. Global scope means scope that covers the entire program. Global variables are distinguished by starting with a dollar-sign ($) character. The Ruby interpreter starts up with a fairly large number of global variables already initialized. Global variables are distinguished by starting with a dollar-sign ($) character. The Ruby interpreter starts up with a fairly large number of global variables already initialized. Global variables don't mesh well with the ideals of object-oriented programming, as once you start using global variables across an application, your code is likely to become dependent on them. Because the ability to separate blocks of logic from one another is a useful aspect of object-oriented programming, global variables are not favored.
## Getting Input
* **gets** (get a string) and **chomp** (a string method) are used to accept input from a user.
* **gets** returns a string and a '\n' character, while **chomp** removes this '\n'.
* **STDOUT** is a global constant which is the actual standard output stream for the program. **flush** flushes any buffered data within io to the underlying operating system (note that this is Ruby internal buffering only; the OS may buffer the data as well). The usage is not mandatory but recommended.
## Ruby Names
#### Variables
* A local variable (declared within an object) name consists of a lowercase letter (or an underscore) followed by name characters (sunil, _z, hit_and_run).
* An instance variable (declared within an object always "belongs to" whatever object self refers to) name starts with an ''at'' sign (''@'') followed by a name (@sign, @_, @Counter).
* A class variable (declared within a class) name starts with two ''at'' signs (''@@'') followed by a name (@@sign, @@_, @@Counter). A class variable is shared among all objects of a class. Only one copy of a particular class variable exists for a given class. Class variables used at the top level are defined in Object and behave like global variables. Class variables are rarely used in Ruby programs.
* Global variables start with a dollar sign (''$'') followed by name characters. A global variable name can be formed using ''$-'' followed by any single character ($counter, $COUNTER, $-x). Ruby defines a number of global variables that include other punctuation characters, such as $_ and $-K.
#### Constants
A constant name starts with an uppercase letter followed by name characters. Class names and module names are constants, and follow the constant naming conventions. Examples: module MyMath, PI=3.1416, class MyPune.
#### Method Names
Method names should begin with a lowercase letter (or an underscore). "?", "!" and "=" are the only weird characters allowed as method name suffixes (! or bang labels a method as dangerous-specifically, as the dangerous equivalent of a method with the same name but without the bang.
## Writing Own Ruby Methods
* We use def and end to declare a method. Parameters are simply a list of local variable names in parentheses.
* We do not declare the return type; a method returns the value of the last statement.
* It is recommended that you leave a single blank line between each method definition.
* Methods that act as Boolean queries are often named with a trailing ?
* Methods that are "dangerous," or modify the receiver, might be named with a trailing ! (Bang methods)
* Ruby lets you specify default values for a method's arguments-values that will be used if the caller doesn't pass them explicitly. You do this using the assignment operator.
* For now remember that there is an interpolation operator #{...}
* **alias** creates a new name that refers to an existing method. When a method is aliased, the new name refers to a copy of the original method's body. If the method is subsequently redefined, the aliased name will still invoke the original implementation.
* In Ruby, we can write methods that can accept variable number of parameters.
* There's no limit to the number of parameters one can pass to a method.
* The sequence in which the parameters are put on to the stack are left to right.
## Ruby ri Tool
ri dovetails with RDoc: It gives you a way to view the information that RDoc has extracted and organized. Specifically (although not exclusively, if you customize it), ri is configured to display the RDoc information from the Ruby source files. Thus on any system that has Ruby fully installed, you can get detailed information about Ruby with a simple command-line invocation of ri. Some more information is available here:
[http://www.caliban.org/ruby/rubyguide.shtml#ri](http://www.caliban.org/ruby/rubyguide.shtml#ri)
[http://en.wikipedia.org/wiki/RDoc](http://en.wikipedia.org/wiki/RDoc)
[https://github.com/rdoc/rdoc](https://github.com/rdoc/rdoc)
## More On Strings
#### Listing all methodes of a class or object
**String.methods.sort**
shows you a list of methods that the Class object String responds to.

**String.instance_methods.sort**
This method tells you all the instance methods that instances of String are endowed with.

**String.instance_methods(false).sort**
With this method, you can view a class's instance methods without those of the class's ancestors.
* For double-quoted string literals, Ruby looks for substitutions - sequences that start with a backslash character - and replaces them with some binary value or does expression interpolation ie. within the string, the sequence #{expression} is replaced by the value of the expression.
* It is to be noted that every time a string literal is used in an assignment or as a parameter, a new String object is created.
* %w is a common usage in strings. (to create array of strings)
## Simple Constructs
* Ruby also has a negated form of the if statement, the unless end.
* Case Expressions: This form is fairly close to a series of if statements: it lets you list a series of conditions and execute a statement corresponding to the first one that's true. case returns the value of the last expression executed. Usage: case when else end
## Ruby Blocks
* IMPORTANT: Ruby Code blocks are chunks of code between braces or between do- end that you can associate with method invocations.
* The Ruby standard is to use braces for single-line blocks and do- end for multi-line blocks. Keep in mind that the braces syntax has a higher precedence than the do..end syntax.
* Inside a method, you can call a Ruby block using the yield keyword with a value.
* You can provide parameters to the call to yield: these will be passed to the block. Within the block, you list the names of the arguments to receive the parameters between vertical bars (|).
* The do and end identify a block of code that will be executed for each item.
## Array
* An Array is just a list of items in order. Every slot in the list acts like a variable: you can see what object a particular slot points to, and you can make it point to a different object. You can make an array by using square brackets.
* Arrays are indexed by integers and the index starts from 0.
* A trailing comma in an array declaration is ignored.
* You can access an array beyond its boundary limits; it will return nil.
* We can add more elements to an existing array.
* Refer to the Array documentation for a list of methods.
* The method each of an Array calls a block once for each element in Array, passing that element as a parameter.
* The variable inside the "goalposts" (i.e. | |) refers to each item in the array as it goes through the loop. You can give this any name you want.
## Ranges in Ruby
* Sequences have a start point, an end point, and a way to produce successive values in the sequence. In Ruby, these sequences are created using the ".." and "..." range operators and are called Range.
* The two dot form creates an inclusive range, and the three-dot form creates a range that excludes the specified high value.
* In Ruby, the sequence 1..100000 is held as a Range object containing references to two Fixnum objects.
* The .to_a method converts a Range to an Array.
* Another use of the versatile range is as an interval test: seeing if some value falls within the interval represented by the range. We do this using ===, the case equality operator.
* Ranges are not limited to integers or numbers. The beginning and end of a range may be any Ruby object.
## Ruby Symbols
* A symbol looks like a variable name but it's prefixed with a colon.
* You can think of :id as meaning the name of the variable id, and plain id as meaning the value of the variable.
* Symbols are useful because a given symbol name refers to the same object throughout a Ruby program.
* Symbols can be considered constants without values.
* Symbols are more efficient than strings. Two strings with the same contents are two different objects, but for any given name there is only one Symbol object. This can save both time and memory.
* When do we use a string versus a symbol?
* If the contents (the sequence of characters) of the object are important, use a string.
* If the identity of the object is important, use a symbol.
* A Symbol object is created by prefixing an operator, string, variable, constant, method, class, module name with a colon.
* If Fred is a constant in one context, a method in another, and a class in a third, the Symbol :Fred will be the same object in all three contexts.
## Hashes
* Hashes are similar to arrays in that they are indexed collection of object references. However, while you index arrays with integers, you can index a hash with objects of any types: strings, regular expressions, and so on.
* When you store a value in a hash, you actually supply two objects - the index (normally called the key) and the value.
* nil is returned when an attempt is made to access keys that do not exist in the hash.
## Random Numbers
* The method to get a randomly chosen number in Ruby is rand.
* If you call rand, you'll get a float greater than or equal to 0.0 and less than 1.0. If you give it an integer parameter (by calling rand(5) ), you will get an integer value greater than or equal to 0 and less than 5.
## Read/Write Text Files
* Both class methods open and readlines belong to the IO class, whose sub-class is File. We have not done classes, objects, inheritance yet but for the record these two methods are inherited by the sub-class File from the class IO.
* The File.open method can open a file in different modes like 'r' Read-only, starts at beginning of file (default); 'r+' Read/Write, starts at beginning of file; 'w' Write-only, truncates existing file to zero length or creates a new file for writing.
* File.open opens a new File if there is no associated block. If the optional block is given, it will be passed file as an argument, and the file will automatically be closed when the block terminates.
* Always close a file that you open. In the case of a file open for writing, this is very important and can actually prevent lost data.
* The seek method of class IO, seeks to a given offset an Integer (first parameter of method) in the stream according to the value of second parameter in the method. The second parameter can be IO::SEEK_CUR - Seeks to first integer number parameter plus current position; IO::SEEK_END - Seeks to first integer number parameter plus end of stream (you probably want a negative value for first integer number parameter); IO::SEEK_SET - Seeks to the absolute location given by first integer number parameter.
## Regular Expressions
* A regular expression is simply a way of specifying a pattern of characters to be matched in a string.
* In Ruby, you typically create a regular expression by writing a pattern between slash characters (/pattern/). In Ruby, regular expressions are objects (of type Regexp) and can be manipulated as such. // is a regular expression and an instance of the Regexp class.
## Writing our own class
* Things an object can do are called methods.
* A class is used to construct an object. A class is a blueprint for an object.
* In Ruby, everything is considered to be an object. And each object has built in 'methods' (Ruby term for functions) which can be used to do various useful things. To use a method, you need to put a dot after the object, and then append the method name. Some methods such as puts and gets are available everywhere and don't need to be associated with a specific object.
* Ruby integers are objects of class Fixnum or Bignum. The Fixnum and Bignum classes represent integers of differing sizes.
* A new class is defined typically using class Name ... end
* Classes in Ruby are first-class objects - each is an instance of class Class.
* Objects are created on the heap.
* Every object in Ruby has a unique id number associated with it that can be found by the method object_id.
* Every object in Ruby has a unique id number associated with it that can be found by the method object_id.
* Variables are used to hold references to objects. Variables themselves have no type, nor are they objects themselves.
## Procs
* Blocks are not objects, but they can be converted into objects of class Proc. This can be done by calling the lambda method of the class Object.
* Remember you cannot pass methods into other methods (but you can pass procs into methods), and methods cannot return other methods (but they can return procs).
## Including Other Files
* The load method includes the named Ruby source file every time the method is executed.
* The more commonly used require method loads any given file only once.
* Note that you say require 'filename', not require 'filename.rb'.
## Ruby Open Class
* In Ruby, classes are never closed: you can always add methods to an existing class. This applies to the classes you write as well as the standard, built-in classes.
## Inheritance
* The benefit of inheritance is that classes lower down the hierarchy get the features of those higher up, but can also add specific features of their own.
* In Ruby, a class can only inherit from a single other class.
## Overriding Methods
* Method overriding allows a subclass to provide a specific implementation of a method that is already provided by one of its superclasses. The implementation in the subclass overrides (replaces) the implementation in the superclass.
* Nothing stops you from defining a method twice, however the new version takes precedence.
## Ruby Overloading Methods
* A Ruby class can have only one method with a given name.
## Access Control
* Ruby gives you three levels of protection:
  * **public** - methods can be called by everyone. A class's instance methods are public by default.
  * **protected** - methods can be invoked only by objects of the defining class and its subclasses.
  * **private** - methods cannot be called with an explicit receiver - the receiver is always self. This means that private methods can be called only in the context of the current object. The initialize method is always private.
* Top-level methods are private instance methods of the Object class.
* attr_reader is reader only; attr_writer is writer only and attr_accessor is both reader and writer.
## Exceptions
* The raise method is from the Kernel module. By default, raise creates an exception of the RuntimeError class. To raise an exception of a specific class, you can pass in the class name as an argument to raise.
* To do exception handling, we enclose the code that could raise an exception in a begin-end block and use one or more rescue clauses to tell Ruby the types of exceptions we want to handle.
## Ruby Time Class
* The Time class contains Ruby's interface to the set of time libraries written in C.
* Time zero for Ruby is the first second GMT of January 1, 1970.
* Ruby's DateTime class is superior to Time for astronomical and historical applications, but you can use Time for most everyday programs.
## Duck Typing
* In Ruby, an object type is defined by what it can do, not by what it is.
## Mutable and Immutable Objects
* Mutability is a property of an instance, not of an entire class. Any instance can become immutable by calling **freeze**.
* The freeze method in class **Object** prevents you from changing an object, effectively turning an object into a constant. After we freeze an object, an attempt to modify it results in **TypeError**.
* **freeze** operates on an object reference, not on a variable. This means that any operation resulting in a new object will work.
* A method **frozen?** tells you whether an object is frozen or not.
## Modules Mixins
* Modules serve two purposes: First they act as namespace, letting you define methods whose names will not clash with those defined elsewhere. Second, they allow you to share functionality between classes - if a class mixes in a module, that module's instance methods become available as if they had been defined in the class. They get mixed in.
## Self
* At every point when your program is running, there is one and only one self - the current or default object accessible to you in your program. You can tell which object self represents by following a small set of rules.
## Constant
* A Ruby constant is a reference to an object
* Constants defined within a class or module may be accessed anywhere within the class or module.
* Outside the class or module, they may be accessed using the scope operator, :: prefixed by an expression that returns the appropriate class or module.
* Constants defined outside any class or module may be accessed as it is or by using the scope operator with no prefix.
* Constants may not be defined in methods.
* Constants may be added to existing classes and modules from the outside by using the class or module name and the scope operator before the constant name.

