#Symbols
Symbols are unique identifiers that are considered code, not data.

:unique_symbol #symbols are words that are prefixed with a colon.

When creating a symbol, if you are using :name there shouldn't be any spaces but if you use :"first name" this is acceptable.

Symbols are unique identifies - commonly used for hash keys (they provide certain advantages over strings)

The main difference is that if you had the same string multiple times throughout your code, each instance is considered a separate object (with a new object ID), whereas a symbol will only exist once and if referenced multiple times, you will be referencing the same object with the same object ID - identical symbols are a single internal object.

an example:
"a string".object_id
=> 70358630335100
"a string".object_id
=> 70358640625960
"a string".object_id
=> 70358644379620

:a_symbol.object_id
=> 1086748
:a_symbol.object_id
=> 1086748
:a_symbol.object_id
=> 1086748

**Constants can't become symbols?**

Strings can be converted into symbols "String".to_sym => :String

If you use tring interpolation on a symbol, this is the same as calling .to_s on the symbol

**It's important to realize that symbols are not "immutable strings", though they are immutable. None of the interesting string operations are available on symbols.

N.B Symbols do not have access to many of the string methods e.g start_with? so they will need to be converted to strings to_S beforehand.

It isn't a good idea to dynamically create a lot of symbols in ruby as this can lead to a memory leak as you are allocating a lot of memory that can't be freed until your program ends. 
Symbols are best used if:
1. Yneed to repeatedly access the symbol
2. You won't need to modify them
3. Where you care more about the identity of the variable than its value e.g Hash keys

An example of a bad use case for dynamically creating symbols is with user input. Because symbols act as code, if you don't validate user input against allowed values this can allow users to cause your program to consume large amounts of memory that will never be garbage collected.
