**--------------------------------------------------------------**



**(LVL1B)**

Check the default source code to see if it says it outright

&#x20;

**--------------------------------------------------------------**



**(LVL2B)**

Try inputting nothing to check if the password file is there or not



**--------------------------------------------------------------**



**(LVL3B)**

Check for a type="hidden" tag under an input

Change it to "show" to show the file directory

Then type it into the URL



**--------------------------------------------------------------**



**(LVL4B)**

Check for a type="hidden" tag under an input

Change it to "show" but this time to show an email box that you then edit to your own



**--------------------------------------------------------------**



**(LVL5B)**

Literally the same thing as last time



**--------------------------------------------------------------**



**(LVL6B)**

Encrypt some sample text EG: abc123?!

Then (given that it is symmetrical), reverse the provided encrypted password, that will be the final password



**--------------------------------------------------------------**



**(LVL7B)**

There is a UNIX calendar function, where you can enter a year to view and it displays the calendar for it

If you enter EG: 2025 and then a ";" followed by a bash command of your choosing, it will do exactly that

EG: 2025 ; ls -la

That will display all the files within the current directory, giving you the password file directory.



**--------------------------------------------------------------**



**(LVL8B)**

Use SSI Injection to inject a payload of:



<!--#exec cmd="ls ../" -->



This lists the files within the directory, giving us the password location file



**--------------------------------------------------------------**





**(LVL9B)**

Again just use some UNIX and SSI injection to inject an appropriate payload as this one checks for whatever is in the payload. Get creative.



**--------------------------------------------------------------**



**(LVL10B)**

Find the cookie regarding authorization, if its set to no, use tamper tools to set it to yes, then refresh the page and send the request.



**--------------------------------------------------------------**



**(LVL11B)**

Use DIRB to find the directories. The ones on here were /e/l/t/o/n which then lead us to .htaccess, which then lead to /DaAnswer, which said "The answer is simple" which I had to take that literally. 



To which if we go to index.php NOT .html, it provides a password input box, which is required to complete the challenge



**--------------------------------------------------------------**





