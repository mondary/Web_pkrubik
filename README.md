# Rubik's Cube Simulator

A single-file, vanilla HTML/CSS/JS Rubik's Cube simulator with a 3D view and move controls. The project is intentionally minimal and runs in a browser with no build step.

## Features
- 3D cube view (CSS 3D) with drag-to-rotate camera
- Move buttons (R, L, U, D, F, B with prime and double variants)
- Move notation input (e.g., `R U R' U'`)
- Animated face turns with speed control
- Scramble action (move counter resets on scramble)
- "Sexy move" shortcut button (R U R' U')
- View-relative R/L mapping (R always acts on the right column of the face currently in front)
- Dynamic R indicator shown on the front face (top-right corner)

## Controls
- Drag the cube to rotate the view
- Use the move buttons or input a sequence and press play
- Speed buttons (turtle, rabbit, lightning) adjust animation duration
- Reset: returns to solved state
- Scramble: applies a random sequence and resets the counter

## View-relative R/L behavior
R and L are mapped to the cube face that is currently "front" in the view:
- Front F -> R acts on face R
- Front R -> R acts on face B
- Front B -> R acts on face L
- Front L -> R acts on face F

The turn direction is chosen so that the right column appears to move upward on screen.

## Run locally
```bash
cd /Users/clm/Documents/GitHub/WEB/Web_pkrubik
python3 -m http.server 5173
```
Open http://localhost:5173

## Project structure
- `index.html` - all UI, styles, and cube logic

## Notes
- No external build tools or frameworks are used.
- Font Awesome icons are loaded from CDN.
