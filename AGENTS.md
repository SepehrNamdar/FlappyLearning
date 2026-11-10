# Repository guidance

## Project layout
- The application lives in `FlappyLearning/`, which has its own Git metadata. Run application Git commands with `git -C FlappyLearning ...` and check status before editing.
- `index.html` loads the canvas demo and speed controls.
- `game.js` implements rendering, physics, scoring, and the training loop.
- `Neuroevolution.js` implements neural networks and genetic evolution; its public API is documented in `README.md`.
- `img/` contains the sprites and background. Preserve `License` and existing attribution.

## Run locally
- Open `FlappyLearning/index.html` in a browser; there is no build or dependency installation step.
- Alternatively, if Python is available, run `python -m http.server 8000 --directory FlappyLearning` from this directory and visit `http://localhost:8000`.
- No package manifest, automated test suite, or lint configuration is currently present.

## Editing conventions
- Keep changes focused and preserve unrelated work in both Git repositories.
- Follow the surrounding JavaScript style: tabs, `var`, constructor functions, and prototype methods. Avoid broad formatting changes.
- Keep the app runnable as plain browser scripts. Preserve script order: `Neuroevolution.js` before `game.js`.
- Maintain the global APIs used by the page, including `Neuroevolution` and `speed`, unless the task explicitly changes them.
- Avoid introducing dependencies or build tooling unless the requested work needs them.
- Update `FlappyLearning/README.md` when changing documented options, public APIs, or run instructions.

## Verification
- For behavior changes, load the demo and check the browser console for errors, asset loading, bird and pipe rendering, score updates, and generation rollover.
- Exercise the speed controls, including MAX, when changing timing or the game loop.
- Training is random; verify valid network outputs, population behavior, and continued generation progression rather than expecting identical scores across runs.
- Report what was checked and any verification that could not be performed.
