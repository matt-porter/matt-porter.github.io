---
layout: post
title:  "Why Python => Rust?"
date:   2018-02-03 21:21:19 +0000
categories: rust python opinion
---
What attracts Python developers to Rust? Rust may seem like an odd choice as a 
Pythonista's second language. Python is a very high-level language, with 
dynamic typing and garbage collection. Rust on the other hand has strict 
typing and requires the developer to give much more thought to memory 
handling. 

So why Rust? For me, it offers something which Python doesn't - the 
performance of a compiled, non-gc language - while still appealing to the same 
ideals that I appreciate within Python and the Python community. Despite being 
compiled, Rust manages to provide many of the high-level constructs that 
Python programmers will be used to - iterators for example. I find that Rust 
shares many of the goals of Python; programmer productivity and a pragmatism 
in design choices. For these reasons, I have found the Rust community to be a 
good "fit", in the same way that Python was when I first picked it up. 

Not only that, but it's becoming easier and easier to integrate the two 
languages. Rust's lack of garbage collection is *useful* if you're developing 
Python extensions. You can find a few different methods of integation, 
including [PyO3][pyo3] - which binds directly to the CPython API (meaning it
wouldn't work so well with PyPy for example), and [milksnake][milksnake] 
which uses CFFI to bind to a rust-built dynamic library. 

[pyo3]: https://github.com/PyO3/pyo3  
[milksnake]: https://github.com/getsentry/milksnake

Take this example of iterating over a range, and printing the values; first
in Python:

{% highlight python %}
def main():
  for i in range(10):
    print("Number {}".format(i))
{% endhighlight %}

And then in Rust:

{% highlight rust %}
fn main() {
  for i in 0..10 {
    println!("Number {}", i);
  }
}
{% endhighlight %}

Easy! Obviously that's a silly, simple example. But it serves to highlight that
Rust and Python aren't so far apart, even thought their methods are different.
