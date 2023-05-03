Download Link: https://assignmentchef.com/product/solved-cs1332-homework-1-arraylist
<br>
You are to code an ArrayList, which is a list data structure backed by an array where all of the data is contiguous and aligned with index 0 of the array.

Your ArrayList must follow the requirements stated in the javadocs of each method you must implement. A constructor stub is provided for you to fill out. <strong>Do not </strong>change headers for the constructor and for any of the methods provided. For example, many of the methods require you to throw exceptions, but you should not add “throws” to the header since they are not necessary.

Adding

You will implement three add() methods. One will add to the front, one will add to the back, and one will add to anywhere in the list. When adding to the front or the middle of the list, subsequent elements must be shifted back one position to make room for the new data. See the javadocs for more details.

Removing

Removing, just like adding, can be done from the front, the back, or anywhere in your ArrayList. When removing from the front or from the middle of the list, the element should be removed and all subsequent elements should be shifted forward by one position. When removing from the back, the last element should be set to null in the array. <strong>All unused positions in the backing array must be set to </strong>null. See the javadocs for more details.

Capacity

The starting capacity of your ArrayList should be the constant INITIAL CAPACITY defined in ArrayList.java. Reference the constant as-is. <strong>Do not </strong>simply copy the value of the constant. If, while adding an element,

the ArrayList does not have enough space, you should regrow the backing array to <strong>twice </strong>its old capacity. <strong>Do not </strong>regrow the backing array when removing elements. <strong>Do not change the initial capacity constant.</strong>

Amortized Efficiency

The efficiency of methods and algorithms in this course are often analyzed using a “per operation” analysis. That is, what is the worst this algorithm can do on any one instance? However, there are times where this type of analysis is unrealistically pessimistic. For example, in this homework, the addToBack() method is <em>O</em>(1) for the most part except in the case of resizing which is <em>O</em>(<em>n</em>). However, a resize operation is rare enough that it’d be misleading to say that the method is <em>O</em>(<em>n</em>).

In cases like this, we use an <strong>amortized analysis</strong>. This type of analysis adds up the cost of a series of operations and then averages the cost. Here, the resize step is <em>O</em>(<em>n</em>), but since we double the capacity whenever the array gets full, we’ve put off resizing for another <em>n </em>add operations. So, putting that together with the common, cheap <em>O</em>(1) operations, we get <em>O</em>(1) using this analysis. Whenever this type of analysis is used, we will prefix the Big-O with the word <strong>amortized</strong>.

<h2>Equality</h2>

There are two ways of defining objects as equal: reference equality and value equality.

Reference equality is used when using the == operator. If two objects are equal by reference equality, that means that they have the exact same memory locations. For example, say we have a Person object with a name and id field. If you’re using reference equality, two Person objects won’t be considered equal unless they have the exact same memory location (are the exact same object), even if they have the same name and id.

Value equality is used when using the .equals() method. Here, the definition of equality is custom made for the object. For example, in that Person example above, we may want two objects to be considered equal if they have the same name and id.

Keep in mind which makes more sense to use while you are coding. <strong>You will want to use value equality in most cases in this course when comparing objects. Notable cases where you’d use reference equality include checking for null or comparing primitives (in this case, it’s just the </strong>== <strong>operator being overloaded).</strong>

<h2>Differences between Java API and This Assignment</h2>

Some of the methods in this assignment are called different things or don’t exist in Java’s ArrayList class. This won’t matter until you tackle coding questions on the first exam, but it’s something to be aware of. The list below shows all methods with a different name and their Java API equivalent if it exists. The format is assignment method name ⇒ Java API name.

<ul>

 <li>addAtIndex(int index, T data)⇒add(int index, T data)</li>

 <li>addToFront(T data)⇒ no explicit method</li>

 <li>addToBack(T data)⇒add(T data)</li>

 <li>removeAtIndex(int index)⇒remove(int index)</li>

 <li>removeFromFront()⇒ no explicit method</li>

 <li>removeFromBack()⇒ no explicit method</li>

 <li>lastIndexOf(T data)⇒lastIndexOf(Object data)</li>

</ul>

