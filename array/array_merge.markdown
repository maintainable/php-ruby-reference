# array_merge

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't use
    associative key/value pairs. See [Array](../array) for more details.
}}

In Ruby we typically wouldn't merge an array. Since arrays are a simple
ordered stack of elements in Ruby, merging is the same as appending the values
to the end of the Ruby array.

{{code:php
    // keys are renumbered
    $first  = array('first');
    $second = array('second', 'third');
    $result = array_merge($first, $second);
    var_export($result);
    // => array(0 => 'first', 1 => 'second', 2 => 'third')
}}

{{code:ruby
    first  = ["first"]
    second = ["second", "third"]
    p first + second
    # ["first", "second", "third"]
}}

When working with an associative array (a hash in Ruby), merging in both PHP
and Ruby replaces any existing elements with the same key.

{{code:php
    $person  = array('name' => 'Walter', 'weight' => 184);
    $updates = array('weight' => 200, 'age' => 42);
    $result = array_merge($person, $updates);
    var_export($result);
    // => array('name' => 'Walter', 'weight' => 200, 'age' => 42)
}}

{{code:ruby
    person = {:name => "Walter", :weight => 184}
    updates = {:weight => 200, :age => 42}
    p person.merge(updates)
    # => {:age=>42, :weight=>200, :name=>"Walter"}
}}


{{related:                
    array/array_merge_recursive
    array/array_combine
}}
