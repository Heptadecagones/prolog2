# Notes on documentation

#[Source I](https://courses.cs.washington.edu/courses/cse573/04au/Project/mini1/RUSSIA/Final_Paper.pdf)
I. Othello heuristic components:
1. Linear combination of heuristics
Values from -100 to 100 (fine-tune to play an optimal game)

##Coin Parity
Counts the number of coins for the player, greedily.

```
Coin parity = 100 * (MaxPC - MinPC) / (MaxPC + MinPC)
```

##Mobility
i. Actual mobility
Number of legal moves

```
if(MaxPAM + MinPAM != 0)
    ActualMobilityHeuristicValue = 100*(MaxPAM - MinPAM) / (MaxPAM - MinPAM)
else
    ActualMobilityHeuristicValue = 0
```


ii. Potential mobility
Moves that could be legal next move
Calculated in an identical fashion

##Corners Captured
Corners have weight based on whether they are *captured*, *potentially* or *unlikely* captured

```if(MaxPCV + MinPCV != 0)
    CornerHeuristicValue = 100*(MaxPCHV - MinPCHV) / (MaxPCHV + MinPCHV)
else
    CornerHeuristicValue = 0
```

##Stability
Three weighted categories: stable, semi-stable and unstable.
Stable (1): Cannot be flanked from the given state
Semi-stable (0): Could potentially be flanked in the future
Unstable (-1): Can be flanked right away

```
if(MaxPSV + MinPSV != 0)
    StabilityHeuristicValue = 100*(MaxPSV - MinPSV) / (MaxPSV + MinPSV)
else
    StabilityHeuristicValue = 0
```


2. Statically assigned weight to squares to calculate value

 4 -3  2  2  2  2 -3  4
-3 -4 -1 -1 -1 -1 -4 -3
 2 -1  1  0  0  1 -1  2
 2 -1  0  1  1  0 -1  2
 2 -1  0  1  1  0 -1  2
 2 -1  1  0  0  1 -1  2
-3 -4 -1 -1 -1 -1 -4 -3
 4 -3  2  2  2  2 -3  4

2.1 Dynamically assigned weights
Stability & Mobility have high weight at the start of a game
Corners and stability gain more weight as the game progresses

II. Search strategies
Min-max
Alpha-beta
Alpha-beta with iterative deepening

#[Source 2](https://www.ffothello.org/informatique/algorithmes/)

Table de transpositions pour garder en mémoire ce qu'on a déjà joué de rentable
Recherche sélective avec pré-élémination de branches peu prometteuses



# Forked description
# Prolog-Othello-Game 
![Othello-game](https://previews.123rf.com/images/norgal/norgal1310/norgal131000056/22617956-closeup-discs-on-green-reversi-board-othello-.jpg)


## Description 
[Othello Game](https://en.wikipedia.org/wiki/Reversi#Othello) Implemented with [Alpha-Beta Algorithm](https://en.wikipedia.org/wiki/Alpha%E2%80%93beta_pruning) in [SWI-Prolog's](https://www.swi-prolog.org/) Logic Programming Language. 
The AI engine alpha-beta algorithm is based on heuristics such as capturing cornes & number of overall captured pieces. 

![SWI-Prolog logo](https://www.swi-prolog.org/icons/swipl.png)


## Features
### Game Mode 
* Play Against Computer (Human vs AI) :technologist:
* Watch Computer vs Computer (AI vs AI) :desktop_computer: :computer:

### Difficulty level  :chess_pawn:
This is relevant of course only when playing against the computer (and not when watching computer against computer). 
The difficulty level is influenced by means such as the depth level of the search algorithm & the heuristics taken into account. 

## Documentation 
See [Documention](Documentation.pdf) for ruther details. 


## Sample Screenshots 
![demo screenshots](app-screenshots.gif)
