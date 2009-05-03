# bin2hex

The `bin2hex` function in PHP converts a string containing binary data into a
human-readable string containing the hexadecimal representation of the data.

{{code:php
    $bytes = chr(0x00) . chr(0xFF);

    $hexString = bin2hex($bytes);
    var_export($hexString);

    //=> "00ff"
}}

Ruby does not have an equivalent method but `String#unpack` with a format
string of `H*` will accomplish the same task.

{{code:ruby
    bytes = 0x00.chr + 0xFF.chr

    hex_string = bytes.unpack('H*').first
    p hex_string

    #=> "00ff"
}}

`String#unpack` always returns an array of extracted values. In the example
above, we need to take the `first` (and only) element of the result to arrive
at the same string as produced by PHP's `bin2hex`.


{{related:
    strings/pack
    strings/unpack
}}
