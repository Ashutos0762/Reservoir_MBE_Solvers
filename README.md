# Material Balance Equation (MBE) Solvers

This project contains Python implementations of the Havlena-Odeh Material Balance Equation for analyzing various reservoir drive mechanisms. It was built to solve reservoir engineering problems, verify theoretical concepts using production and PVT data, and explore automated drive mechanism identification.

## Project Structure and Reservoir Models

The repository is structured around six distinct reservoir conditions, followed by a diagnostic modeling notebook. Each case applies the straight-line material balance methodology to isolate specific reservoir unknowns.

*   **`case1.ipynb`: Undersaturated Oil Reservoirs**
    Focuses on reservoirs operating above the bubble point. The notebook calculates the initial oil in place ($N$) by plotting the underground withdrawal ($F$) against total fluid expansion. It also demonstrates how accounting for rock and connate water expansion alters the final calculated volume.

*   **`case2.ipynb`: Saturated Oil Reservoirs**
    Analyzes reservoirs driven primarily by solution gas liberation. This script computes dynamic fluid saturations ($S_o$, $S_g$) at varying pressure depletion stages and derives the relative permeability ratio ($k_{rg}/k_{ro}$) using field production data.

*   **`case3.ipynb`: Gas-Cap Drive Reservoirs**
    Applies the Havlena-Odeh equation to reservoirs with an initial free gas cap. By plotting $F/E_o$ against $E_g/E_o$, the code determines both the initial oil in place ($N$) and the initial gas-cap size ratio ($m$) from the intercept and slope of the resulting linear trend.

*   **`case4.ipynb`: Water Drive Reservoirs**
    Evaluates reservoirs receiving pressure support from an adjacent aquifer. The notebook utilizes a simple pot aquifer model, plotting $F/E_o$ versus the pressure drop term ($\Delta P/E_o$) to calculate the initial oil in place ($N$) and the aquifer influx constant ($K$).

*   **`case5.ipynb`: Combination Drive Reservoirs**
    Addresses complex reservoirs supported simultaneously by fluid expansion, a gas cap, and water influx. Instead of iterative graphical methods, this notebook uses multiple linear regression to solve a three-variable system, determining $N$, $m$, and $K$ simultaneously while calculating the fractional contribution of each drive mechanism over time.

*   **`case6.ipynb`: Average Reservoir Pressure Estimation**
    Demonstrates a reverse application of the material balance equation. For fields lacking reliable pressure survey data, this script estimates average reservoir pressure at specific time steps by finding the numerical intersection between production-based fluid withdrawals and theoretical reservoir expansion.

*   **`ML_Drive_Mechanism_Classifier.ipynb`: Diagnostic Analysis**
    Extends traditional analysis by integrating machine learning. This notebook uses Campbell diagnostic plots to visually identify unmodeled energy sources. It then trains a Random Forest classifier on synthetic production deviations to automatically identify the dominant reservoir drive mechanism based on statistical features like R-squared values and deviation correlations.

---

## Usage

Each Jupyter Notebook is entirely self-contained. To review a specific case:

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/Ashutos0762/Reservoir_MBE_Solvers.git
