# JTGS Presentation Tools

## Installation

Install the required Python library:

```bash
pip install python-pptx
```

**Hint:** Consider setting up aliases (`~/.bashrc`):
```bash
# Usage: mksetlist Waymaker HolySpirit Praise AmazingGrace
alias mksetlist='python /path/to/scripts/folder/generate_setlist.py -s'
```

## Usage

### `generate_setlist.py`
Combines multiple PPTX songs into a single presentation with intro and transition slides.

**Command:**
```bash
python generate_setlist.py -s song_a song_b -o output.pptx
```
**Example usage:**
```bash
python generate_setlist.py -s Waymaker HolySpirit AmazingGrace
```

**Arguments:**
- `-s, --songs`: List of song filenames (without `.pptx` extension).
- `-o, --output`: Optional output filename (default: `JTGS_YYYY_MM_DD.pptx`).

**Configuration:** Uses `~/.config/jtgs-ppt/jtgs.conf` for paths to song folder, intro, and transition slides. Configuration example:
```ini
[Paths]
song_folder = /mnt/data/MUSIC
intro_slide = /mnt/data/MUSIC/intro.pptx
transition_slide = /mnt/data/MUSIC/transition.pptx
```

### `sanitize_pptx.py`
Batch processes presentations to remove slide transitions and map fonts (e.g., Arial Black to Noto Sans Black).

**Command:**
```bash
python sanitize_pptx.py
```

**Configuration:** Directly edit `INPUT_FOLDER` and `OUTPUT_FOLDER` within the script to set source and destination directories.

## LibreOffice UI Scaling Fix

Copy `libreoffice.conf` to `~/.config/environment.d/` and log out & in again. LibreOffice should be scaled properly.

**WARNING**: This will make ALL Qt apps scaled as well.

**TODO**: Find an alternative.