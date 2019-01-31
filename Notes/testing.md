# Testing

## Why Test?
The benefit of writing tests - that you run often - is that it becomes increasingly difficult for parts of your application to break without you knowing about it. Testing also helps you with writing better code.

## Unit Testing
This involves testing small chunks of code - functions/ methods. If you find your tests calling multiple functions, you should try and split them into more simple tests. The more tests the better.
Try to test the public interface of a class as these are less likely to change in a way that would render tests useless e.g during code refactoring.

## What to test?
You should test the purpose of that particular method:
* Does it produce the expected action?
* Does the method return the correct value?
* Does it causes a particular side effect?

*N.B. You shouldn't unit test an API call, they aren't necessary and can slow down your tests - you can use integration tests to check that the API is doing its job. You can check that the API is being passed the correct parameters, that the returning value is the exected data type, that the error function is behaving correctly etc. 
