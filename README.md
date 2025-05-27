[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/CMOE-TUDelft/ODE_Research_Project_Drag/HEAD?urlpath=%2Fdoc%2Ftree%2Ftest.ipynb)

# 🌀 Drag coefficient estimation

This project provides a Pluto.jl notebook to solve the time-dependent incompressible Navier-Stokes equations using stabilized finite element methods with [Gridap.jl](https://github.com/gridap/Gridap.jl) to estimate drag coefficient in 2D flow around a structure. This guide is aimed at **non-experts in Julia**.

This tutorial is designed for the students doing the "Drag Coefficient Estimation" project of the course *OE44190: Offshore Research Project*. But it is open to the general audience.

<img src="plots/gifs/square_drag.gif" width="500">

---

## 1. Install Julia

1. Go to the [official Julia website](https://julialang.org/downloads/).
2. Download the **latest stable version** for your operating system.
3. Follow the installation instructions:

   * On Windows: run the `.exe` installer.
   * On macOS: open the `.dmg` and drag Julia to Applications.
   * On Linux: extract the tarball and add the binary path to your `PATH`.

To verify installation, open a terminal or command prompt and type:

```bash
julia
```

---

## 2. Install VS Code (not required)

We assume that the user will use VS Code to run julia code. This is not required and the same calls from point 3 onwards can be done directly from the terminal or other IDE.

1. Download [Visual Studio Code](https://code.visualstudio.com/).
2. *OPTIONAL*: Open VS Code, go to the **Extensions** tab (Ctrl+Shift+X), and search for "Julia".

---

## 3. Open and Run the Pluto Notebook

1. Clone or download this repository:

```bash
git clone https://github.com/CMOE-TUDelft/NavierStokes-DragCoef-FEM-Tutorial.git
cd ODE_Research_Project_Drag
```

2. Open the project folder in VS Code.

3. Press `Ctrl+Shift+P`, type and select: `Julia: Start REPL`.

4. Activate the julia environment and instantiate the packages. In the Julia REPL, type `]` to enter in the package mode and call `instantiate` function

```julia
instantiate
```

5. In the Julia REPL, start Pluto:

```julia
import Pluto
Pluto.run()
```

6. Your browser will open a Pluto interface. Click **"Open from file"** and select the notebook file:

```
drag_square.jl
```

---

## 4. Execute and Change Parameters

* Once the notebook loads, click **"Run All"** at the top or press `Shift+Enter` inside each cell to execute it.
* You can change simulation parameters like:

  * Time step size `Δt`
  * Total simulation time `T`
  * Kinematic viscosity `ν`
  * Body forces
  * Initial/boundary conditions

Pluto automatically re-runs dependent cells when you change a value.

---

## 5. Where is the Solution Stored?

The computed solution (velocity and pressure fields) is stored and exported in **VTK (.vtu, .pvd)** files inside the `data/` folder (or the specified output path in the notebook).

The `.pvd` file contains a link to all time steps. Each time step is stored as a separate `.vtu` file, e.g.:

```
data/FILENAME.pvd
data/FILENAME_0.01.vtu
data/FILENAME_0.02.vtu
...
```

---

## 6. Visualizing the flow field with ParaView

1. Download and install [ParaView](https://www.paraview.org/download/).

2. Open ParaView and go to **File > Open**.

3. Navigate to the `data/` directory and open the `.pvd` files.

4. Click **"Apply"** in the Properties panel.

5. Use the toolbar to:

   * Animate time series
   * Plot velocity vectors or pressure contours
   * Slice, probe, or visualize streamlines

You can be createive here.

---

## 📩 Questions?

If you encounter issues, feel free to [open an issue](https://github.com/CMOE-TUDelft/NavierStokes-DragCoef-FEM-Tutorial/issues) or contact the maintainer.

---
