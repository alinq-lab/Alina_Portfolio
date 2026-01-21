# Arrays & Data Structure Log

a) Concept implemented:

## Topic: Arrays (data structure)

Relevant code snippet:

int maxHighScores = 5;        // Maximum number of high scores to store
int[] highScores = new int[maxHighScores]; // Array to store the scores

// Load scores from file
void loadHighScores() {
  String[] lines = loadStrings("highscores.txt");
  for (int i = 0; i < maxHighScores; i++) {
    if (i < lines.length) highScores[i] = int(lines[i]);
    else highScores[i] = 0;
  }
}

// Update array with new score
void updateHighScores() {
  highScores[maxHighScores - 1] = score; // add the new score at the end
  Arrays.sort(highScores);               // sort array in ascending order
  saveHighScores();                      // save updated scores to file
}


b) Where and why it was used:

## Where:

The array highScores is used whenever a player wins, loses, or finishes a game to keep track of the top 5 scores.

The loadHighScores() function is called in setup() so that previous scores are loaded when the game starts.

The updateHighScores() function is called when the game ends (win or lose) to check if the player’s score should be saved.

## Why implemented this way:

An array is perfect because we know the number of high scores we want to store (maxHighScores = 5).

Arrays allow easy access by index (for adding new scores, sorting, and displaying).

Sorting ensures that we can always keep track of the lowest and highest scores easily.

c) Challenges and how they were fixed:

## Challenge: Handling cases when the high scores file is empty or has fewer than 5 scores.

## Solution: Added a check in loadHighScores():

if (i < lines.length) highScores[i] = int(lines[i]);
else highScores[i] = 0;


This fills empty spots with 0, preventing errors.

## Challenge: Inserting a new score while keeping the top scores updated.

## Solution: Placed the new score at the end of the array and used Arrays.sort() to automatically order the array. This removed the need for complex loops or manual shifting.

## Challenge: Displaying scores in order on the screen.

## Solution: Using a simple for-loop:

for (int i = 0; i < maxHighScores; i++) {
  text((i+1) + ". " + highScores[i], width/2, 100 + i*30);
}
