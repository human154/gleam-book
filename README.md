# The Gleam Programming Language

## Introduction

Gleam is a friendly language for building type-safe, scalable systems!

It compiles to Erlang and has straightforward interop with other BEAM languages such as Erlang, Elixir and LFE.

### The Unique Characteristics of Gleam

Gleam is built on the foundation of the Erlang ecosystem.  Gleam code runs on a virtual machine (V.M.) called "Beam".  The Beam V.M. is a unique marvel of industiral-strength technology.  It is the product of countless hours of engineering, and it gives Gleam the rare feature of fault tolerence.  Combine this with convenient and fast concurrency, and you have the unique combination of superpowers which Gleam inherites by running on the Beam Virtual Machine. 

Two things, taken together, set Gleam apart from other languages that target the Beam V.M.:

1.  Static Type Checking. 

    Currently, the well established languages in the Erlang ecosystem are dynamically typed. In contrast, Gleam leverages the strongest advantages of static typing:

    - As is common with compiled languages, the Gleam compiler checks your source code and insists you address any errors before the code is run. These errors, which are caught by the compiler and are fixed early, are errors that your user/customer will never need to experience and they are errors which you will never be called to fix in the middle of the night. The bottom line here is that Gleam's compiler enables the creation of better quality, more reliable software that requires less maintenance.
    - When your Gleam code base grows into a larger, more complex project, you can continue to make changes fearlessly. The compiler will identify any related, incidental changes, that need to be made anywhere in the entire code base.
    - Gleam provides carefully crafted, super helpful error messages, leaving you with the experience of having an extremely capable and friendly pair programmer.

2.  Gleam's Enthusiastic Community!

     Louis Pilford, Gleam's primary creator, has shown a stong desire and ability to fostor the Gleam community. Louis already has more than 120 enthusiastic sponsors through github. Amung those sponsors is José Valim, the creator of the very successful Beam language, Elixir.


Aside from targeting the Beam V.M., Gleam can also compile to Javascript.

Being easy to learn is one of Gleam's primary goals.  To keep the language simple, Gleam is designed to have only one way of writing code, as opposed to providing alternative ways for the programmer to express themselves.

Given the language's simplicity, and the fact that it is written in Rust, the Gleam compiler is naturally very fast at compiling Gleam source code.



