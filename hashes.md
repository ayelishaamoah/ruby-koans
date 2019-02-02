#Hashes - Key-value pairs

A Hash assigns values to keys, so that values can be looked up by their key - any values can be used as keys.

A common approach is to use symbols as keys -> They are immutable and improve performance

Hash.new creates an empty Hash > {}

numbers = { 
    "one" => "eins", 
    :two => "zwei", 
    3 => "drei" 
}

You can access values in a similar way to an array but instead of an index ID, you provide the key:

numbers["one"] > "eins"
numbers[:two] > "zwei"
numbers[3] > "drei"

If they key doesn't exist, the nil value will be returned.

##.fetch
As a better alternative, you can use .fetch( key , default ) or .fetch(key) {| key | block } > obj

This allows you to dictact what behaviour should execute when the key doesn't exist. You can eithr provide a default message or a block of code that should run. 


##Default values
If a value isn't provided, a default value will be returned for a particular key.
Hash.new("default")
hash[:one] << "uno"
hash[:two] > ["default"]

###Interesting behaviour to note

If you assign a blank array as the default value, you pass the default reference of array to all elements in the hash - all elements in hash refers same array. 
hash = Hash.new([])

hash[:one] << "uno"
hash[:two] << "dos"

hash[:one] > ["uno", "dos"]
hash[:two] > ["uno", "dos"]
hash[:three] > ["uno", "dos"]

A way to avoid this unexpected behaviour is to pass a block of code that will ensure that each hash value is creating a new array.

hash = Hash.new {|hash, key| hash[key] = [] }

hash[:one] << "uno"
hash[:two] << "dos"

hash[:one] > ["uno"]
hash[:two] > ["dos"]
hash[:three] > []


