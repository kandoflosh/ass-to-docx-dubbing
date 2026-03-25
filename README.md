# ASS to DOCX Dubbing Converter

A Python application for converting Aegisub (.ass) subtitle files into formatted Word documents (.docx) with character-to-actor mapping and highlighting.

## Features

- 📝 Load and parse .ass (Aegisub) subtitle files
- 🎭 Map characters to voice actors
- 📄 Generate full script document with all dialogues
- 🎬 Generate individual actor scripts with highlighted character lines (yellow)
- 🌍 Full Unicode/Cyrillic support
- 🎯 Clean Aegisub-specific tags and formatting

## Requirements

- Python 3.8+
- PyQt6 (for GUI)
- python-docx (for Word document generation)

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/kandoflosh/ass-to-docx-dubbing.git
   cd ass-to-docx-dubbing
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Run the application:
   ```bash
   cd src
   python main.py
   ```

2. Click **"Load .ass File"** to select your subtitle file

3. The application will display all unique characters found in the file

4. Enter the corresponding actor name for each character in the "Actor" column

5. Click **"Generate Documents"** and select an output directory

6. The application will create:
   - `full_script.docx` - Complete script with all dialogues
   - `actor_<name>.docx` - Individual scripts for each actor with highlighted lines

## Project Structure

```
src/
├── main.py                 # Application entry point
├── gui/
│   ├── __init__.py
│   └── main_window.py      # PyQt6 GUI implementation
├── parser/
│   ├── __init__.py
│   └── ass_parser.py       # .ass file parser
└── generator/
    ├── __init__.py
    └── docx_generator.py   # Word document generator
```

## Document Format

Generated documents contain a table with three columns:

| Timecode | Character | Text |
|----------|-----------|------|
| 00:01    | Character Name | Dialogue text |

- **Timecode**: Converted to MM:SS format
- **Character**: Name of the speaking character
- **Text**: Cleaned dialogue (Aegisub tags removed)

Actor-specific scripts highlight character lines in yellow for easy identification.

## License

MIT License - See LICENSE file for details

## Author

kandoflosh