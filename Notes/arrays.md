#Arrays

You can create an array using Array.new constructor method which creates an empty array.

You can also create an array using an array literal:
arr = [1, 2]

Shorthand way to push an item on to an array
arr << 1
> [1]

You can access an item in an array at a given index using:
array[index]
> value
If we try to retrieve an element that does not exist, we get back nil.

You can also add a value to a specific index, if there is already an element at that position, it will be overwritten.

array[index] = "value"

##Slicing Arrays
You can slice an array by setting a starting index, and stating how many elements to include. This creates a new array with the slice of selected elements, or returns nil if nothing is found.

*N.B You have to think of indexes in a different way when slicing an array, the index is placed before the element, as opposed to specifying the actual elemets locations. This is necessary functionality to allow ranges to be set.
array[start, length] > new_ary or nil

array = [ :peanut,   :butter,   :and,   :jelly  ]
        0          1          2       3       4

The above highlights that although there are 4 elements in the array, with an index of 0 to 3, when slicing the array, position 4 is included in the array. This is why if you were to write:
array[4, 1] > [] - **you get a blank array, instead of nil**
array[5,1] > nil **This returns nil as that reference point doesn't exist within the array**

You can use ranges to slice an array, this works the same as accessing an element using its index position.
array[0..2] > this will select all elements from index 0, up to and including index 2
array[0...-1] > this will select all elements from index 0, up to but excluding index -1

#Array Methods
array.push(*value*) > adds the given value to the end of the array
array.pop() > returns the last value in an array
array.shift() > returnes the first value in an array
array.unshift(*value*) > adds the given value to the front of the array

##Array Assignment
###Non-parallel assignment
names = ["John", "Smith"]

###Parallel assignment

If you want to assign each element in an array to a name variable, you can use parallel assinment:
first_name, last_name = ["John", "Smith"]
> first_name > "John"
> last_name > "Smith"

If you have multiple values in an array but there are more elements than you have created variable names for, the additional elements will be ignored.

first_name, last_name = ["John", "Smith", "III"]
> first_name > "John"
> last_name > "Smith"

If you are unsure about the number of elements that will be in an array you can use the splat operator (*) to signify that all remaining elements will be assigned to a given variable.

first_name, *last_name = ["John", "Smith", "III"]
> first_name > "John"
> last_name > ["Smith", "III"]

If you attempt parallel assignment with too few elements in the array, it will return nil for the additional variable.

first_name, last_name = ["Sally"]
first_name > "Sally"
last_name > nil

You can also use parallel assignments with subarrays. 

first_name, last_name = [["Rachel", "Marie"], "Smith"]
first_name > ["Rachel", "Marie"]
last_name > "Smith"

If you attempt to use parallel assignment but have only declared one variable (N.B the trailing comma after the first variable), it will only assign the first element to a variable.

first_name, = ["John", "Smith"]
first_name > "John"


You can also swap values using parallet assignment.
first_name = "Smith"
last_name = "John"
first_name, last_name = last_name, first_name
first_name > "John"
last_name > "Smith"
