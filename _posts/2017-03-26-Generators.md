---
layout: posts
title: Generators
---

Generators
----------

Generators (also called simple generators for historical reasons) are relatively new to Python,
and are (along with iterators) perhaps one of the most powerful features to come along for years. However, the 
generators concept is rather advanced, and it may take a while before it "clicks" and you see how it works or
how it would be useful for you. Rest assured that while generators can help you write really elegant code, you can
certainly write any program you wish without a trace of generatos.

A generator is a kind of iterator that is defined with normal function syntax. Exactly how generators
work is best known through example. Let's first have a look at how you make them and use them, and take a peek 
under the hood.  

Making a generator
------------------

Making a generator is simple; it's just like making a function. I'm sure you are starting to tire of 
the good old Fibonacci sequence by now, so let me do something else.

Example

   def nth(gen, n): 

     for i in xrange(n - 1): 

              gen.next() 

         return gen.next() 

   def gen_primes(): 

      yield 2 
      yield 3 
      i = 5 

     while True: 

     if is_prime(i): 

        yield i 

        i += 2 

   def is_prime(n): 

      if n <= 1: return False 

         elif n == 2: return True 

         elif n % 2 == 0: return False 

         else: 

            d = 3 

      while d * d <= n: 

         if n % d == 0: return False 
 
         d += 2 return True