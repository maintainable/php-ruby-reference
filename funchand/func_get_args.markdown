# func_get_args

We can use variable arguments in Ruby using the glob operator
(`*`). By prefixing a parameter in your method definition with this
operator, you tell the method to combine all remaining arguments for the
method into an array for that argument.


{{code:php
    function add()
    {
        $total = 0;
        foreach (func_get_args() as $num) {
           $total += $num;
        }
        return $total;
    }

    print add(1, 2, 3);
    // => 6
}}


{{code:ruby
    def add(*nums)
      total = 0
      nums.each {|num| total += num }
      total
    end
    # => 6
}}


{{related:
    func_get_arg  
    func_num_args
}}
