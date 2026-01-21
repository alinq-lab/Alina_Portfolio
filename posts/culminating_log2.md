# Learning Log Entry 2 – Selection Structures

a) What concept did you implement?

Concept: Selection Structures (if, else if, else)

The selection structures I used are to make decisions based on game conditions, player input, and current game state. 

Code snippet:
if (gameState.equals("START")) startScreen();
else if (gameState.equals("CUSTOMIZE")) customizeScreen();
else if (gameState.equals("PLAY")) playGame();
else if (gameState.equals("WIN")) winScreen();
else if (gameState.equals("LOSE")) loseScreen();

## b) Where did you use it, and why did you implement it that way?

Selection structures control:

- Screen navigation
- Collision detection
- Life loss
- Level progression
- Win and lose conditions
Using a gameState decision structure in draw() keeps the program organized and prevented multiple screens from rendering at the same time. 
Conditional checks are also used during gameplay to detect collisions, determine when lives should decrease, and decide when the game ends

## c) What challenges did you encounter, and how did you fix them?

A challenge was ensuring that only one game state ran at a time. Early versions caused overlapping screens.
I fixed this by standardizing all screen transitions through the gameState variable and checking it consistently before making any visuals.
