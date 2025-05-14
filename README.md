# Ausbreitung-einer-ansteckenden-Krankheit
# Infectious Disease Spread Simulation in Dormitory

## Project Overview

This Jupyter Notebook simulates the spread of an infectious disease (e.g., SARS-CoV‑2) in a controlled environment—a dormitory ("Schlafsaal"). The model is based on a grid (matrix) where each entry represents a person’s health state. Optional features include:

* Death probability (Sonderfall A)
* Incubation period (Sonderfall B)
* Vaccination rollout (Sonderfall C)
* Daily bed swapping (Sonderfall D)

At each time step (day), the simulation updates infection, recovery, death, and vaccination, then visualizes the dormitory as either an image sequence or an animated video.

## Authors

* **Kilian Runnwerth** 
* **Dominic Lehm** 

## Prerequisites

Install dependencies listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

Required packages include:

* numpy >= 1.21
* matplotlib >= 3.4
* ipython >= 7.0
* jupyterlab >= 3.0  # if using JupyterLab

## Project Structure

```
project-root/
├── disease_spread_simulation.ipynb   # Main Jupyter Notebook
├── requirements.txt                  # Python dependencies
├── README.md                         # This document
└── images/                           # (Optional) output images for image sequence
```

## Usage

1. **Launch Jupyter**:

   ```bash
   jupyter lab  # or jupyter notebook
   ```
2. **Open** `disease_spread_simulation.ipynb`.
3. **Run all cells** and follow the input prompts:

   * Number of rows (n) and columns (m)
   * Initial patient position (kx, ky)
   * Infection probability (p)
   * Disease duration (k)
   * Enable/disable Sonderfälle (A–D)
   * Animation output mode:

     * `0` – Save MP4 video
     * `1` – Display video inline (no save)
     * `2` – Export daily images (PNG sequence)

### Animation Output

* **Image Sequence**: Saved under `images/` (one PNG per day). Useful for frame-by-frame analysis.
* **MP4 Video**: Requires `ffmpeg`. Configure the path in the notebook:

  ```python
  matplotlib.rcParams['animation.ffmpeg_path'] = '/path/to/ffmpeg'
  ```

  After running, the video (e.g. `animation.mp4`) will be saved in the working directory.

![Simulation Animation](animation.gif)
## Results & Interpretation

Refer to Section 3 of the notebook for detailed analyses:

* 3.1 Without Sonderfälle: circular spread patterns
* 3.2 with Death (A)
* 3.3 with Incubation (B)
* 3.4 with Vaccination (C)
* 3.5 with Bed Swapping (D)
* 3.6 Combined scenarios (A–D)

## References

1. Python `random.seed()`: [https://www.w3schools.com/python/ref\_random\_seed.asp](https://www.w3schools.com/python/ref_random_seed.asp)
2. Reshape NumPy arrays: [https://www.projectpro.io/recipes/reshape-numpy-array-in-python](https://www.projectpro.io/recipes/reshape-numpy-array-in-python)
3. `numpy.random.choice`: [https://numpy.org/doc/stable/reference/random/generated/numpy.random.choice.html](https://numpy.org/doc/stable/reference/random/generated/numpy.random.choice.html)
4. Check zero values in NumPy: [https://www.geeksforgeeks.org/python-check-if-all-values-in-numpy-are-zero/](https://www.geeksforgeeks.org/python-check-if-all-values-in-numpy-are-zero/)
5. Matplotlib `imshow` with custom colors: [https://stackoverflow.com/questions/37719304/python-imshow-set-certain-value-to-defined-color](https://stackoverflow.com/questions/37719304/python-imshow-set-certain-value-to-defined-color)
6. Gridlines in `imshow`: [https://stackoverflow.com/questions/38973868/adjusting-gridlines-and-ticks-in-matplotlib-imshow](https://stackoverflow.com/questions/38973868/adjusting-gridlines-and-ticks-in-matplotlib-imshow)
7. Chessboard-like plots: [https://stackoverflow.com/questions/10194482/custom-matplotlib-plot-chess-board-like-table-with-colored-cells](https://stackoverflow.com/questions/10194482/custom-matplotlib-plot-chess-board-like-table-with-colored-cells)
8. Matplotlib `pyplot.title`: [https://matplotlib.org/api/\_as\_gen/matplotlib.pyplot.title.html](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.title.html)
9. Saving Matplotlib animations: [https://holypython.com/how-to-save-matplotlib-animations-the-ultimate-guide/](https://holypython.com/how-to-save-matplotlib-animations-the-ultimate-guide/)
10. FFmpeg on Windows: [https://www.youtube.com/watch?v=IECI72XEox0](https://www.youtube.com/watch?v=IECI72XEox0)
11. FFmpeg on macOS: [https://www.youtube.com/watch?v=H1o6MWnmwpY](https://www.youtube.com/watch?v=H1o6MWnmwpY)

---

*Developed as part of the "Mathematische Software" course (WiSe 2022/23) by Olaf Bochmann.*
