Hoon is a "subject-oriented" programming language

Hoon is a purely functional systems language

`subject` is a piece of data that represents the environment, or the context, of an expression.

This is a "noun"
```
> 17
17
```

add is a function
```
> (add 2 2)
4
```

naked generators are gates (take input to produce output)

save the gate in a `.hoon` file, and add it to the `/gen` dir of a desk on your ship.

mount a desk to the Unix filesystem

easy to use `%base` desk with fake ship `/urbit -F zod`

to mount run `|mount %base` in dojo (termial)