#Swift Style Guide

When writing this book, and when writing Swift code for our own projects, we try to stick to the following rules:

1. Readability is most important. This is helped by brevity.

1. Always add documentation comments to functions — especially generic ones.

1. Types start with UpperCaseLetters. Functions and variables start with lowerCaseLetters.

1. Use type inference. Explicit but obvious types get in the way of readability.

1. Don’t use type inference in cases of ambiguity or when defining contracts (which is why, for example,funcs have an explicit return type).

1. Default to structs unless you actually need a class-only feature or reference semantics.

1. Mark classes as final unless you’ve explicitly designed them to be inheritable.

1. Use the trailing closure syntax, except when that closure is immediately followed by another opening brace.

1. Use guard to exit functions early.

1. Eschew force-unwraps and implicitly unwrapped optionals. They are occasionally useful, but needing them constantly is usually a sign something else is wrong.

1. Don’t repeat yourself. If you find you have written a very similar piece of code more than a couple of times, extract it into a function. Consider making that function a protocol extension.

1. Favor map and reduce. But don’t force it: use a for loop when it makes sense. The purpose of higher-order functions is to make code more readable. An obfuscated use of reduce when a simple for loop would be clearer defeats this purpose.

1. Favor immutability: default to let unless you know you need mutation. But use mutation when it makes the code clearer or more efficient. Wrap that mutation in a function to isolate unexpected side effects.

1. Swift generics tend to lead to very long function signatures. Unfortunately, we have yet to settle on a good way of breaking up long function declarations into multiple lines. We’ll try to be consistent in how we do this in sample code.

1. Much to the dismay of half of this book’s authorship, the “cuddled else” is official Swift style: } else {.