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
---

# Unicorns {#Cover}

![](pictures/cover.jpg)
<!-- photo by John Carey, fiftyfootshadows.net -->

## About me

* Florian Gilcher
* Twitter: @argorak
* Github: Skade
* [http://asquera.de](http://asquera.de)

## The disclaimer

* I love banging my head against a wall until the wall comes down
* ...this time, the wall won.

## The disclaimer

This talk is more a problem statement than about anything I ever implemented.

## The problem

We never merge breaking changes into master, right?

## The problem

What about changes that break our documentation?

## Padrino

[Padrino](http://padrinorb.com) is a full-stack framework written in Ruby, based on Sinatra and aimed at giving the user full control of the stack.

## 1:n Documentation

That means that more often then not, our documentation code breaks because of third party libraries, not because of ourselves.

## 1:n Documentation

Mostly, it's actual code breakage, no semantic breakage.

## The big question

How do we test documentation?

## Sidestep the problem

Don't include code in your documentation.

## Gherkin/Cucumber

~~~cucumber
Feature: Search courses
  Courses should be searchable by topic

  Scenario: Search by topic
    Given there are 240 courses which do not have the topic "biology"
    And there are 2 courses A001, B205 that each have "biology" as one of the topics
    When I search for "biology"
    Then I should see the following courses:
      | Course code |
      | A001        |
      | B205        |
~~~



## Tools
{:.cover #Picture}

![](pictures/welder.jpg)
<!-- photo by John Carey, fiftyfootshadows.net -->
