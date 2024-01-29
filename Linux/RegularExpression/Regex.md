REGEX
Regular Expression (REGEX)



Will look for any key-word that contains "no" 
-i flag ignores case sensetivity, Linux by default is case sensitive
```
grep -i "no" /etc/passwd
```


Will look for any key word that contains "no" and one character after "no"
```
grep -i "no."/etc/passwd
```


Looks for key-word that contains "no" and two characters after "no" Every dot represents another character after the key-word
Note: you can also place the dot or dots infront of the key-word, which does the oppoisite 
```
grep -i "no.." /etc/passwd
```




Character classes
-----------------

grep -i "no[l]" /etc/passwd 
Looks for key-word that contains "no", and also specificly l after "no" key-word
This is referred to as a [Character Class] in Regex
Note: one set of square brackts is for one character.g


grep -i [0-9] /etc/passwd
Looks for anything that has a number 0-9 in /etc/passwd 


grep -i [^0-9] /etc/passwd
You can put the carrot sign, (arrow-up) to negate the numbers, meaning it will look for anything, BUT the numbers 0-9 in /etc/passwd
Note: one set of square brackets is for ONE character


grep -i [:] /etc/passwd 
Wil look for anything that contains a semi-colon in /etc/passwd 



Anchoring
-----------
$ is for anchor to end of line.
^ is for anchor to start of line. The ^ is called a "carrot symbol"

Referred to as "anchoring", grab only "nologin" if it's last word of the line 
```
grep -i "nologin$" /etc/passwd
```


Referred to as "anchoring", grab only "faze" if it's the first word of the line 
```
grep -i "^faze" /etc/passwd
```



grabs the only specific word, in this case I'm telling it to grab only faze
```
grep "^faze$" /etc/passwd
```


grabs any empty lines, you can used the -n flag to get the numbered line that is empty 

```
grep -n "^$" /etc/passwd
```


grabs words that only have a specified ammount of characters, In this scenario I'm telling it to look for words that have only three letter in /etc/passwd. I'm then using word count, to show me the total ammount of words that only contain three letters. 

```
grep -n "^...$" /etc/passwd | wc -l
```


? mean 0 or 1 occurance of previous character or character-class = same as {0,1}

Grouping
---------
()

Alternation/Choice
------------------





yes command is used to output multiple pieces of text into a file, usually used in scripts.

yes "some-text" | head -n 200 >> file.txt