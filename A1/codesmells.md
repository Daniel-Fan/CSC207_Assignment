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
