Learning Log Entry 3 – Repetition Structures (Loops)
a) What concept did you implement?

Concept: Repetition Structures
The concept I implemented is a repetition structure using a for loop.
I used a for loop to repeatedly draw heart images that represent the player’s remaining lives during gameplay.

code snippet:
for (int i = 0; i < lives; i++) {
  image(heart1, 20 + i * 55, 30);
}

b) Where did you use it, and why did you implement it that way?

I used this for loop inside the playGame() function. Its purpose is to visually display the number of lives the player has left by drawing one heart for each life.
This approach was chosen because:
- The number of lives changes dynamically during the game
- A for loop allows the program to repeat the same drawing action without duplicating code
- The loop automatically updates the display when lives are lost, making the code more efficient and flexible
By using the loop counter (i) to offset the x‑position of each heart, the hearts are evenly spaced and easy to read. This is much cleaner than using multiple if statements for each possible number of lives.

c) What challenges did you encounter, and how did you fix them?

One challenge was ensuring the hearts did not overlap when multiple lives were displayed. Initially, all hearts appeared in the same position. 
I fixed this by multiplying the loop index (i) by a spacing value so each heart is drawn further to the right.
Another challenge was making sure the life display stayed accurate when the ball went off the screen.
I solved this by linking the loop condition directly to the lives variable, so whenever a life is lost, the loop automatically updates the number of hearts shown.
This helped keep the visual display consistent with the game logic.
