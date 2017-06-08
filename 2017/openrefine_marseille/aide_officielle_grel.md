# Aide officielle OpenRefine sur les fonctions GREL

## Variables
cell	La cellule en cours. Elle a deux champs : 'value' et 'recon'.

value	La valeur de la cellule en cours. C’est un alias de 'cell.value'.

row	La ligne en cours. Elle a cinq champs : 'flagged', 'starred', 'index', 'cells' et 'record'.

cells	Les cellules de la ligne en cours. C’est un alias de 'row.cells'. Une cellule spécifique peut être retrouvée avec 'cells.<nom de la colonne>' lorsque <nom de la colonne > est un mot simple et avec 'cells.["<nom de la colonne>"]' dans les autres cas.

rowIndex	L’index de la ligne en cours. C’est un alias de 'row.index'.

## Fonctions
* abs	(number d)
	renvoie: number
	Returns the absolute value of a number
* acos	(number d)
	renvoie: number
	Returns the arc cosine of an angle, in the range 0 through PI
* and	(boolean a, boolean b)
	renvoie: boolean
	ANDs two boolean values
* asin	(number d)
	renvoie: number
	Returns the arc sine of an angle in the range of -PI/2 through PI/2
* atan	(number d)
	renvoie: number
	Returns the arc tangent of an angle in the range of -PI/2 through PI/2
* atan2	(number x, number y)
	renvoie: number theta
	Converts rectangular coordinates (x, y) to polar (r, theta)
* ceil	(number d)
	renvoie: number
	Returns the ceiling of a number
* chomp	(string str, string separator)
	renvoie: string
	Removes separator from the end of str if it's there, otherwise leave it alone.
* combin	(number d)
	renvoie: number
	Returns the number of combinations for n elements as divided into k
* contains	(string s, string frag)
	renvoie: boolean
	Returns whether s contains frag
* cos	(number d)
	renvoie: number
	Returns the trigonometric cosine of an angle
* cosh	(number d)
	renvoie: number
	Returns the hyperbolic cosine of a value
* cross	(cell c, string projectName, string columnName)
	renvoie: array
	TODO
* datePart	(date d, string part)
	renvoie: date
	Returns part of a date
* degrees	(number d)
	renvoie: number
	Converts an angle from radians to degrees.
* diff	(o1, o2, time unit (optional))
	renvoie: string for strings, number for dates
	For strings, returns the portion where they differ. For dates, it returns the difference in given time units
* endsWith	(string s, string sub)
	renvoie: boolean
	Returns whether s ends with sub
* escape	(string s, string mode ['html','xml','csv','url','javascript'])
	renvoie: string
	Escapes a string depending on the given escaping mode.
* even	(number d)
	renvoie: number
	Rounds the number up to the nearest even integer
* exp	(number n)
	renvoie: number
	Returns e^n
* facetCount	(choiceValue, string facetExpression, string columnName)
	renvoie: number
	Returns the facet count corresponding to the given choice value
* fact	(number i)
	renvoie: number
	Returns the factorial of a number
factn	(number i)
	renvoie: number
	Returns the factorial of a number
fingerprint	(string s)
	renvoie: string
	Returns the fingerprint of s, a derived string that aims to be a more canonical form of it (this is mostly useful for finding clusters of strings related to the same information).
floor	(number d)
	renvoie: number
	Returns the floor of a number as an integer
gcd	(number d, number e)
	renvoie: number
	Returns the greatest common denominator of the two numbers
get	(o, number or string from, optional number to)
	renvoie: Depends on actual arguments
	If o has fields, returns the field named 'from' of o. If o is an array, returns o[from, to]. if o is a string, returns o.substring(from, to)
hasField	(o, string name)
	renvoie: boolean
	Returns whether o has field name
htmlAttr	(Element e, String s)
	renvoie: String attribute Value
	Selects a value from an attribute on an Html Element
htmlText	(Element e)
	renvoie: String text
	Selects the text from within an element (including all child elements)
inc	(date d, number value, string unit (default to 'hour'))
	renvoie: date
	Returns a date changed by the given amount in the given unit of time
indexOf	(string s, string sub)
	renvoie: number
	Returns the index of sub first ocurring in s
innerHtml	(Element e)
	renvoie: String innerHtml
	The innerHtml of an HTML element
