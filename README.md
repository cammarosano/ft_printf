# ft_printf #

As part of the [42](https://www.42.fr/) cursus, this project's goal was to recode printf (C standard library).

The printf function takes a format string and optional arguments and produce a formatted sequence of characters for output. More info [here](https://docs.microsoft.com/en-us/cpp/c-runtime-library/format-specification-syntax-printf-and-wprintf-functions?view=msvc-160).

A conversion specification consists of a **%** followed by optional fields and the required **type** field:  
`%[flags][width][.precision][length]type`  

Supported conversion **types**:

* **c**: character  
* **s**: string  
* **p**: pointer  
* **d, i**: signed decimal
* **u**: unsigned decimal  
* **o**: unsigned octal  
* **x, X**: unsigned hexadecimal  
* **%**: "%" sign  
* **n**: number of characters written so far is stored into integer (int * argument expected)  
* **f**: double to decimal notation [-]ddd.ddd  
* **e**: double to scientific notation [-]d.ddde±dd  
* **g**: double to f or g style, depending on the number of signicant digits informed as *precision*  

Supported **flags**:

* **\-** : left-align  
* **0**: left padding with zeros (instead of spaces)
* **\+** : always place sign (+ or -) before a number produced by a signed conversion  
* **' ' (space)** : put a space before positive number produced by a signed conversion  
* **\#** : alternate form for the following conversions:  
	* x, X: prefix "0x" (or "0X")  
	* o: prefix 0  
	* f, e: result always contains a decimal point  
	* g: result always contains a decimal point and trailing zeros are not removed

**Width**: minimum width of the output (result is padded with spaces to the left to meet this requirement, unless specified by flags **0** or **-**)

**Precision**:
* integer conversions (d, i, o, u, x, X): minimum number of digits  
* float conversions (f, e): number of digits after decimal point
* g conversion: number of significant digits
* string conversion (s): maximum number of characters to be printed

The **width** and **precision** specifiers expect a decimal digit string or a **\*** combined with an int argument (before the argument to be converted).

Supported **length** modifiers (integer conversions):

* **l**: long *
* **ll** : long long
* **h**: short
* **hh** : char  

\* For **c** and **s** conversions:
* **%lc**: wide character (wint_t argument expected)
* **%ls**: wide string conversion (wchar_t * argument expected)
