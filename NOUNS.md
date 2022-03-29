Atoms are unsigned integers (natural numbers)

dojo will take `123` but will stop you from typing `1234`

instead you should type `1.234`

hoon likes URL-safe notation. y tho?

dojo parses the command line as you type!

auras tell us what type of information an atom is

examples of literals:
```
> 0b1001
0b1001

> 0b1001.1101
0b1001.1101

> 0x9d
0x9d

> 0xdead.beef
0xdead.beef

> --9
--9

> -79
-79

> --0b1001
--0b1001

> -0x9d
-0x9d
```

To see their values in the default atom notation, you can tell Hoon to throw away the aura information; by using '@'
```
> `@`0b1001
9

> `@`0b1001.1101
157

> `@`0x9d
157

> `@`0xdead.beef
3.735.928.559

> `@`--9
18

> `@`-79
157

> `@`--0b1001
18

> `@`-0x9d
313
```

`@` syntax is used to "cast" a value to a raw atom  i.e., an atom without an aura

atoms can be used as strings in Hoon
```
> 'Howdy!'
'Howdy!'

> `@`'Howdy!'
36.805.260.308.296

> 'Hello world!'
'Hello world!'

> `@`'Hello world!'
10.334.410.032.606.748.633.331.426
```