Arrays & Data Structures
a) Concept Implemented
Topic: Arrays & Array Manipulation (with file I/O)
This program uses arrays as its main data structure.
Arrays are used because they allow the program to store multiple related values under one variable name and access them using an index.
I implemented arrays to store multiple high scores in the game. The lines[] array temporarily holds data read from a file. 
The highScores[] array stores integer scores that the game uses to track top scores.
This demonstrates array usage, array indexing, and looping.

code snippet:

String[] lines = loadStrings("highscores.txt");
for (int i = 0; i < maxHighScores; i++) {
  if (i < lines.length) highScores[i] = int(lines[i]);
  else highScores[i] = 0;
}

b) 
Arrays were used to:
- Store multiple high scores at once
- Keep scores ordered from highest to lowest
- Load and save scores using a text file
- Display scores with a ranking number

My code is used in the loadHighScores() function and throughout the high score system (updateHighScores(), saveHighScores(), showHighScores()).
Why implemented this way:
- High scores need to be saved to a file and sortable.
Using arrays allows me to:
- Easily store multiple scores.
- Access any score via its index (e.g., highScores[0] is the highest).
- Loop through scores to insert, shift, and update them in the leaderboard.
- String[] lines is used because files store text. Reading it into a string array lets me convert it to integers later

Purpose of the code:
Load high scores from a file.
Ensure the game can display, update, and save scores.
