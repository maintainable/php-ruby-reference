# String Functions

Ruby strings are full blown objects. In PHP we typically pass the string we
want to modify as an argument to a string function.

{{code:php
    $reversed = strrev('my string');
}}

Ruby instead executes a method on the string object itself. 

{{code:ruby
    reversed = 'my string'.reverse
}}

This provides a very consistent way of manipulating strings where we are no
longer required to remember which function argument is the string we are
manipulating.
