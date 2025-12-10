# Sudoku (Java Swing)

A simple, single-file Java Swing implementation of a Sudoku GUI. This repository contains a playable 9x9 Sudoku game implemented with `JFrame`, `JButton`, and `GridLayout`. The UI includes a number pad, an error counter, reset and hint functionality, and a built-in solution for the sample puzzle.

---

## Features

* 9×9 Sudoku board rendered with Swing buttons
* Prefilled puzzle cells (disabled so they cannot be changed)
* Number pad (1–9) to select input
* Error counter that increments on wrong placements
* Reset button to restart the initial puzzle
* Hint button that fills one correct cell
* Completion detection with a congratulations dialog

---

## Files

* `Sudoku.java` — main Java source file. Contains the entire implementation (UI, event handling, puzzle + solution).

> If you split the code into multiple files, update this list accordingly.

---

## Requirements

* Java Development Kit (JDK) 8 or later
* No external libraries required (pure Java / Swing)

---

## Build & Run

From the repository root, compile and run the program with:

```bash
# compile
javac Sudoku.java

# run
java Sudoku
```

> On systems where multiple Java versions are installed, make sure `javac` and `java` correspond to the same JDK.

---

## Usage / Controls

1. Click a number button (1–9) to select that number.
2. Click an empty tile on the board to place the selected number.
3. If the number is incorrect, the error counter increases and the tile briefly flashes red.
4. `Reset` restores the board to the initial puzzle state and clears errors.
5. `Hint` fills one empty cell with the correct value from the internal solution.

---

## Code structure & important notes

* The project uses a nested `Tile` class that extends `JButton` and stores its own coordinates `(r, c)` and a `fixed` flag.
* The initial puzzle and the full solution are stored as `String[] puzzle` and `String[] solution`.
* Prefilled tiles are disabled (`setEnabled(false)`) and styled differently so the player cannot alter them.
* The UI is created and manipulated on the Swing Event Dispatch Thread via `SwingUtilities.invokeLater(...)`.
* Borders are drawn programmatically to highlight 3×3 subgrids using `BorderFactory.createMatteBorder`.

---

## Known improvements included in code

The version in this repository includes these fixes / improvements (compared to a minimal or earlier draft):

* Correct Java `String` usage (`isEmpty()` / `equals(...)`) instead of `!= ""`.
* Disabled prefilled tiles to prevent accidental editing.
* General border logic for drawing 3×3 box separators (no hard-coded cells).
* `tiles[][]` 2D array to simplify checks (completion, hints, reset).
* `Reset` and `Hint` buttons added.
* Visual feedback for invalid moves (tile flash) and user value styling.
* Uses Swing best practice of creating UI on the Event Dispatch Thread.

---

## TODO / Possible enhancements

* Allow replacing a previously entered number (currently disallowed to prevent accidental overwrites).
* Keyboard input support: map numeric keys to number buttons.
* Add difficulty levels / multiple puzzles loaded from files.
* Save / load game progress to a file.
* Timer, scoring, or limited error lives (game over condition).
* Unit tests for validating puzzle/solution logic.
* Refactor into multiple classes and packages for maintainability.

---

## Contribution

Feel free to open issues or submit pull requests. If you want to contribute, please:

1. Fork the repo
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Commit changes with clear messages
4. Open a PR describing your changes

---

## License

This project is available under the MIT License. See `LICENSE` for details.

---

## Author / Contact

Created by: Relx (replace with actual author)

If you want me to update the README (add screenshots, change wording, add run configurations or split into modules), tell me what you'd like and I will update it.
