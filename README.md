#Jekyll-HexToRGB

A super simple hex conversion Jekyll Liquid filter plugin.

This was made because I needed something to convert a hexadecimal string in the
form `"RRGGBB"` into the decimal in an array of form `[R, G, B]`

## Installation
*Assuming you are using a Jekyll site setup*

+ If you have no `_plugins` directory in your site, create one
+ Simply put `hex_to_rgb.rb` into your `plugins` directory

## Usage
This will add the filter `hex_to_rgb` to your project. Here are some examples of
it being used:

#### Examples
    {{ "aabbcc" | hex_to_rgb }} 
    # => [170, 187, 204]

    {{ "abc" | hex_to_rgb }} 
    # => [170, 187, 204]

    {{ "0a0b0c" | hex_to_rgb }} 
    # => [10, 11, 12]

#### Explanation
This filter acts differently based on the length of the sting given


##### Given a string of even length:
  1. Parse the strings in groups of 2 characters
  2. Convert each group to decimal
##### Given a string of odd length:
  1. Parse the string into individual characters
  2. Make groups of the character repeated twice
  3. Convert each group into decimal.

## Note
 This will parse and convert strings of ANY length. (Not just strings of 3 or 6
characters). Doing something like `{{ "12345" | hex_to_rgb }}` would return `[1,
2, 3, 4, 5]`

