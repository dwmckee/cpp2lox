# cpp2lox

A casual attempt to reproduce Robert Nystrom's lox in Herb Sutter's C++
syntax 2.

## Build

The current build is based on meson and requires at least version 0.55.0
(for support of the `patch_directory` feature in wrap files).

### Build credit

I shamelessly stole the meson build support for `cppfront` from [Jussi
Pakkanen's](https://github.com/jpakkane) [cpp2meson
repository](https://github.com/jpakkane/cpp2meson), only I took
advantage of `patch_directory` to maintain the build file in *my*
repository instead of creating a cutout for cppfront. Thanks, Jussi!

## Discussion

There are plenty of things that `cppfront` does not yet support, and
that is going to affect how we write the code.

Things missing include

* `enum` and `switch` which mean we'll have to write mixed code. A
  `-pure-cpp2` version will have to wait for improvements to the
  transpiler.

* Be design there is no support for owning raw pointer and unsafe
  allocation strategies like `new`. This means I have to decide between
  using mixed code to implement the garbage collector or simply using a
  cpp2 arena in the first place. The latter is more convenient but the
  former more in keeping with the pedagogical nature of *Crafting
  Interpreters*. I've already given up on explicit dynamic arrays in
  favor of `std::vector` but that is largely because I've long been
  conversant with dynamic arrays in C, so they don't offer me anything
  new.

Things that may or may not be there but I don't know how to invoke include 

* **Separate compilation** which means I'm starting a all in one big
  file version. Really hope to figure this out.

## Repository

I intend to tag version for places where the book and I both get to a
working intermediate state.