Here is the grading breakdown for the assignment. There are various deductions not listed that are incurred when breaking the rules listed in this PDF, and in other various circumstances.

Keep in mind that add functions are necessary to test other functions, so if an add doesn’t work, remove tests might fail as the items to be removed were not added correctly. Additionally, the size function is used many times throughout the tests, so if the size isn’t updated correctly or the method itself doesn’t work, many tests can fail.

<h1>A note on JUnits</h1>

We have provided a <strong>very basic </strong>set of tests for your code, in ArrayListStudentTests.java. These tests do not guarantee the correctness of your code (by any measure), nor do they guarantee you any grade. You may additionally post your own set of tests for others to use on the Georgia Tech GitHub as a gist. Do <strong>NOT </strong>post your tests on the public GitHub. There will be a link to the Georgia Tech GitHub as well as a list of JUnits other students have posted on the class Piazza.

If you need help on running JUnits, there is a guide, available on Canvas under Files, to help you run JUnits on the command line or in IntelliJ.

<h1>Style and Formatting</h1>

It is important that your code is not only functional but is also written clearly and with good style. We will be checking your code against a style checker that we are providing. It is located on Canvas, under Files, along with instructions on how to use it. We will take off a point for every style error that occurs. If you feel like what you wrote is in accordance with good style but still sets off the style checker please email Tim Aveni (<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="8df9e7eccdeaecf9e8eee5a3e8e9f8">[email protected]</a>) with the subject header of “[CS 1332] CheckStyle XML”.

<h2>Javadocs</h2>

Javadoc any helper methods you create in a style similar to the existing Javadocs. If a method is overridden or implemented from a superclass or an interface, you may use @Override instead of writing Javadocs. Any Javadocs you write must be useful and describe the contract, parameters, and return value of the method; random or useless javadocs added only to appease Checkstyle will lose points.

<h2>Vulgar/Obscene Language</h2>

Any submission that contains profanity, vulgar, or obscene language will receive an automatic zero on the assignment. This policy applies not only to comments/javadocs but also things like variable names.

<h2>Exceptions</h2>

When throwing exceptions, you must include a message by passing in a String as a parameter. <strong>The message must be useful and tell the user what went wrong</strong>. “Error”, “BAD THING HAPPENED”, and “fail” are not good messages. The name of the exception itself is not a good message.

For example:

<strong>Bad</strong>: throw new IndexOutOfBoundsException(‘‘Index is out of bounds.’’);

<strong>Good</strong>: throw new IllegalArgumentException(‘‘Cannot insert null data into data structure.’’);

<h2>Generics</h2>

If available, use the generic type of the class; do <strong>not </strong>use the raw type of the class. For example, use new LinkedList&lt;Integer&gt;() instead of new LinkedList(). Using the raw type of the class will result in a penalty.

<h1>Forbidden Statements</h1>

You may not use these in your code at any time in CS 1332.

<ul>

 <li>package</li>

 <li>arraycopy()</li>

 <li>clone()</li>

 <li>assert()</li>

 <li>Arrays class</li>

 <li>Array class</li>

 <li>Thread class</li>

 <li>Collections class</li>

 <li>toArray()</li>

 <li>Reflection APIs</li>

 <li>Inner or nested classes</li>

 <li>Lambda Expressions</li>

 <li>Method References (using the :: operator to obtain a reference to a method)</li>

</ul>

If you’re not sure on whether you can use something, and it’s not mentioned here or anywhere else in the homework files, just ask.

Debug print statements are fine, but nothing should be printed when we run your code. We expect clean runs – printing to the console when we’re grading will result in a penalty. If you submit these, we will take off points.

<h1>Provided</h1>

The following file(s) have been provided to you. There are several, but we’ve noted the ones to edit.

<ol>

 <li>java</li>

</ol>

This is the class in which you will implement the ArrayList. Feel free to add private helper methods but <strong>do not add any new public methods, inner/nested classes, instance variables, or static variables</strong>.

<ol start="2">

 <li>java</li>

</ol>

This is the test class that contains a set of tests covering the basic operations on the ArrayList class. It is not intended to be exhaustive and does not guarantee any type of grade. <strong>Write your own tests to ensure you cover all edge cases.</strong>