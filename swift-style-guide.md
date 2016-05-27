#Swift Style Guide

When writing this book, and when writing Swift code for our own projects, we try to stick to the following rules:

Readability is most important. This is helped by brevity.

Always add documentation comments to functions — especially generic ones.

Types start with UpperCaseLetters. Functions and variables start with lowerCaseLetters.

Use type inference. Explicit but obvious types get in the way of readability.

Don’t use type inference in cases of ambiguity or when defining contracts (which is why, for example,funcs have an explicit return type).

Default to structs unless you actually need a class-only feature or reference semantics.

Mark classes as final unless you’ve explicitly designed them to be inheritable.

Use the trailing closure syntax, except when that closure is immediately followed by another opening brace.

Use guard to exit functions early.

Eschew force-unwraps and implicitly unwrapped optionals. They are occasionally useful, but needing them constantly is usually a sign something else is wrong.

Don’t repeat yourself. If you find you have written a very similar piece of code more than a couple of times, extract it into a function. Consider making that function a protocol extension.

Favor map and reduce. But don’t force it: use a for loop when it makes sense. The purpose of higher-order functions is to make code more readable. An obfuscated use of reduce when a simple for loop would be clearer defeats this purpose.

Favor immutability: default to let unless you know you need mutation. But use mutation when it makes the code clearer or more efficient. Wrap that mutation in a function to isolate unexpected side effects.

Swift generics tend to lead to very long function signatures. Unfortunately, we have yet to settle on a good way of breaking up long function declarations into multiple lines. We’ll try to be consistent in how we do this in sample code.

Much to the dismay of half of this book’s authorship, the “cuddled else” is official Swift style: } else {.