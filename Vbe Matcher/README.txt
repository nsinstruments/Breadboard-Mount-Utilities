Vbe Matcher
===========
This is a simple widget to match the Vbe on two bipolar transistors. 

Theory of Operation
-------------------
See the document by Ian Fritz in this repository.

Caveat Emptor
-------------
This circuit adequately reproduces the Ian Fritz circuit described in the
paper, along with the added trimmer. If we were breadboarding this circuit,
that would be the end of it. However, given that it's a PCB, practically there
are quite a few nice things that could have been done but weren't. For
example, there could be posts to clip an alligator clip for a multimeter, thus
saving one or two of your four hands. It works, but it isn't streamlined for
ease of use. One of the nice things about the Ian Fritz circuit, however, is
that it's intuitive and simple and easy to understand and modify.

Another thing that I should mention is that you should consider whether the
transistors in question need to have the same Vbe or just the same Vt, or
temperature dependency. Proximity gives you the same Vt, and you don't need to
match. In my case, Vt is usually the important part, and so I don't use this
circuit very often.
