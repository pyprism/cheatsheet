Symbol | Meaning
--------|------
. |	Any character except newline.
\. | 	A period (and so on for \\*, \\(, \\, etc .)
^ |	The start of the string.
$ |	The end of the string.
\d,\w,\s |	A digit, word character [A-Za-z0-9_], or whitespace.
\D,\W,\S |	Anything except a digit, word character, or whitespace.
[abc] |	Character a, b, or c.
[a-z] |	a through z.
[^abc] |	Any character except a, b, or c.
aa|bb   Either aa or bb.
? 	| Zero or one of the preceding element.
* 	| Zero or more of the preceding element.
+ 	| One or more of the preceding element.
{n} 	| Exactly n of the preceding element.
{n,} |	n or more of the preceding element.
{m,n} |	Between m and n of the preceding element.
??,*?,+?,
{n}?, etc. 	| Same as above, but as few times as possible.
(expr) 	| Capture expr for use with \1, etc.
(?:expr) |	Non-capturing group.
(?=expr) |	Followed by expr.
(?!expr) |	Not followed by expr.
[]       | Character set

###Metacharacters

Metacharacter | Meaning | Type
-----------  |  -------- ---- | ---------
\ |  Escape next character
^ | Negative a character set
* | Preceding item zero or more times | Repetition Metacharacters
+ | Preceding item one or more times  |            "
? | Preceding item zero or one time   |            "
{ | Start quantified repetition of preceding item | Quantified Repetition
} | End quantified repetition or preceding item |  "
? | Make preceding quntifier lazy
( | Start grouped expression | Grouping Metacharacters
) | End grouped expression | "

###Shorthand Character Sets
Shorthand | Meaning | Equivalent
----------| ---------|----------
\d | Digit | [0-9]
\w | word character | [a-zA-Z0-9_]
\s | Whitespace | [ \t\r\n]
\D | Not digit | [^0-9]
\W | Not word character | [^a-zA-Z0-9_]
\S | Not Whitespace | [^ \t\r\n]

###POSIX Bracket Expressions
Class  | Meaning | Equivalent
------ | --------| ----------
[:alpha:]  | Alphabetic Characters | A-Za-z
[:digit:] | Numeric Characters | 0-9
[:alnum:] | Alphanumeric Characters | A-Za-z0-9
[:lower:] | Lowercase alphabetic characters | a-z
[:upper:]  |Uppercase alphabetic characters | A-Z
[:punct:]  | Punctuation characters |
[:space:] | Space characters | \S
[:blank:] | Blank characters(space , tab) |
[:print:] | Printable characters , spaces |
[:graph:] | Printable characters , no spaces |
[:cntrl:] | Control Characters(non-printable) |
[:xdigit:] | Hexadecimal characters | A-Fa-f0-9