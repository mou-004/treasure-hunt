🔺 THE CURSED CACHE 🔺
A pirate-themed, browser-based puzzle hunt where you explore abandoned rooms, solve randomly generated puzzles to collect clues, and crack the final riddles to find the legendary treasure.

📖 Game Rules
Find the Puzzles: You are in a room filled with objects (bookshelves, pictures, chests, etc.). Click on objects to interact with them.

Traps & Clues: Not all objects contain puzzles. Some are "decoys" that just give you empty flavor text. The objects with actual puzzles will open a puzzle panel.

Solve to Collect: You must solve the puzzle before the timer runs out. If you solve it, you earn a Clue Word (e.g., GOLD, MAP, CHEST).

Lives (Integrity): You have 3 lives (4 in the final level). If you answer wrong or let the timer hit zero, you lose a life. Lose all lives, and it's Game Over.

The Level Final Riddle: Once you collect all the clues for that level, the final chest in the 3rd room unlocks. You must use the collected clues to solve the Level Final Riddle.

The True Final Riddle: Complete all 3 levels to unlock the True Final Riddle. The answers from Level 1, 2, and 3 become your final clues. Solve it to win the game!

🎮 How to Play
Navigate Rooms: Use the ◀ and ▶ arrows on the left and right sides of the game screen to move between the 3 rooms in each level.

Interact: Click or tap on the emoji objects (🗄️, 🖼️, 🧰, 💰, etc.) to see what's inside.

Input Answers: Type your answer in the text box and press SUBMIT or hit Enter.

Hint System: Each puzzle has one hint available if you get stuck. Click 💡 HINT inside the puzzle panel.

Watch the Clock: The colored bar at the top of the puzzle panel is a timer. It gets faster in later levels!

🧠 The Algorithm & How It Works
This game is built entirely in Vanilla JavaScript, HTML, and CSS. It relies on several core algorithms and procedural generation techniques:

1. Random Puzzle Generation (Procedural Generation)
Instead of hardcoding puzzles, the game uses factory functions (makeMathPuzzle, makeSequencePuzzle, etc.) to generate a new puzzle every time you play.

Math: Uses Math.random() to pick a random multiplier and base number, ensuring the answer is always a clean integer.

Scramble: Takes a hardcoded word, splits it into an array, uses the Fisher-Yates shuffle algorithm to randomize the letters, and joins them back together.

2. Random Object Placement (Shuffle & Assignment)
When a level loads, the game needs to hide the puzzles in random objects.

It takes the array of all available objects (CANDIDATE_SPOTS).

It uses the Fisher-Yates shuffle to randomize the order.

It slices the first N items (N = number of puzzles for that level) and assigns them as type: 'puzzle'.

The rest are assigned as type: 'decoy'.

3. Answer Normalization (String Matching)
Players type messy things (extra spaces, capital letters, punctuation). To ensure fair checking, the game uses a normalize() function:

Converts the string to lowercase.

Uses a Regular Expression (/[^a-z0-9]/g) to strip out any character that is not a letter or a number.

This guarantees " Gold! " and "gold" are treated as the exact same answer.

4. Timer Algorithm
The timer uses setInterval() firing every 100ms (0.1 seconds). It calculates the remaining percentage and updates the CSS width of the timer bar. If the timer hits 0, it triggers the timeUp() function, deducts a life, and resets the timer with 10 fewer seconds.

📝 Cheat Sheet: Q&A Answers
Because the puzzles are randomized, the exact numbers/words change. Here is the master list of all possible questions and how to solve them.

🔢 Math Puzzles
The game will give you two numbers. Just do the math.

Pirate divides gold: Total Coins ÷ Coins per Sailor = Answer

Ship rations: Total Barrels ÷ Drinks per day = Answer

Map folding: Total Width ÷ Sections = Answer

Chest locks: Locks × Digits per code = Answer

Vault piles: Total Bars ÷ Piles = Answer

🧠 Sequence Puzzles
2, 4, 8, 16, ? → 32 (Multiply by 2)

3, 6, 12, 24, ? → 48 (Multiply by 2)

1, 1, 2, 3, 5, 8, ? → 13 (Add previous two)

5, 10, 15, 20, ? → 25 (Add 5)

2, 6, 18, 54, ? → 162 (Multiply by 3)

1, 4, 9, 16, ? → 25 (Square numbers: 1x1, 2x2, 3x3...)

🔤 Scramble Puzzles
Unscramble the letters provided in the game.

R A R O T P → parrot

R A P I T E → pirate

D N A L S I → island

S A P S M O C → compass

E T A R U S E R → treasure

N I T A P A C → captain

R O H C N A → anchor

N O N A C → cannon

D R O W S → sword

T S E H C → chest

🧠 Pattern Puzzles
N, E, S, W, N, E, S, ? → w (Compass: North, East, South, West)

N, NE, E, SE, S, SW, W, ? → nw (8 points: North-West)

A, B, C, A, B, C, A, ? → B

1, 2, 3, 1, 2, 3, 1, ? → 2

A, C, E, G, I, K, M, ? → O (Skip a letter)

Z, X, V, T, R, P, N, ? → L (Skip a letter backwards)

🧠 Logic Puzzles
If A=1, B=2, C=3...

Letter 20 → t

Letter 21 → u

Letter 22 → v

Letter 23 → w

Letter 24 → x

Letter 25 → y

Letter 26 → z

🗝️ Final Riddles (Type exactly these)
Level 1 Final: "I am what every pirate hunts..." → gold

Level 2 Final: "I hold gold. I am made of wood and iron..." → chest

Level 3 Final: "I am surrounded by water. I hide treasure..." → island

TRUE FINAL RIDDLE: "One is yellow... One holds the first... One is surrounded by water..." → treasure
