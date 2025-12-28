---
description: "Configure agent behavior for Rubik's Cube simulator project"
argument-hint: "Project-specific agent configuration and constraints"
model: ""
agent: ""
subtask: ""
---

# Rubik's Cube Simulator - Agent Configuration

## Project Overview
Single-file Rubik's Cube simulator using vanilla HTML/CSS/JS with CSS 3D transforms. No build tools, frameworks, or external dependencies beyond Font Awesome CDN icons.

## Core Constraints (NON-NEGOTIABLE)

### Technology Stack
- **STRICTLY** vanilla HTML/CSS/JavaScript
- **NO** build tools (webpack, vite, etc.)
- **NO** frameworks (React, Vue, Angular, etc.)
- **NO** canvas/WebGL - use CSS 3D transforms only
- **NO** npm packages unless explicitly requested
- **NO** TypeScript unless explicitly requested

### File Structure
- **PRIMARY**: `index.html` - contains ALL UI, styles, and logic
- **DEBUG**: `cube-debug.html` - debug viewer with net/layers views
- **DOCS**: `README.md` - project documentation
- **NOTES**: `AGENTS.md` - existing agent guidelines

### Code Organization
- Keep everything in `index.html` unless explicitly requested otherwise
- Prefer small, localized edits
- Avoid heavy dependencies
- Use CSS 3D transforms for all 3D rendering

## Cube Implementation Details

### Color Scheme
- U (Up): Yellow
- D (Down): White  
- F (Front): Red
- R (Right): Green
- L (Left): Blue
- B (Back): Orange

### Default View
- Rotation: rotX -15, rotY -15
- Coordinates overlay shown in top-right
- Move counter shown in top-left

### Cube Sizes Supported
- 2x2
- 3x3 (standard)
- 3x3 twisted preset
- 4x4

### Move Behavior
- View-relative R/L mapping
- R/L depend on current front-facing side
- Turn direction picks "upward" column on screen
- R indicator displayed on front face (top-right corner)

### Data Structure
- Stickers stored as `{pos, normal, color}`
- `rotateLayer()` updates both pos and normal
- Rendering: `.face` nodes containing `.sticker` nodes
- Animation queue for move sequences

## Agent Behavior Guidelines

### When Working on This Project

#### DO:
- Read existing code before making changes
- Test in browser after modifications
- Follow vanilla JS patterns already established
- Use CSS 3D transforms for any 3D effects
- Keep changes minimal and localized
- Maintain existing UI/UX patterns

#### DO NOT:
- Add build tools or package.json
- Introduce frameworks or libraries
- Use canvas/WebGL for rendering
- Break the single-file structure
- Change the core CSS 3D approach
- Add unnecessary complexity

### Feature Implementation
- New features should integrate with existing patterns
- UI controls should match existing style
- Animations should use existing animation system
- Debug features should follow cube-debug.html patterns

### Bug Fixes
- Identify root cause in existing code
- Make minimal, targeted fixes
- Test thoroughly in browser
- Ensure no regressions in other features

## Development Workflow

### Local Testing
```bash
cd /Users/clm/Documents/GitHub/WEB/Web_pkrubik
python3 -m http.server 5173
# Open http://localhost:5173
```

### Verification Steps
1. Test in multiple browsers (Chrome, Firefox, Safari)
2. Verify cube manipulation works correctly
3. Check animations and UI responsiveness
4. Validate move notation parsing
5. Test scramble/reset functionality

## Known Quirks & Considerations

### Current Limitations
- `getFrontFace()` only considers F/R/B/L for R/L mapping
- Scramble increments move counter as moves play
- No support for upside-down viewpoints in R/L mapping

### When Extending Functionality
- Consider expanding `getFrontFace()` for U/D support
- Evaluate move counter behavior for scramble
- Maintain backward compatibility with existing move sequences

## Emergency Procedures

### If Something Breaks
1. Revert to last working state
2. Identify what changed
3. Make minimal fix
4. Test thoroughly
5. Document the issue and solution

### If Unsure About Approach
1. Study existing patterns in index.html
2. Check AGENTS.md for specific guidance
3. Make minimal test changes first
4. Verify before expanding scope

## Project Philosophy
This project demonstrates that complex 3D interactions can be achieved with vanilla web technologies. The constraint-driven approach (no build tools, single file) is intentional and should be preserved.