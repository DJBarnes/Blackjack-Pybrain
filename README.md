Blackjack-Pybrain
=================

Authors
-------
Carl Oldham
David Barnes

What is it?
-----------
Blackjack-Pybrain is a small application written for the explicit purpose of demonstrating a very simple Reinforcement Learning Neural Network.

Which Version to Run?
---------------------
There are two versions of the application provided in this repository. Both versions create reinforcement learning agents that play blackjack against a dealer.

blackjack.py will create a single RL learner who will play against the dealer.

blackjackMulti.py will create five RL learners who play against the dealer. Each player has slightly different attributes which makes them learn and perform slightly different from one another.

After all of the games have been played, a summarization of the results of the games played is output, as well as the results of each players action-value table. Using matplotlib, a graph is created to display the results of the learned action-value tables.

Rules of the Game
-----------------
This is a very simple RL example which omits many of the traditional rules of blackjack.

The deck class is a key/value array, and dealing does not occur in the traditional dealing method, where each player receives their first card, and then next each receives their second card. Instead a card is drawn from random out of the array, one after another until the RL agent or dealer has a full hand. It then begins dealing to the next player.

The dealer plays his hand before the RL agents play theirs. This was done in an effort to make it easier to know whether a RL agent has won or lost the game as soon as they have finished playing their hand.

Card values are 2 through 11. The ace value is 11, and does not have the ability to count as both 1 and 11. Because of this, there are a few notable problems that occur.

It is possible for the dealer and the RL agents to be dealt a hand of 22, making the players bust immediately.

The dealer will always stand once their hand value reaches or exceeds 17. If the dealer has a ace and a 6, they can not count their hand as 7. It will always be 17.

Reward System for Agents
------------------------
Player Busts: -2  <br />
Player Losses: -1 <br />
Player Ties: 0    <br />
Player Wins: 2    <br />
Dealer Busted: 1  <br />
