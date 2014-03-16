---

layout: ribbon

style: |

    #Cover h2 {
        margin:30px 0 0;
        color:#FFF;
        text-align:center;
        font-size:70px;
        }
    #Cover p {
        margin:10px 0 0;
        text-align:center;
        color:#FFF;
        font-style:italic;
        font-size:20px;
        }
        #Cover p a {
            color:#FFF;
            }
    #Picture h2 {
        color:#FFF;
        }
    #SeeMore h2 {
        font-size:100px
        }
    #SeeMore img {
        width:0.72em;
        height:0.72em;
        }
    .noHead  h2 {
        display: inline-block;
        visibility: hidden;
    }
    #dont-join-shitstorms h2 {
        color: red;
    }
    #think-before-you-tweet h2 {
        color: red;
    }
---

# Much more `fn` - Rust
{:.cover .Picture .FullMetal .noHead}

![](pictures/cover.jpg)

## Much more `fn` - Rust

* Systems programming language
* ... by Mozilla
* ... Imperative with functional parts
* ... low-level
* ... `null`-free, typed and safe
* ... strictly better than Java or Clojure (by default)

## Braces, as Richie indented

![](pictures/rust/Dennis_MacAlistair_Ritchie.jpg)

## **{Rust is a curly-brace language}**

## Structs

Rust has no classes, it is based on structs.

    pub struct tb_cell {
        character: u32,
        foreground: u16,
        background: u16,
    }

## Implementations

But implementations on top of structs.

    impl tb_cell {
      fn new(character, foreground, background) -> tb_cell {
        tb_cell { character: character,
                  foreground: foreground,
                  background: background}
      }
    }


## Mutability as a first class concept

Defining functions over a struct works the python way.

      fn set_foreground(&self, color) {
        self.foreground = foreground
      }

`BANG!`

## Mutability as a first class concept

      fn set_foreground(&mut self, color) {
        self.foreground = foreground
      }

## Mutability

* allows for switching between immutable and mutable styles
* good for concurrent code
  - unsurprisingly, Rust ships with good concurrency primitives
* still allows for predictable low-level operations

## &~*(@) - Ownership

What looks a lot like swearing here are pointers expression your relationship to data.

  * `~` I own the data
  * `&` But I borrow it away to someone to work on
  * `@` This code was written when Rust still had garbage collection
  * `*` What would a C-like language be without dereferencing?

## Traits

Additional functionality can be implemented per module using Traits.

    impl ToStr for tb_cell {
      fn to_str(&self) -> ~str {
        ~"We sold this implementation for advertisement:
        Hire http://asquera.de"
      }
    }

## DCI

We're on `wroc_love.dci` here - this is incredible for DCI. Local implementations
over raw data is a first class concept.

## Painless interfacing with C

The struct layout is C-ABI compatible. An FFI definition.

    extern {
      pub fn tb_put_cell(x: c_int, y: c_int, cell: *tb_cell);
    }

Optionally without runtime, making writing shared libraries in Rust possible.

## Built in tests

    #[cfg(test)]
    mod test {
      #[test]
      fn test_eljojo_is_no_mutant() {
        assert_eq!(Eljojo.new().mutant(), false);
      }
    }

## Haskell - the good parts

    match jar {
      Some(sweets) => ~"\o/",
      None => ~":("
    }

* Option and Result types
* destructuring


## A word of warning

Rust is still in construction. Run `master`, keep it that way until 1.0.

...Expect breaking changes every week. But easy to follow.

...Currently for mind-blowing only.

## That's `fn`

When can you ever see a language in construction so openly?

...commit access is really easy to get with quite some low-hanging fruits.

## Great, vibrant community already

* Strong, vibrant community with strict rules
* Enforces it strongly
* -> Almost no trolls, strong, on topic discussions

## Links

* http://rustlang.org
* http://github.com/mozilla/rust
* http://www.rustforrubyists.com/ by Steve Klabnik
