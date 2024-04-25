<h3> What is the grep command used for?</h3>
<p> The grep is a useful command that allows the ability to search for a specific  keyword on a linux server, whether that being a file, pdf file, zipped file, proccess id.</p>


pgrep nginx
pgrep is used for procces id 


fgrep
fgrep is used 

  
zgrep 
zgrep is used to grep from zip files, 


pdfgrep is used to grep from pdf files.


In the command below, I'm grepping for the keywords in /var/log/messages for any crash messages, also I am adding another grep to specifically narrow it down the date
```
grep -iE "reboot|shutdown|boot|error|fail|failed|warn|warning|disabled" /var/log/messages | grep -iE 'Apr 14'
```
