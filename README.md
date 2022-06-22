# Playing Cards

1. Fork this repo
2. Clone your fork to your local machine
3. cd playing_cards
4. Add my repo as an upstream (`git remote add upstream git@github.com:jasonnoble/playing_cards.git`)
5. `bundle`

Open the editor of your choice.

## Setup

You should work on a topic branch. Make sure you are on the main branch:

```
$ git branch
* main
$
```

Create a topic branch:

```
$ git checkout -b attempt_1
Switched to a new branch 'attempt_1'
$ git branch
* attempt_1
  main
$
```

## Overall Goals

1. Get comfortable with RSpec TDD process
2. Continue practicing Ruby
3. Get comfortable with staging and committing changes via `git`
4. You should commit at least at the end of each iteration. The more you commit, the better.

## Running Guard

This repo has a number of automated tasks handled by the Guard gem. After creating your topic branch, run the following:

```
$ guard --clear
```

This does a number of things:

* Runs `bundle` if you've changed your Gemfile
* Runs Rubocop to analyze your Ruby code for linting issues
* Runs RSpec

Leave this command running in your terminal. Whenever you change any code, guard will notice you saved changes and re-run the steps above.

## Iteration 1

A `PlayingCard` represents a playing card

Attributes:

* suit ('diamond', 'heart', 'spade', 'club')
* value ('1','2','3','4','5','6','7','8','9','J','Q','K','A')

Methods:

* suit (Returns the suit of the card)
* value (Returns the value of the card)

Steps:
1. Create a spec/playing_card_spec.rb file
   1. Require the spec_helper
   2. Require './lib/playing_card'
   3. RSpec.describe PlayingCard

Verify the following via your spec file:

* Creating a card requires you pass in a `suit` and `value`
* You can ask a card its suit
* You can ask a card its value

Iteration Rubric:

* Rubocop returns no errors
* All tests are green
* Code coverage shows 100% test coverage

## Iteration 2

A `Deck` represents a deck of playing cards

Attributes:

* None

Methods:

* initialize
  * Calling Deck.new should add the following cards to the deck's array of cards
    * 1 - 9, J, Q, K, A of Hearts
    * 1 - 9, J, Q, K, A of Diamonds
    * 1 - 9, J, Q, K, A of Clubs
    * 1 - 9, J, Q, K, A of Spades
* shuffle
  * Calling `shuffle` on a deck of cards changes the cards to be in a random order
* deal
  * Removes a card from the deck and returns that card

Iteration Rubric:

* Rubocop returns no errors
* All tests are green
* Code coverage shows 100% test coverage

## Iteration 3

A `Player` represents a player in a card game.

Attributes:

* Name
* won_cards
  * The cards that the player has won

Methods:

* hand
  * The cards the player has in their hand
* deal(card)
  * Adds the card to the player's hand
* play(card)
  * The card passed in is the high card (may be nil)
  * Plays a card from the player's hand
* win(cards)
   * Adds the cards to the player's `won_cards`
   
Iteration Rubric:

* Rubocop returns no errors
* All tests are green
* Code coverage shows 100% test coverage

## Iteration 4

A `Game` represents a card game

Attributes:

* deck
  * A deck of shuffled cards

Methods:

* add_player(player)
  * Adds a player to the game
* deal
  * Using the deck, deal a card, then pass it to the next player
  * Each player should end up with 13 cards
* play_round
  * asks each player for a card
  * Determines the winner (highest value == win)
  * passes the cards to the winner

Iteration Rubric:

* Rubocop returns no errors
* All tests are green
* Code coverage shows 100% test coverage

## Compare your results

After you've committed all your results via Git, you can check your work by running the following:

```
$ git diff upstream/complete
```

## Do it again!

```
git checkout main
git checkout -b attempt_2
```
