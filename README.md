# Barebones OSKAR

Repository of some simple settings file, telescope models, and sky models to get
started with OSKAR simulations.

the sources only sky model is just [this](https://github.com/JLBLine/srclists)
but converted to OSKAR format. It does NOT have the shapelets model of FornaxA
properly converted.

The current pointing is a zenith pointing of EoR0 (0, -27), using a real start
time from a real MWA observation. Astroplan will be needed if you want good
pointings of other fields.

## Note
The data in this repo has had the telescope layouts flipped (N->E, E->N) to match the real telescope.

This was done simply using this script:

```python
import numpy as np
from pathlib import Path

base_dir = Path()
telescopes_dirs = base_dir.glob("telescope_model_*")
for telescope_dir in telescopes_dirs:
    layout_file = telescope_dir / "layout.txt"
    assert layout_file.exists()
    layout_data = np.loadtxt(layout_file, delimiter=",")
    layout_data_fixed = layout_data[:, [1, 0, 2]]
    np.savetxt(layout_file, layout_data_fixed, delimiter=",", fmt="%0.17g")
```