# Function: movePlayer()
a) Concept implemented
Topic: Custom Functions & Error Checking / Restrictions
Code snippet:

void movePlayer() {
  if (keyPressed) {
    if (keyCode == LEFT) player_x -= speed;
    if (keyCode == RIGHT) player_x += speed;
    if (keyCode == UP) player_y -= speed;
    if (keyCode == DOWN) player_y += speed;
  }

  // Restrict player movement within the court boundaries
  player_x = constrain(player_x, 150, width - 150);
  player_y = constrain(player_y, height/2+20, height - 50);
}

b) Where and why it was used
## Where: Called inside playGame() every frame to handle player movement.

## Why: I need a dedicated function to move the player smoothly in response to key presses.

The constrain() function prevents the player from leaving the playable area, which is an error checking/restriction mechanism.

This keeps the gameplay fair and avoids glitches, like the player going off-screen.

c) Challenges and fixes

## Challenge: Initially, the player could move off the visible screen if the speed pushed them too far.

## Fix: Added constrain() to limit player_x and player_y to specific ranges.

These ranges correspond to the playable area: left/right boundaries and the bottom half of the screen for player movement.

# Function: collided()
a) Concept implemented

Topic: Custom Functions & Collision Detection (with restrictions)

Code snippet:

boolean collided(float x, float y) {
  return dist(ball_x, ball_y, x, y) < 60;
}

b) Where and why it was used

## Where: Called in playGame() to detect collisions between the ball and player/NPC.

## Why: Detecting collisions is important for gameplay, since hitting the ball increases the score and changes ball direction.

creating a collision detection in a custom function avoids repeating the same logic multiple times for player and NPC.

The < 60 value is a restriction that defines the collision radius; this prevents false positives when objects are far apart.

c) Challenges and fixes

## Challenge: Choosing an appropriate collision distance for accurate gameplay.

## Fix: I tested different distances and set it to 60 pixels, which matches the size of the player and NPC images.

This ensures collisions are detected only when the ball is actually near the player/NPC, not when it is too far.
