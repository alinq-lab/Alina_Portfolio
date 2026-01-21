# Learning Log Entry 1 – Variables & Data Tracking
## a) What concept did you implement?
 Variables & Data Tracking
In my game, I used multiple types of variables to track game state, player movement, scoring, lives, and level progression. These included int, float, boolean, String, and PImage variables.

Code snippet:
float player_x, player_y;
float ball_x, ball_y;
float speed = 6;
float npcSpeed = 3;

int lives = 3;
int score = 0;
int level = 1;
int maxLevel = 7;

boolean showLevelUp = false;

String gameState = "START"; 

## b) Where did you use it, and why did you implement it that way?

I used variables throughout the entire program to store and update important game data in real time. Position variables (player_x, player_y, ball_x, ball_y) track movement and allow the game to update object positions every frame.
Speed variables (speed, npcSpeed, ballSpeedX, ballSpeedY) allow the difficulty to increase as the player levels up. Integer variables (score, lives, level) track progress and determine win/lose conditions.
Boolean variables (showLevelUp) control whether certain messages or effects appear on screen. String variable (gameState) controls which screen is currently displayed (start menu, customization, gameplay, win, or lose).
Using different variable types made the program more efficient and readable. For example, float values allow smooth movement, while int values are better for whole-number data like score and lives. The gameState variable allowed me to manage screen transitions without duplicating more code.

## c) What challenges did you encounter, and how did you fix them?

Managing an ongoing game state over several play sessions was one of the challenges I faced.
Even after the game entered a restart state, the values of many important variables, including score, lives, speed values, and level progression, continued to update because they were declared globally.
Unintentional carryover effects resulted from this, like higher difficulty or inaccurate scoring when beginning a new game. 
I created  a resetGame() function that centralizes all variable reinitialization in order to fix this. 
I made sure that every new session starts in a clear and consistent state by calling resetPositions() and explicitly resetting gameplay variables. 
This reduced logical errors, better organized the code, and made the restart process more dependable and manageable.
