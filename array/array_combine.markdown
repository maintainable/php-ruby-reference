# array_combine

{{notice:
    This function's solution uses a Ruby `Hash` object since Ruby arrays don't
    use associative key/value pairs. See [Array](../array) for more details.
}}

There is no direct equivalent of `array_combine` in Ruby. We can get similar
results by manually building a hash from two arrays.

{{code:php
    $make  = array('VW',    'Ford');
    $model = array('Jetta', 'Explorer');

    $result = array_combine($make, $model);
    var_export($result);
    // => array('VW' => 'Jetta', 'Ford' => 'Explorer')
}}

{{code:ruby
    make  = ['VW',    'Ford']
    model = ['Jetta', 'Explorer']

    result = {}
    model.each_with_index do |val, key| 
      result[make[key]] = val
    end
    p result
    # => {"VW"=>"Jetta", "Ford"=>"Explorer"}
}}


{{related:
    array/array_merge         
    array/array_walk          
    array/array_values
}}
