# Repository Guidelines

## Project Structure & Module Organization
- `temporizador.py`: main Tkinter Pomodoro timer application.
- `setup.py`: py2app configuration for building a macOS app bundle.
- `alarma.mp3`: sound played when each timer completes.
- `diagrama-flujo.png`: flowchart referenced by the documentation.
- `README.txt`: Spanish, line-by-line explanation of the script.
- `venv/`: local virtual environment (not committed output; treat as local-only).

## Build, Test, and Development Commands
- Run locally: `python3 temporizador.py` (launches the GUI timer).
- Build macOS app: `python3 setup.py py2app` (creates a `.app` bundle; requires py2app).
- Install dependencies: `python3 -m pip install -U py2app` (only needed for builds).

## Coding Style & Naming Conventions
- Language: Python 3, Tkinter GUI.
- Indentation: 4 spaces.
- Naming: `snake_case` for functions/variables, `UPPER_SNAKE_CASE` for constants.
- Keep UI text in Spanish to match existing copy.
- Avoid non-portable system calls unless guarded (current alarm uses `afplay`, macOS-only).

## Testing Guidelines
- No automated tests or framework are present.
- If adding tests, prefer `pytest` and place them in `tests/` with names like `test_temporizador.py`.
- Manual validation: run the GUI and verify the work/break cycle, sound playback, and dialog flow.

## Commit & Pull Request Guidelines
- Commit history uses short, Spanish, imperative-style messages (e.g., "Agregar", "Actualizar", "Ignorar").
- Keep commits focused on one change.
- PRs should include a concise summary, steps to test (e.g., `python3 temporizador.py`), and screenshots for UI changes.

## Security & Configuration Notes
- The alarm playback uses `os.system("afplay alarma.mp3")`. Keep the file name stable or update the command accordingly.
- On non-macOS systems, replace `afplay` with an OS-appropriate audio command.
