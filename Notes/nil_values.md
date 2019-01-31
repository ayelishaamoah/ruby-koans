# The Nil value

In Ruby, the nil value is an object that represents "nothing".

It is one of only 2 falsy values in Ruby - nil & false. Everything else is truthy - including 0.

The nil object can lead to frequent undefined method nil:NilClass errors. A common way to guard against this is to use && or ifs to check for nils - a cleaner way to organise your code would be to use the *Null Object Pattern* to wrap this behaviour with a defined object e.g a pre-defined error message.

-[ ] Read more here - https://littlelines.com/blog/2013/06/22/how-to-guard-against-ruby-nil-errors