#Strings

You can use either double "" or single '' quotes to signify a string.

You can use double quotes to create strings with single quotes e.g:
string = "Don't"

The escape character \ allows you to insert characters in a string:
"He said, \"Don't\""

With double quotes we can use command expansion and backslash notation whereas single quotes do not.
puts "embedded #{1 + 1} expression" #"embedded 2 expression"

puts 'embedded #{1 + 1} expression' #"embedded #{1 + 1} expression"


Flexible strings allow you to handle difficult strings - it avoids *leaning toothpick syndrome* (the number of escape characters in a string gets to a point where it becomes undreadable).  

%(flexible quotes can 
handle both ' and " 
characters)

You can choose the delimeter to wrap the string e.g {}, !!, []
If you add a newline within a flexible string, it will add a newline character.

Here document is a syntax which can express strings spanning multiple lines, the characters between the two identifiers - something other than EOS can be used.
<<EOS
It was the best of times,
It was the worst of times.
EOS