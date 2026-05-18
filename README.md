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

Clone the required helper repository:

```bash
git clone https://github.com/arimue/PlanetScope_landslide_tracking.git
```

Create the environment:

```bash
conda env create -f environment.yml
conda activate YOUR_ENV_NAME
```

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

# Citation

This workflow builds upon methods presented in:
Mueting, A. and Bookhagen, B. (2024).
Tracking slow-moving landslides with PlanetScope data: new perspectives on the satellite's perspective.
Earth Surface Dynamics, 12, 1121–1143.
https://doi.org/10.5194/esurf-12-1121-2024
