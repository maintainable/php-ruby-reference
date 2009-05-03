# func_get_arg

We can use variable arguments in Ruby using the glob operator (`*`). By
prefixing a parameter in your method definition with this operator, you tell
the method to combine all remaining arguments for the method into an array for
that argument. We can get specific elements of this array of arguments like we
do with `func_get_arg` by simply specifying the index of the argument we need.


{{code:php
    function name()
    {
        return $firstName = func_get_arg(0);
    }

    print name('joe', 'rubenstein');
    // => joe
}}


{{code:ruby
    def name(*names)
      first_name = names[0]
    end

    puts name("joe", "rubenstein")
    # => joe
}}


{{related:
    funchand/func_get_args
    funchand/func_num_args
}}
