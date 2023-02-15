### Website to test and construct regular expressions
https://regexr.com/
#### Spaces
> \s
#### Word boundaries
The transition between word (`\w`) and non-word (`\W`) characters. In practice this allows strings that include alphanumeric and underscore characters to be separeted from their surrounds.
> \b
#### Non-printing characters
> [^[:print:]]
#### Spaces, commas, full-stops, parentheses, ampersands, and backslashes
> [^\ \,.''&-()]+
#### String containing only a valid integer
> ^-?\d+$
#### String containing only a valid decimal
> ^-?\d+(.\d+)?$
#### Numbers, including those formatted with a decimal point.
> ^-?\d+$|^-?\d+(.\d+)?$
#### Dates matching the format MM/DD/YYYY with optional two digits for days and months.
> ^([1-9]|[0-2]\d|3[0,1])(\/|\.|-)([1-9]|0\d|1[0,1,2])(\/|\.|-)\d{4}$
#### Search within individual lines of text
Uses non-capturing negative look ahead for either newline or start of string and non-capturing negative look behind for either newline or end of string.
> (?!\n|^)  _{search pattern}_  (?<!\n|$)
#### XML tags as enclosed by angle brackets
Anything between opening (`<`) and closing (`>`) angle brackets.
> <{1}[^>]+>{1}
#### .csv or .CSV file extension
Any string ending in `.csv` or `.CSV`.
> .+\.(csv|CSV)$
>
#### Letters and numbers following the last underscore.
Uppercase letters, lowercase letters, and numbers following the last underscore (`_`).
> (?<=\_)[A-Za-z0-9]+$
>
