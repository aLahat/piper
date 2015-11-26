# piper
A language for computational protocols

This is an interpreter for a basic language for linux protocols.
This is designed for when many steps are used in a pipeline and/or many options are used.

This tool enables to write a script based in bash that can be easily read and shared.
Instead of writing a command such as:
'''
command -o 2 -f 3 -t te.txt -v 'aawd -nd adw.csv' | grep awd > out.csv
'''
It can be written as:
'''
##test command (made up jibijabber)
command	-o	2 	#just a random letter and value as options
	-f	3 	#more jibijabber
	-t 	te.txt 
	-v 
	'		#as tabs and newlines are trivial it is easy to see the options
	aawd	-nd 	
		adw.csv
	' 
| 
grep	awd 		#this greps the output of the first command
> 
out.csv			#and this just pushes it to the end
'''

In our script the command can be written with tabs, newlines, and comments making it easier to follow the commands.

In addition there is also options of using variables, lists, and wildcards to iterate through the same command:
'''
## command with a variable
#cliche = hello_world	#to set a variable just call it after the title with a line starting with hash
echo [[cliche]]		#it is used by being called between brackets

## command with a list
#numbers = 1 2 3 4 5	#to set a list is the same as setting a variable but with spaces in between variables
echo [[numbers]]	#it us used the same way as a variable

## command with wild cards
#files = *.txt		#just the same as a variable
echo [[files]]		#it is this simple
'''

piper allows for reviewing the comandsone by one (-b), printing the parsed comands (-v), viewing specific steps (-s). and most importatly running them (-r).

