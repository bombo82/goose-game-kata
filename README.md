# The Goose Game Kata
Goose game is a game where two or more players move pieces around a track by rolling a die. The aim of the game is to reach square number sixty-three before any of the other players and avoid obstacles. ([wikipedia](https://en.wikipedia.org/wiki/Game_of_the_Goose))

This kata has been invented by [Matteo Vaccari](https://github.com/xpmatteo), you can find the original slides [here](https://www.slideshare.net/pierodibello/il-dilettevole-giuoco-delloca-coding-dojo).

This is a variation of the original Goose Game Kata I use for Clean Code Classes.

## General requirements
- You may use whatever programming language you prefer. Use something that you know well.
- You should deliver the sources of your application, with a short README that explains how to compile and run it.

**IMPORTANT:** Implement the requirements focusing on writing the best code you can produce.

## Features

### Add players
As a player, I want to add me to the game so that I can play.

- Add Player
   ```
   If there is no participant
   the user add player Pippo
   the system responds with a list of players containing "Pippo"
   the user add player Pluto
   the system responds with a list of players containing "Pippo, Pluto"
   ```

- Duplicated Player
   ```
   If there is already a participant Pippo
   the user add player Pippo
   the system informs that "Pippo already existing player"
   ```

### Move a player
As a player, I want to move the marker on the board to make the game progress

- Start
   ```
   If there are two participants Pippo and Pluto on space Start
   the user moves Pippo by 6 spaces
   the system informs that "Pippo moves from Start to 6"
   the user moves Pluto by 4 spaces
   the system informs that "Pluto moves from Start to 4"
   the user moves Pippo by 5 spaces
   the system informs that "Pippo moves from 6 to 11"
   ```

### Win
As a player, I win the game if I land on space "63"

- Victory
   ```
   If there is one participant Pippo on space 60
   the user moves Pippo by 3 spaces
   the system informs that "Pippo moves from 60 to 63. Pippo Wins!!"
   ```

- Winning with the exact dice shooting
   ```
   If there is one participant Pippo on space 60
   the user moves Pippo by 5 spaces
   the system informs that: "Pippo moves from 60 to 63. Pippo bounces! Pippo returns to 61"
   ```

### The game rolls the dice
As a player, I want the game rolls the dice for me to save effort

- Dice roll
   ```
   If there is one participant Pippo on space 4
   assuming that the dice get 1 and 2
   when the user moves Pippo
   the system informs that: "Pippo rolls 1, 2. Pippo moves from 4 to 7"
   ```

### Space "6" is "The Bridge"
As a player, when I get to the space "The Bridge", I jump to the space "12"

There are a picture of a bridge between space 6 and 12.

**Scenarios:**
- Get to "The Bridge"
   ```
   If there is one participant Pippo on space 4
   when the user moves Pippo by 2 spaces
   the system informs that "Pippo moves from 4 to The Bridge. Pippo jumps to 12"
   ```

### If you land on "The Goose", move again
As a player, when I get to a space with a picture of "The Goose", I move forward again by the sum of the two dice rolled before

The spaces 5, 9, 14, 18, 23, 27 have a picture of "The Goose"

**Scenarios:**
- Single Jump
   ```
   If there is one participant Pippo on space 3
   when the user moves Pippo by 2 spaces
   the system informs that "Pippo moves from 3 to 5, The Goose. Pippo moves again and goes to 7"
   ```

- Multiple Jump
   ```
   If there is one participant Pippo on space 10
   when the user moves Pippo by 4 spaces
   the system informs that "Pippo moves from 10 to 14, The Goose. Pippo moves again and goes to 18, The Goose. Pippo moves again and goes to 22"
   ```

### Prank (Optional Step)
As a player, when I land on a space occupied by another player, I send him to my previous position so that the game can be more entertaining.

**Scenarios:**
- Prank
   ```
   If there are two participants Pippo and Pluto respectively on spaces 15 and 17
   when the user moves Pippo by 2 spaces
   the system responds: "Pippo moves from 15 to 17. On 17 there is Pluto, who returns to 15"
   ```
