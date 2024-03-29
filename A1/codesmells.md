# Markdown

Markdown is a plain-text file format. There are lots of programming tools that use Markdown, and it's useful and
easy to learn. Hash marks (the number sign) indicate headers. Asterisks indicate lists.

# Template

Use the following Code Smell template (copy and paste it at the end of this file and then edit it; don't include the "Begin template" or "End template" lines):

==== Begin template ====
## Code Smell: [Write the code smell name]

### Code Smell Category: [Write the code smell category name]

### List of classes and line numbers involved:

* [Write a class and list of line numbers, one class per asterisk, that describe the smell]

### Description:

[In your own words, explain how this particular code smells.]

### Solution:

[In your own words, explain how you might solve this code smell:
how would you refactor the code?]
==== End template ====

# List of code smells
## Code Smell: [Switch Statement]

### Code Smell Category: [Object-Orientation Abusers]

### List of classes and line numbers involved:

* [WarehouseSimulation, line 53-80]

### Description:

[there are three items in both nextEvent.startsWith and nextEvent.endsWith, Each situation is using one if statement,
making the while loop too long.]

### Solution:

[We could write a new class working for the event which starts with 'Order'.
There will be two subclass which is working for "Picker" and "Sequencer".
We can override each method in new class('Order') for "Picker" and "Sequencer"
in order to achieve the function of if statement.]

## Code Smell: [Dead Code]

### Code Smell Category: [Dispensable]

### List of classes and line numbers involved:

* [OrderException]
* [OrderListManager, line25 and 30]

### Description:

[OrderException is never used in any other class in this project
List<PickerOrderList> called completedOrders is no longer used.
Set<Picker> called pickers is no longer used.]

### Solution:

[We just need to delete the class and those instance variables.]

## Code Smell: [Dead Code]

### Code Smell Category: [Dispensable]

### List of classes and line numbers involved:

* [OrderListManager, line47, 48, 60]

### Description:

[the method boolean pickExpected(String name, String sku) will always return False and the return value is used for
if statement in method void pick(String name, String sku). if statement will always be true.]

### Solution:

[We could delete method boolean pickExpected(String name, String sku) and we don't need if statement
in method void pick(String name, String sku)]

## Code Smell: [Alternative Classes with Different Interfaces]

### Code Smell Category: [Object-Orientation Abusers]

### List of classes and line numbers involved:

* [PickerOrderList]
* [SequencerOrderList]

### Description:

[Two classes have the similar functionality but with different method names.And they have different variable names.
One is picker something and the other is sequencer something]

### Solution:

[We can write a class WorkerOrderList which is super class for PickerOrderList and SequencerOrderList.
Then we could override some specific methods for Picker and Sequencer.]

## Code Smell: [Alternative Classes with Different Interfaces]

### Code Smell Category: [Object-Orientation Abusers]

### List of classes and line numbers involved:

* [Picker]
* [Sequencer]

### Description:

[Two classes have the similar functionality but with different method names.And they have different variable names.
One is picker and the other is sequencer.]

### Solution:

[We can write a class Worker which is super class for Picker and Sequencer.
Then we could override some specific methods for Picker and Sequencer.]

## Code Smell: [Comments]

### Code Smell Category: [Dispensable]

### List of classes and line numbers involved:

* [TranslationTable, line25-33]

### Description:

[Too many comments for each line of code.]

### Solution:

[We could delete the comments in line25, 27, 30, 32.]

## Code Smell: [Large Method]

### Code Smell Category: [Bloaters]

### List of classes and line numbers involved:

* [WarehouseSimulation, line41-96]

### Description:

[The method called void start has too long lines of actual code.]

### Solution:

[From the first code smell(Switch Statement), we can decrease the line of code by rewriting the if statement by inheritance
to lead to a cleaner and shorter code]


## Code Smell: [Speculative Generality]

### Code Smell Category: [Dispensable]

### List of classes and line numbers involved:

* [Worker]

### Description:

[the class called worker is empty, it should be used to handle a future situation.]

### Solution:

[We can delete the class called worker.]