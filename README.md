# Parametric Curve Fitting using Gradient-Based Optimization

## 📘 Overview
This project aims to identify unknown parameters **θ (rotation angle)**, **M (exponential growth factor)**, and **X (horizontal translation)** of a given parametric curve using numerical optimization and gradient-based learning.

The problem was provided as a research-oriented assignment to explore both **mathematical modeling** and **computational optimization** in the context of AI and ML applications.

---

## 🧩 Problem Definition

The given curve is defined as:

<img width="629" height="183" alt="image" src="https://github.com/user-attachments/assets/97b46ebb-8b4d-46bc-b772-56402bd0e4ba" />


The task is to determine the constants **θ**, **M**, and **X** such that the above equations best fit the given set of (x, y) data points in `xy_data.csv`.

---

## 🧮 Approach

The project uses a **gradient-based optimization** method inspired by deep learning frameworks to iteratively minimize the error between the actual data and the predicted curve.

### Steps Followed

1. **Data Loading**  
   The dataset (`xy_data.csv`) was imported containing measured (x, y) points.

2. **Model Definition**  
   The parametric form of the curve was defined using trigonometric and exponential functions.  
   Parameters θ, M, and X were initialized as learnable variables.

3. **Loss Function**  
   The error between the observed and predicted data was calculated using a combination of:
   - L2 (Mean Squared Error) for smooth convergence
   - L1 (Absolute Error) for robust fine-tuning
   - A small penalty term to keep the parameter `t` within the valid range (6 ≤ t ≤ 60)

4. **Optimization**  
   The parameters were optimized using the **Adam optimizer** with a gradually decaying learning rate (scheduler).  
   Training was run for 4000 epochs until convergence.

5. **Visualization**  
   - Actual (x, y) data points were plotted as blue dots.  
   - The fitted curve was plotted in red to visually confirm the accuracy of the fit.  
   - The final parameters were also validated through a parametric plot in Desmos.

---

## 🧮 Final Results

After optimization, the following parameters were obtained:

| Parameter | Symbol | Actual (from Optimization) | Approximated (Rounded/Expected) | 
|------------|:-------:|:--------------------------:|:-------------------------------:|
| Rotation angle | θ | 29.999794° | 30° (0.5236 rad) | 
| Exponential factor | M | 0.029241 | 0.0300 |
| Horizontal shift | X | 55.000210 | 55.0000 | 

The final fitted parametric curve:

<img width="1257" height="107" alt="image" src="https://github.com/user-attachments/assets/06c850fe-5384-4bae-a044-54c759173991" />


---

## 📊 Visualization

**Desmos Parametric Equation (for reference)**: \left(t*\cos(0.5236)-e^{0.03\left|t\right|}\cdot\sin(0.3t)\sin(0.5236)\ +55,42+\ t*\sin(0.5236)+e^{0.03\left|t\right|}\cdot\sin(0.3t)\cos(0.5236)\right)
<img width="1551" height="954" alt="image" src="https://github.com/user-attachments/assets/335d6bd8-7a75-4135-8f59-674232da86b0" />


