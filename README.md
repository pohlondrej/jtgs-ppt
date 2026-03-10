# JTGS Presentation Tools

## Installation

Install the required Python library:

```bash
pip install python-pptx
```

## Usage

### `generate_setlist.py`
Combines multiple PPTX songs into a single presentation with intro and transition slides.

**Command:**
```bash
python3 generate_setlist.py -s song_a song_b -o output.pptx
```

- **Arguments:**
    - `-s, --songs`: List of song filenames (without `.pptx` extension).
    - `-o, --output`: Optional output filename (default: `JTGS_YYYY_MM_DD.pptx`).
- **Configuration:**
    Uses `~/.config/jtgs-ppt/jtgs.conf` for paths to song folder, intro, and transition slides.

### `sanitize_pptx.py`
Batch processes presentations to remove slide transitions and map fonts (e.g., Arial Black to Noto Sans Black).

**Command:**
```bash
python3 sanitize_pptx.py
```

- **Configuration:**
    Directly edit `INPUT_FOLDER` and `OUTPUT_FOLDER` within the script to set source and destination directories.
