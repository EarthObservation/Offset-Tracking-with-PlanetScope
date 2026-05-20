# Offset-Landslide-Tracking-with-PlanetScope
Workflow for landslide displacement tracking using PlanetScope imagery and Ames Stereo Pipeline (ASP), including image download, preprocessing, offset tracking, and visualization.

The notebook `Sledenje_odmikov_pikslov_plazovi.ipynb` includes:

* PlanetScope image search and download
* preprocessing
* offset tracking
* visualization of displacement results

---

# Requirements

* Planet API key
* AOI polygon/shapefile
* Ames Stereo Pipeline (ASP)
* Conda

---

# Installation

Clone this repository:

```bash
git clone https://github.com/EarthObservation/Offset-Tracking-with-PlanetScope-Data.git
```

Create the environment:

```bash
conda env create -f environment.yml
conda activate YOUR_ENV_NAME
```

Set your Planet API key:

1. Sign in to your Planet account.
2. Open **Account** -> **My Settings**.
3. Reveal and copy the value shown in the **API Key** section.

Export it in your shell before running the notebook:

```bash
export PL_API_KEY="your-planet-api-key"
```

To make it persistent across new shell sessions, add it to your shell profile (`~/.bashrc` or `~/.zshrc`):

```bash
echo 'export PL_API_KEY="your-planet-api-key"' >> ~/.bashrc  # use ~/.zshrc if you use zsh
source ~/.bashrc  # or: source ~/.zshrc
```

The notebook reads `PL_API_KEY` from the environment. If you prefer not to export it, it can also fall back to a local `planet_api_key.txt` file containing only the key, but using the environment variable is the recommended setup.

---

# Install Ames Stereo Pipeline (ASP)

Download ASP:

```bash
wget https://github.com/NeoGeographyToolkit/StereoPipeline/releases/download/3.6.0/StereoPipeline-3.6.0-2025-12-26-x86_64-Linux.tar.bz2
```

Extract:

```bash
tar -xjf StereoPipeline-3.6.0-2025-12-26-x86_64-Linux.tar.bz2
```

Add ASP to PATH:

```bash
echo 'export PATH=$PATH:$HOME/StereoPipeline-3.6.0-2025-12-26-x86_64-Linux/bin' >> ~/.bashrc
source ~/.bashrc
```

Verify installation:

```bash
parallel_stereo --help
```

---

# Notes

This repository is intended as a research workflow for landslide monitoring using PlanetScope imagery and offset tracking techniques.

The notebook's `Sledenje_odmikov_pikslov_plazovi.ipynb` comments and variable names are partially written in Slovene, as the workflow was also developed for teaching purposes.

Helper modules from `PlanetScope_landslide_tracking` are vendored in `planetscope_landslide_tracking/`, so a separate helper repository clone is no longer required. The vendored helper code is distributed under its upstream MIT license in `planetscope_landslide_tracking/LICENSE`.

# Citation

This workflow builds upon methods presented in:
Mueting, A. and Bookhagen, B. (2024).
Tracking slow-moving landslides with PlanetScope data: new perspectives on the satellite's perspective.
Earth Surface Dynamics, 12, 1121–1143.
https://doi.org/10.5194/esurf-12-1121-2024
