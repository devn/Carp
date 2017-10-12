# Todo

## Critical Bugs
* The 'range' function is fully generic (for all 'a') but only compiles when 'a' is numeric type

## Big Language Features
* Generic data types (apart from Array, which already is)
* Tagged unions (also known as "sum types" or "enums")
* Lambdas (anonymous functions)

## Smaller Language Features ("niceties")

## Language Design Considerations
* What's the correct type of the variable in a set!-form, i.e. (set! &x value) or (set! x value)
* The 'copy' function should probably be a special form, just like 'ref'?
* Is some kind of interface/typeclass construct worthwhile?
* How should passing primitive types (that do not care about being referenced) as ref:ed parameters be handled?
* How to handle heap allocated values? Box type with reference count?
* Fixed-size stack allocated arrays would be useful (also as members of structs)
* Look over how many times the function 'annotateOne' in Infer.hs actually needs to be applied to a form

## Code generation
* LLVM backend
* Emit #LINE macros in the generated C code

## Tooling
* Proper error handling when defining invalid struct types (right now it crashes)
* Stop evalutaion of forms after errors to avoid "Trying to refer to undefined symbol" error
* Built in REPL history (without using rlwrap)
* Preserve whitespace to allow saving forms back to disk
* Refactorings at the REPL
* Hide instances of templates/generic functions when printing the environment (by default)
* Warnings about giving away values should be compiler errors and not Haskell trace:s
* Somehow make it possible to enter ":t foo" at the REPL (can't be done now because each atom is evaluated separately)
* Rename type variables from t0, t1, t2 to a, b, c, etc.