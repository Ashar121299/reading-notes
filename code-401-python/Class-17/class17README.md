## Python Regular Expression Tutorial

_Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not.
If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use.
They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, 
or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining._

### importing re

In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this
module with the help of import:

import re

### basic/ordinary characters

we can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves 
exactly and do not have a special meaning in their regular expression syntax.
Examples are 'A', 'a', 'X', '5'.

pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")


#### notice the r at the start of the pattern Cookie,This is called a raw string literal. It changes how the string literal is interpreted. Such literals are
#### stored as they appear.

### wild or special characters

Special characters are characters that do not match themselves as seen but have a special meaning when used in a regular expression. For simple understanding,
they can be thought of as reserved metacharacters that denote something else and not what they look like.

A period. Matches any single character except the newline character.

re.search(r'Co.k.e', 'Cookie').group() /// Cookie

re.search(r'^Eat', "Eat cake!").group() /// Eat

re.search(r'cake$', "Cake! Let's eat cake").group() /// Cake

re.search(r'[0-6]', 'Number: 5').group()  /// '5'

re.search(r'Number: [^5]', 'Number: 0').group() /// 'Number: 0'

re.search(r'Just a \regular character', 'Just a \regular character').group() /// 'Just a \regular character'

print("Lowercase w:", re.search(r'Co\wk\we', 'Cookie').group()) /// Lowercase w: Cookie

print("Lowercase s:", re.search(r'Eat\scake', 'Eat cake').group()) /// Lowercase s: Eat cake

print("How many cookies do you want? ", re.search(r'\d+', '100 cookies').group()) /// How many cookies do you want?

###  repetitions 

It becomes quite tedious if you are looking to find long patterns in a sequence. Fortunately, the re module handles repetitions using the following special
characters:

Checks if the preceding character appears one or more times starting from that position.

re.search(r'Co+kie', 'Cooookie').group() /// 'Cooookie'

re.search(r'Ca*o*kie', 'Cookie').group() /// 'Cookie'

re.search(r'Colou?r', 'Color').group() /// 'Color'



###  groups and named groups

The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis ()
are called groups. The parenthesis does not change what the expression matches, but rather forms groups within the matched sequence. You have been using the group() 
function all along in this tutorial's examples. The plain match.group() without any argument is still the whole matched text as usual.

###  greedy vs. non-greedy matching.

When a special character matches as much of the search sequence (string) as possible, it is said to be a "Greedy Match". It is the normal behavior of a regular
expression, but sometimes this behavior is not desired:


### useful functions 

#### 1.compile(pattern, flags=0)

Regular expressions are handled as strings by Python. However, with compile(), you can computer a regular expression pattern into a regular expression object.
When you need to use an expression several times in a single program, using compile() to save the resulting regular expression object for reuse is more efficient
than saving it as a string. This is because the compiled versions of the most recent patterns passed to compile() and the module-level matching functions are cached.

#### 2.search(pattern, string, flags=0)

With this function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match. It returns a 
corresponding match object if found, else returns None if no position in the string matches the pattern. Note that None is different from finding a zero-length 
match at some point in the string.

#### 3.match(pattern, string, flags=0)

Returns a corresponding match object if zero or more characters at the beginning of string match the pattern. Else it returns None, if the string does not match
the given pattern.

#### 4.findall(pattern, string, flags=0)

Finds all the possible matches in the entire sequence and returns them as a list of strings. Each returned string represents one match.

#### 5.finditer(string, [position, end_position])

Similar to findall() - it finds all the possible matches in the entire sequence but returns regex match objects as an iterator.

#### 6.sub(pattern, repl, string, count=0, flags=0)
####   subn(pattern, repl, string, count=0)

sub() is the substitute function. It returns the string obtained by replacing or substituting the leftmost non-overlapping occurrences of pattern in string by the
replacement repl. If the pattern is not found, then the string is returned unchanged.

The subn() is similar to sub(). However, it returns a tuple containing the new string value and the number of replacements that were performed in the statement.

#### 7.split(string, [maxsplit = 0])

This splits the strings wherever the pattern matches and returns a list. If the optional argument maxsplit is nonzero, then the maximum 'maxsplit' number of
splits are performed.


### compilation flags


An expression's behavior can be modified by specifying a flag value. You can add flags as an extra argument to the different functions that you have seen in this
tutorial. Some of the more useful ones are:

#### IGNORECASE (I)

- Allows case-insensitive matches.
#### DOTALL (S)

- Allows . to match any character, including newline.

#### MULTILINE (M)
- Allows start of string (^) and end of string ($) anchor to match newlines as well.

#### VERBOSE (X)

- Allows you to write whitespace and comments within a regular expression to make it more readable.
