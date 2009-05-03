# func_num_args

We can use variable arguments in Ruby using the glob operator
(`*`). By prefixing a parameter in your method definition with this
operator, you tell the method to combine all remaining arguments for the
method into an array for that argument. We can count the number of arguments
by checking the length of the resulting array.


{{code:php
    function test()
    {
        return func_num_args();
    }

    print test(1, 2, 3, 4);
    // => 4
}}


{{code:ruby
    def test(*nums)
      nums.length
    end

    puts test(1, 2, 3, 4)
    # => 4
}}


{{related:
    funchand/func_get_arg
    funchand/func_get_args
}}                        