join	(array a, string sep)
	renvoie: string
	Returns the string obtained by joining the array a with the separator sep
jsonize	(value)
	renvoie: JSON literal value
	Quotes a value as a JSON literal value
lastIndexOf	(string s, string sub)
	renvoie: number
	Returns the index of sub last ocurring in s
lcm	(number d, number e)
	renvoie: number
	Returns the greatest common denominator of the two numbers
length	(array or string o)
	renvoie: number
	Returns the length of o
ln	(number n)
	renvoie: number
	Returns the natural log of n
log	(number n)
	renvoie: number
	Returns the base 10 log of n
match	(string or regexp)
	renvoie: array of strings
	Returns an array of the groups matching the given regular expression
max	(number a, number b)
	renvoie: number
	Returns the greater of two numbers
md5	(string s)
	renvoie: string
	Returns the MD5 hash of s
min	(number a, number b)
	renvoie: number
	Returns the smaller of two numbers
mod	(number a, number b)
	renvoie: number
	Returns a modulus b
multinomial	(one or more numbers)
	renvoie: number
	Calculates the multinomial of a series of numbers
ngram	(string s, number n)
	renvoie: array of strings
	Returns an array of the word ngrams of s
ngramFingerprint	(string s, number n)
	renvoie: string
	Returns the n-gram fingerprint of s
not	(boolean b)
	renvoie: boolean
	Returns the opposite of b
now	(undefined)
	renvoie: date
	Returns the current time
odd	(number d)
	renvoie: number
	Rounds the number up to the nearest even integer
or	(boolean a, boolean b)
	renvoie: boolean
	Returns a OR b
ownText	(Element e)
	renvoie: String ownText
	Gets the text owned by this HTML element only; does not get the combined text of all children.
parseHtml	(string s)
	renvoie: HTML object
	Parses a string as HTML
parseJson	(string s)
	renvoie: JSON object
	Parses a string as JSON
partition	(string s, string or regex frag, optional boolean omitFragment)
	renvoie: array
	Returns an array of strings [a,frag,b] where a is the string part before the first occurrence of frag in s and b is what's left. If omitFragment is true, frag is not returned.
