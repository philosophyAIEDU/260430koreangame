# Add Coloring Game and Alphabet Train Game

This plan outlines the addition of two new game modes to the existing Hangul learning application.

## User Review Required

> [!IMPORTANT]  
> Please review the proposed designs for the new games to ensure they match your vision before I begin coding.

## Open Questions

> [!WARNING]  
> **1. Coloring Game Mechanism:** "색깔을 선택해서 손으로 터치해서 그릴 수 있게" (Touch to draw with selected colors). Do you want a free-hand drawing experience where the user drags their finger to color inside the outlines, or a "flood fill" experience where tapping a region instantly fills it with the selected color? (Free-hand drawing is easier to implement for complex shapes, while flood-fill requires specific closed-path images).
> **2. Coloring Pictures:** I will use built-in HTML5 Canvas paths or SVG paths for the outlines (Car, Train, Dinosaur, Animal, Flower, Nature). Are simple line-art shapes acceptable?
> **3. Alphabet Train Game Mechanics:** How would you like the alphabet train game to be played? 
>   - Option A: Drag and drop train cars in alphabetical order (A-B-C...).
>   - Option B: Click on the train cars to hear the alphabet and see a related word.
>   - Option C: Connect alphabet blocks to the train to make it move.

## Proposed Changes

### 1. Mode Selection Updates
- Modify `#mode-screen` in `index.html` to include buttons for the 3rd game (색칠 놀이) and 4th game (알파벳 기차).

### 2. Game 3: Coloring Game
- Add a new screen `<div id="coloring-screen">`.
- Include a color palette (red, orange, yellow, green, blue, purple, etc.).
- Include a picture selector (thumbnail buttons for car, train, dinosaur, animal, flower).
- Implement a large HTML5 `<canvas>` for drawing.
- Add drawing logic (free-hand path drawing with selected color).
- Implement a "Save" button that uses `canvas.toDataURL()` to download the image as a PNG.

### 3. Game 4: Alphabet Train Game
- Add a new screen `<div id="alphabet-train-screen">`.
- Create train car UI elements.
- Implement game logic based on the user's preferred mechanic (e.g., ordering alphabet train cars).
- Add TTS (Text-to-Speech) for English alphabets so the user can hear the pronunciation.

## Verification Plan

### Manual Verification
- Start the app and click the new mode buttons.
- Select a picture in the coloring game, choose a color, draw on it, and click "Save" to verify the image is downloaded.
- Play the alphabet train game to ensure the logic and audio feedback work correctly.
