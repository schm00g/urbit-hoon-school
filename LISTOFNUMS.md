hoon prog generator

in hoon expressions are comprised of runes

RUNES are keywords

```
|=  end=@                                               ::  1
=/  count=@  1                                          ::  2
|-                                                      ::  3
^-  (list @)                                            ::  4
?:  =(end count)                                        ::  5
  ~                                                     ::  6
:-  count                                               ::  7
$(count (add 1 count))                                  ::  8
```

gate `|=` is a function 

`@` for short. An atom is a natural number

HOW TO RUN A HOON PROGRAM ON URBIT:
* in `base/gen` directory of your ship create `.hoon` file
* `test.hoon` for example
* add logic etc.
* save and commit your changes
* how? by running `|commit %base` in >dojo
* run our commited file by typing into the >dojo
* `+test 5` where number is argument (if present)