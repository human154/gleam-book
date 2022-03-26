# The Gleam Programming Language

>Gleam is a friendly language for building type-safe, scalable systems!
>
>It compiles to Erlang and has straightforward interop with other BEAM languages such as Erlang, Elixir and LFE.    

## Chapter 1. Introduction

### The Characteristics of Gleam

#### Fault Tolerence, Concurrency And Distribution!

Gleam code runs on a virtual machine (V.M.) called "Beam".  The Beam V.M. is a unique marvel of industiral-strength technology.  It is the product of countless hours of engineering. The Beam ecosystem gives Gleam the rare feature of fault tolerence.  Combine this with convenient and fast concurrency with excellent, effortless multi-core support, as well as support for distribution and you have the unique combination of superpowers which Gleam inherites by running on the Beam Virtual Machine. 

#### Enhanced Code Quality Through Static Type Checking

Currently, the well established languages in the Erlang ecosystem are dynamically typed. In contrast, Gleam leverages the strongest advantages of static typing.

The Gleam compiler checks your source code and insists you address any errors before the code is run. These errors, which are caught by the compiler and are fixed early, are errors that your user/customer will never need to experience and they are errors which you will never be called to fix in the middle of the night. 

In type checked languages, you put in more up-front effort into crafting your code. This extra effort results in the creation of higher quality, more reliable software that requires less maintenance compared to dynamically typed languages.

#### Productivity

As your Gleam code base grows, Gleam's static typing will help you to continue to make changes fearlessly in the midst of the complexity. The compiler will identify any related, incidental changes that need to be made, anywhere in the entire code base.

Gleam provides carefully written, super-helpful error messages, leaving you with the experience of having an extremely capable and friendly pair programmer.

#### Compiles To Javascript

Aside from targeting the Beam V.M., Gleam can also compile to Javascript! This means the enormous Javascript ecosystem can be leverged. It also lays the foundation for fullstack web developmeent.

#### Easy To Learn

Being easy to learn is one of Gleam's primary goals.  To keep the language simple, Gleam is designed to have only one way of writing code, as opposed to providing alternative ways for the programmer to express themselves.

#### Fast Compilation

Gleam's simplicity means that Gleam's compiler is very fast and you won't have long wait times for compiling Gleam source code. The compiler is written in Rust.

#### Immutable Data

Languages targeting the Beam V.M. work with imutable data. When we talk about data types in the next chapter we'll see how this simplifies the language and makes it easier to reason about.  Gleam uses a functional programming style which is a great match for working with immutable data.

If you haven't worked in a functional style before, then you are in the right place! Gleam is amung the simplest and friendliest functional languages in existence!

#### A Great Community!

Louis Pilford, Gleam's primary creator, has shown a stong desire and ability to fostor the Gleam community. Louis already has more than 120 enthusiastic sponsors through github. Amung those sponsors is José Valim, the creator of the very successful Beam language, Elixir.

You are very welcome and we are happy to have you join in!

You can talk to and get help from other Gleam community members in the following forums: 
- [Gleam’s web chat on Discord.](https://discord.gg/Fm8Pwmy)
- [Gleam discussions on Github.](https://github.com/gleam-lang/gleam/discussions)
- [Gleam’s threads on the Erlang Forums](https://erlangforums.com/gleam)

### The Limitations Of Gleam
Gleam is a young language. The Gleam community is working hard to remedy the following limitations:
- A limited number of tutorials available online.
- A limited ecosystem of libraries. This is offset by the fact that Gleam programs can easily make use of the entire Beam ecosystem (including libraries from Erlang, Elixir, LFE and and other Beam languages) as well as the Javascript Ecosystem
- There is no repl yet for Gleam.
- Limited documentation.
- Limited Editor Support.
- String interpolation and default function arguments are not yet a part of the language.

### Contributing

The Gleam community is growing but still young. There are plenty of opportunities to make a contribution:
- Write a blog post or tutorial about Gleam.
- Make something with Gleam and share your feedback with the Gleam developers.
- Contribute to the [Gleam ecosysten](https://github.com/gleam-lang).
- If you're interested in writing Rust then you could help develop the [compiler](https://github.com/gleam-lang/gleam).
- [Sponsor Gleam development](https://github.com/sponsors/lpil?o=esb).

## Chapter 2. Hello Data!

### Example 1

```gleam
import gleam/io     // The io module provides the println() function below.

pub fn main() {
  io.println("Hello Gleam!")
}
```

### Example 2

```gleam
import gleam/io
import gleam/erlang
import gleam/string

pub fn main() {
  assert Ok(name_with_newline) = erlang.get_line("Please Enter Your Name >> ")
  let name = string.trim_right(name_with_newline)
  let greeting = string.concat(["Welcome ", name, "!"])
  io.println(greeting)
}
```

### Immutable Data Makes Gleam Code Simpler

In most programming languages there are two ways to work with data:
1. Alter/mutate data right where it sits in memeory.
2. Create new data which is seperate from, but based on existing data. 

Most languages will allow data to be altered:

```gleam
// This isn't Gleam !!!

x = 1
increment(x)
// Now x is 2
```

The above mutation is not possible in Gleam!

In Gleam, we can only create seperate, new data, which is derived from existing data:

```gleam
let x = 1
let y = increment(x)
// Now x is 1 and y is 2.
```

Gleam code is a bit simpler to read and understand than languages that allow both ways of working with data. When you see something like `increment(x)`, you can immediately know that the function does not change `x` because the language doesn't allow changing data. Likewise, when you're writing Gleam code, you never need to decide between mutating data or creating new data, you always create new data.

### Shadowing

Gleam does allow us to create new names that are the same as existing names:
```gleam
let z = "cat"
let z = 4  // This new z makes the one defined in the line above inaccessible after this line.
// z is 4
```
Nothing relating to the first `z` changed, except that it became inaccessible after a new, identical name, was created.

The "shadowed" name can be used on the right of the equals sign:
```gleam
let x = 5 // This x will be shadowed on the next line.
let x = x + 1 // The new x is given a value of 6.
// The first x defined is inaccessible here.
```

Shadowing can make writing code easier at times, but generally its probably better to think of a discriptive new name to represent new data.

