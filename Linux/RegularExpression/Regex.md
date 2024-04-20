<h1> Regular Expression (REGEX) </h1>
[] character classes
^ Front of line Anchor
& End of line Anchor
| OR
\ Escape character

Literal Characters:
Literal characters in regex are the most commonly used, for example say I want to find my user from /etc/passwd I would grep it by describing the name in quotes.
grep "my-user" /etc/passwd


Meta Characters:
Meta characters are characters that have special meaning.


```
grep -i "no" /etc/passwd
```
grep -i "no" /etc/passwd
Will look for any key-word that contains "no" 
-i flag ignores case sensitivity, Linux by default is case sensitive


grep -i "no."/etc/passwd
Will look for any key word that contains "no" and one character after "no"


grep -i "no.." /etc/passwd
Looks for key-word that contains "no" and two characters after "no" Every dot represents another character after the key-word
Note: you can also place the dot or dots in front of the key-word, which does the opposite 


Character classes
-----------------

grep -i "no[l]" /etc/passwd 
Looks for key-word that contains "no", and also specifically l after "no" key-word
This is referred to as a [Character Class] in Regex
Note: one set of square brackets is for one character.


grep -i [0-9] /etc/passwd
Looks for anything that has a number 0-9 in /etc/passwd 


grep -i [^0-9] /etc/passwd
You can put the carrot sign, (arrow-up) to negate the numbers, meaning it will look for anything, BUT the numbers 0-9 in /etc/passwd
Note: one set of square brackets is for ONE character


grep -i [:] /etc/passwd 
Wil look for anything that contains a semi-colon in /etc/passwd 



Anchoring 
$ Dollar symbol, is for anchor to end of line.
^ Carrot symbol, is for anchor to start of line. The ^ is called a "carrot symbol"
---------------

grep -i "nologin$" /etc/passwd
Referred to as "anchoring", grab only "nologin" if it's last word of the line 

grep -i "^faze" /etc/passwd
Referred to as "anchoring", grab only "faze" if it's the first word of the line 

grep "^faze$" /etc/passwd
grabs the only specific word, in this case I'm telling it to grab only faze

grep -n "^$" /etc/passwd
grabs any empty lines, you can used the -n flag to get the numbered line that is empty 


grep -n "^...$" /etc/passwd | wc -l
grabs words that only have a specified amount of characters, In this scenario I'm telling it to look for words that have only three letters in /etc/passwd. I'm then using word count, to show me the total amount of words that only contain three letters. 


? mean 0 or 1 occurrence of previous character or character-class = same as {0,1}
makes previous character or char class optional, an example of usage is shown in grouping.


Grouping 
---------------
egrep "(az")?e" /etc/passwd
In the example above it grabs "(az)" as optional, and ?e as mandatory.
so the computer will display any words that contain "(az)" characters and e as mandatory,
it will also look for aze as a whole.

The "(az)" is considered as grouping.

When using multiple meta characters, we must use extended grep (egrep), This allows us to utilize multiple meta characters. 




Alternation/Choice 
----------------------
egrep "(f|t)aze" /etc/passwd
In this example it will grab the user "faze" and "taze" as well as aze 
In this example it grabs the user "faze" from /etc/passwd and or it grabs the user "taze" as well.
| is used to specify an or condition.
Also note we are using grouping with the alternation/choice




Escape Character 
--------------------
egrep "\:\:" /etc/passwd
In this example it will grab and display only two semi-colona nothing more.




Repetitions {} 
Indicate specific, minimum or maximum occurrences of previous character or character class
------------------
egrep "[0-9]{3}" /etc/passwd
In this example it will grab numbers 0-9, but with the repetition of 3, meaning, show me all the 
numbers 0-9 that have 3 repetitions in those numbers.











yes command is used to output multiple pieces of text into a file, usually used in scripts.

yes "some-text" | head -n 200 >> file.txt
