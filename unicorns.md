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

    .Picture .Warning h2 {
        color:#000000;
        }
    .Picture.AsAdvertised h2 {
        color:#FFFFFF;
        }
    #SeeMore h2 {
        font-size:100px
        }
    #SeeMore img {
        width:0.72em;
        height:0.72em;
        }
---

# Unicorns {#Cover}

![](pictures/cover.jpg)
<!-- photo by John Carey, fiftyfootshadows.net -->

## About me

* Florian Gilcher
* Twitter: [@argorak](http://github.com/argorak)
* Github: [skade](http://github.com/skade)
* Company: [http://asquera.de](http://asquera.de)

## Ruby community addict

* Conference chair of [eurucamp](http://eurucamp.org) and [JRubyConf.eu](http://jrubyconf.eu)
* Organizer of the [elasticsearch UG Berlin](www.meetup.com/ElasticSearch-UG-Berlin/)
* Co-Administrator of a german [Ruby community](http://rubyforen.de)
* [Padrino](http://padrinorb.com) core member

## Warning
{:.cover .Picture .Warning}

![](pictures/warning.jpg)

## Warning

* I love banging my head against the wall until the wall comes down
* ...this time, the wall (somewhat) won.

## A few questions

We never merge changes breaking our tests, right?

## A few questions

What about changes that break our documentation?

## The problem

Documentation that doesn't even compile is not unusual.

## What should documentation provide?

* An overview of the topic at hand
* Insight into topics, not components
* Applications of the described knowledge

## Beginning
{:.cover .Picture .AsAdvertised}

![](pictures/as_advertised.jpg)

## Evolution
{:.cover .Picture .AsDelivered}

![](pictures/as_delivered.jpg)

## The big question

How do we test documentation?

## The beasts

* Broken code, be it through sloppyness or code changes
* Deprecations
* Superceded approaches
* Documentation decays much faster than code

## Third parties
{:.cover #ThirdParties}

![](pictures/third_parties.jpg)

## Third parties

If you use downstream libraries and document interactions with them, you have to check all that **for those libraries, too**.

## Solutions

## Sidestep the problem

Don't include code in your documentation.

* Only high-level documentation of concepts
* Code goes to examples

## Issues

* Makes imagining what we're talking about hard
* Copy & paste is obviously not possible
* Beginner-unfriendly

## Reap the low-hanging fruit

* Write examples, test them, link to them
  - with hard settings for deprecations and warnings.
  - if possible, make the compiler fail on such things.
* Include them as a mandatory part into your integration tests.

## Work out documentation formats

* Work our documentation formats that naturally seperate prose and code.

## Example: Service Profiles

{:.cover .ServiceProfiles}

![](pictures/service_profiles.png)

## Example: Service Profiles

* All high-level descripts get a card
* Technical things (like "health check") are really dry.

## Better have some tools
{:.cover .Picture}

![](pictures/welder.jpg)

## Gherkin/Cucumber


    Feature: output_hello_world

      We can output strings "hello world" using the puts
      function.

      Scenario: Use puts to output "hello world".
        Given a file named "puts.rb" with:
          """ruby
            puts "hello world"
          """

## Gherkin/Cucumber

This write a Ruby file, evaluates it and tests your assumptions.
It uses Gherkins description features.

## Gherkin/Cucumber

![Relishapp](pictures/relishapp.png)

## Gherkin/Cucumber

* Works very well for small examples
* Has very special display needs
* Very formalized language that gets boring
* Interleaving context is possible, if tedious

## Doctest

Python ships a mixture of method docs and runnable code: [doctest](http://docs.python.org/2/library/doctest.html)

    def factorial(n):
        """Return the factorial of n, an exact integer >= 0.

        >>> [factorial(n) for n in range(6)]
        [1, 1, 2, 6, 24, 120]

## Doctest

* Very nice if arguments are simple
* If elaborate setup is needed, two dangers are there
  - implicit setup
  - noisy setup
* Not for larger texts with code examples

## Literate programming

Literate programming interleaves text and code. It it's purest style, code has to marked instead of comments.

## Literate programming

count.lhs

    Count Count wants to count words today.
    For that reason, he asks the user to provide some.
    > main = interact wordCount
    >    where wordCount input = show ( length input ) ++ "\n"

## Literate programming

Tools comments for text:

* [Docco, Rocco, Shocco, Pycco, Gocco, Locco, Nocco](http://jashkenas.github.io/docco/)
* ...for JavaScript, Ruby, Shell, Python, Go, Lua, .Net
* ...fragmentation much?

## Literate programming

This _great_ for one-file examples with long text. Also a natural way to attach text to tests.

## Literate programming

[Code is not literature](http://www.gigamonkeys.com/code-reading/).

An easy to understand text works from top to bottom. This is not true for code.

Boilerplate really kills your reading flow.

## Multiple representations

Use selenium steps both as visual documentation and for testing.

![Walkhub](pictures/walkhub.png)

Implemented by [walkhub](http://walkhub.net).

## Multiple representations

* Works well for interfaces
* The automation fakes interaction anyways
* Not quite the thing for a book ;)

## Reverse 

## Photo credits

All pictures by [@dariocravero](https://twitter.com/dariocravero) and myself.