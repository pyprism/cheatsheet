```
. 	Any character except newline.
\. 	A period (and so on for \*, \(, \\, etc.)
^ 	The start of the string.
$ 	The end of the string.
\d,\w,\s 	A digit, word character [A-Za-z0-9_], or whitespace.
\D,\W,\S 	Anything except a digit, word character, or whitespace.
[abc] 	Character a, b, or c.
[a-z] 	a through z.
[^abc] 	Any character except a, b, or c.
aa|bb 	Either aa or bb.
? 	Zero or one of the preceding element.
* 	Zero or more of the preceding element.
+ 	One or more of the preceding element.
{n} 	Exactly n of the preceding element.
{n,} 	n or more of the preceding element.
{m,n} 	Between m and n of the preceding element.
??,*?,+?,
{n}?, etc. 	Same as above, but as few times as possible.
(expr) 	Capture expr for use with \1, etc.
(?:expr) 	Non-capturing group.
(?=expr) 	Followed by expr.
(?!expr) 	Not followed by expr.
```