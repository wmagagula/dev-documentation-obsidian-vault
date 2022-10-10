What are they?

- Say we have Func<A,B> and Action<A,B>
- Both Func<A,B> and Action<A,B> (known as delegates) are pointers to methods that have the same type signatures as they've been specified.

These can be used to define callback methods and implement event handling

So use Func<A,B> when the method it points to accepts zero/one/more args and returns a value (of any type hence <T>).  

And use Action<A,B> when the method it points to accepts zero/one/more args and returns void

Use Func<A,B,C> if you have a method that takes two arguments and returns type C.

Using Action<A,B> if you have a method that takes two arguments and returns void

  

[12:35] Francois Malan

So now one ccan see another subtle difference between

Func<A,B> and Action<A,B>

The Func takes one argument less