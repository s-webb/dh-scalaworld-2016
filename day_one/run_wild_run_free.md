### Run Wild, Run Free! - Raul Raja

For me, this talk contained the most practical and immediately useful content presented at the conference.

Raul presented solutions to some of the most common problems he has encountered whilst providing consultancy to around
10 teams of scala developers since 2013. All of which seemed unfortunately familiar to me, to some extent. Here's one
example:

```scala
def getCountryCode(personId : String) = {
  findPerson(personId) map { maybePerson =>
    maybePerson map { person =>
      person.address map { address =>
        findCountry(address.addressId) map { maybeCountry =>
          maybeCountry map { country =>
            country.code
          }
        }
      }  
    }
  }
}
```

Design patterns, relatively simple ones, exist that can be used to avoid creating deeply nested, hard to follow code 
like this. The problem in Raul's opinion is that newcomers to scala (often coming from an OO background) just aren't 
aware of them.

The following three strategies were presented, in context of the problems that they solve, with code examples:

- Algebraic design and sealed hierarchies for safer exceptions control (using the Xor datatype, monad transformers)
- Abstract over return types for code reuse (using higher-kinded types in function signatures)
- Abstract over implementations to increase flexibility and composition (using free monads)

**Repo** - https://github.com/47deg/run-wild-run-free

**Slides (PDF)** - https://github.com/47deg/run-wild-run-free/blob/master/presentation.pdf

**Slides** - https://speakerdeck.com/raulraja/run-wild-run-free

