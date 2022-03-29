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

list of auras aand meaning
```
Aura         Meaning                        Example of Literal Syntax
-------------------------------------------------------------------------
@d           date
  @da        absolute date                  ~2018.5.14..22.31.46..1435
  @dr        relative date (ie, timespan)   ~h5.m30.s12
@n           nil                            ~
@p           phonemic base (urbit name)     ~sorreg-namtyv
@r           IEEE floating-point
  @rd        double precision  (64 bits)    .~6.02214085774e23
  @rh        half precision (16 bits)       .~~3.14
  @rq        quad precision (128 bits)      .~~~6.02214085774e23
  @rs        single precision (32 bits)     .6.022141e23
@s           signed integer, sign bit low
  @sb        signed binary                  --0b11.1000
  @sd        signed decimal                 --1.000.056
  @sv        signed base32                  -0v1df64.49beg
  @sw        signed base64                  --0wbnC.8haTg
  @sx        signed hexadecimal             -0x5f5.e138
@t           UTF-8 text (cord)              'howdy'
  @ta        ASCII text (knot)              ~.howdy
    @tas     ASCII text symbol (term)       %howdy
@u              unsigned integer
  @ub           unsigned binary             0b11.1000
  @ud           unsigned decimal            1.000.056
  @uv           unsigned base32             0v1df64.49beg
  @uw           unsigned base64             0wbnC.8haTg
  @ux           unsigned hexadecimal        0x5f5.e138
```

cells [head tail]
```
> [32 320]
[32 320]
```

`[6 [62 620]]` and `[6 62 620]` are considered equivalent in Hoon.

A cell must be a pair