# Connect Four

## Background

This project is being built according to [specifications](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/ruby-programming/lessons/connect-four) from [The Odin Project](https://www.theodinproject.com/)'s
[Ruby Programming](https://www.theodinproject.com/paths/full-stack-ruby-on-rails/courses/ruby-programming) course.

## Objectives

Using Test-Driven Development practices, build a Ruby command-line version of
the board game Connect Four.

* Select a required piece of functionality.
* Write a specification/test that fails.
* Implement only enough functionality to make the test pass.
* Refactor the code, if possible to do so with a passing test.

## Notes

### Connect Four ([wikipedia](https://en.wikipedia.org/wiki/Connect_Four))
* Two players
  * Red tokens
  * Yellow tokens
* Board
  * Seven columns
  * Six rows
  * Columns are filled from the bottom-up --> players can select columns, but rows are predetermined.
* Solved game --> can always be won with the right moves.
* Rules
  * Players win by forming a diagonal, vertical, or horizontal connection of four of their tokens.
  * The game is a draw if the board fills up before either player can connect four tokens.
  * No initial first player --> random? --> loser goes first in next game?

### Rails Conf 2013 The Magic Tricks of Testing by Sandi Metz ([youtube](https://www.youtube.com/watch?v=URSWYvyc42M))
* Think of the Object Under Test as a space capsule
  * Focus on the public interface
* Queries
  * Return information/calculation with no change in state
* Commands
   * Change state but return nothing
* Hybrid
  * E.g., popping Queues --> return item & change state of queue
* The Grid
  * Incoming
    * Queries --> make assertions about what they return
      * Test the interface, not the implementation.
    * Command --> make assertions about direct (responsibility of the last class involved) 
                  public side effects.
  * Sent to Self --> implementation detail --> by default don't test
  * Outgoing
    * Queries --> Ignore. Receiver is responsible for incoming query.
    * Commands --> integration test --> expect that the command is sent
      * Create a mock of the receiver
      * Depend on the interface of the API
      * Must update the mock if the API changes, otherwise tests will pass but app will be broken.

### Unicode Characters

* Unicode Character “🟡” (U+1F7E1)
* Unicode Character “🔴” (U+1F534)
* https://en.wikipedia.org/wiki/Box-drawing_character

### Ruby Sleep (for animation)
* https://stackoverflow.com/questions/1329967/tell-ruby-program-to-wait-some-amount-of-time
* https://devdocs.io/ruby~3/kernel#method-i-sleep