phonetic	(string s, string encoding (optional, defaults to 'metaphone3'))
	renvoie: string
	Returns the a phonetic encoding of s (optionally indicating which encoding to use')
pow	(number a, number b)
	renvoie: number
	Returns a^b
quotient	(number numerator, number denominator)
	renvoie: number
	Returns the integer portion of a division
radians	(number d)
	renvoie: number
	Converts an angle in degrees to radians
reinterpret	(string s, string encoder)
	renvoie: string
	Returns s reinterpreted thru the given encoder.
replace	(string s, string or regex f, string r)
	renvoie: string
	Returns the string obtained by replacing f with r in s
replaceChars	(string s, string f, string r)
	renvoie: string
	Returns the string obtained by replacing all chars in f with the char in s at that same position
reverse	(array a)
	renvoie: array
	Reverses array a
round	(number n)
	renvoie: number
	Returns n rounded
rpartition	(string s, string or regex frag, optional boolean omitFragment)
	renvoie: array
	Returns an array of strings [a,frag,b] where a is the string part before the last occurrence of frag in s and b is what's left. If omitFragment is true, frag is not returned.
select	(Element e, String s)
	renvoie: HTML Elements
	Selects an element from an HTML elementn using selector syntax
sha1	(string s)
	renvoie: string
	Returns the SHA-1 hash of s
sin	(number d)
	renvoie: number
	Returns the trigonometric sine of an angle
sinh	(number d)
	renvoie: number
	Returns the hyperbolic sine of an angle
slice	(o, number from, optional number to)
	renvoie: Depends on actual arguments
	If o is an array, returns o[from, to]. if o is a string, returns o.substring(from, to)
smartSplit	(string s, optional string sep)
	renvoie: array
	Returns the array of strings obtained by splitting s with separator sep. Handles quotes properly. Guesses tab or comma separator if "sep" is not given.
sort	(array a)
	renvoie: array
	Sorts array a
split	(string s, string or regex sep, optional boolean preserveAllTokens)
	renvoie: array
	Returns the array of strings obtained by splitting s with separator sep. If preserveAllTokens is true, then empty segments are preserved.
splitByCharType	(string s)
	renvoie: array
	Returns an array of strings obtained by splitting s grouping consecutive chars by their unicode type
splitByLengths	(string s, number n, ...)
	renvoie: array
	Returns the array of strings obtained by splitting s into substrings with the given lengths
startsWith	(string s, string sub)
	renvoie: boolean
	Returns whether s starts with sub
strip	(string s)
	renvoie: string
	Returns copy of the string, with leading and trailing whitespace omitted.
substring	(o, number from, optional number to)
	renvoie: Depends on actual arguments
	If o is an array, returns o[from, to]. if o is a string, returns o.substring(from, to)
sum	(array a)
	renvoie: number
	Sums numbers in array a
tan	(number d)
	renvoie: number
	Returns the trigonometric tangent of an angle
tanh	(number d)
	renvoie: number
	Returns the hyperbolic tangent of a value
toDate	(o, boolean month_first / format1, format2, ... (all optional))
	renvoie: date
	Returns o converted to a date object, you can hint if the day or the month is listed first, or give an ordered list of possible formats using this syntax: http://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html
toLowercase	(string s)
	renvoie: string
	Returns s converted to lowercase
toNumber	(o)
	renvoie: number
	Returns o converted to a number
toString	(o, string format (optional))
	renvoie: string
	Returns o converted to a string
toTitlecase	(string s)
	renvoie: string
	Returns s converted to titlecase
toUppercase	(string s)
	renvoie: string
	Returns s converted to uppercase
trim	(string s)
	renvoie: string
	Returns copy of the string, with leading and trailing whitespace omitted.
type	(object o)
	renvoie: string
	Returns the type of o
unescape	(string s, string mode ['html','xml','csv','url','javascript'])
	renvoie: string
	Unescapes all escaped parts of the string depending on the given escaping mode.
unicode	(string s)
	renvoie: string
	Returns an array of strings describing each character of s in their full unicode notation
unicodeType	(string s)
	renvoie: string
	Returns an array of strings describing each character of s in their full unicode notation
uniques	(array a)
	renvoie: array
	Returns array a with duplicates removed
xor	(boolean a, boolean b)
	renvoie: boolean
	XORs two boolean values
Controls
filter	(expression a, variable v, expression test)
	renvoie: array
	Evaluates expression a to an array. Then for each array element, binds its value to variable name v, evaluates expression test which should return a boolean. If the boolean is true, pushes v onto the result array.
forEach	(expression a, variable v, expression e)
	renvoie: array
	Evaluates expression a to an array. Then for each array element, binds its value to variable name v, evaluates expression e, and pushes the result onto the result array.
forEachIndex	(expression a, variable i, variable v, expression e)
	renvoie: array
	Evaluates expression a to an array. Then for each array element, binds its index to variable i and its value to variable name v, evaluates expression e, and pushes the result onto the result array.
forNonBlank	(expression o, variable v, expression eNonBlank, expression eBlank)
	renvoie: Depends on actual arguments
	Evaluates expression o. If it is non-blank, binds its value to variable name v, evaluates expression eNonBlank and returns the result. Otherwise (if o evaluates to blank), evaluates expression eBlank and returns that result instead.
forRange	(number from, number to, number step, variable v, expression e)
	renvoie: array
	Iterates over the variable v starting at "from", incrementing by "step" each time while less than "to". At each iteration, evaluates expression e, and pushes the result onto the result array.
if	(expression o, expression eTrue, expression eFalse)
	renvoie: Depends on actual arguments
	Evaluates expression o. If it is true, evaluates expression eTrue and returns the result. Otherwise, evaluates expression eFalse and returns that result instead.
isBlank	(expression o)
	renvoie: boolean
	Returns whether o is null or an empty string
isError	(expression o)
	renvoie: boolean
	Returns whether o is an error
isNonBlank	(expression o)
	renvoie: boolean
	Returns whether o is not null and not an empty string
isNotNull	(expression o)
	renvoie: boolean
	Returns whether o is not null
isNull	(expression o)
	renvoie: boolean
	Returns whether o is null
isNumeric	(expression o)
	renvoie: boolean
	Returns whether o can represent a number
with	(expression o, variable v, expression e)
	renvoie: Depends on actual arguments
	Evaluates expression o and binds its value to variable name v. Then evaluates expression e and returns that result

