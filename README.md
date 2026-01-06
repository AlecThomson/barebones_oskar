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