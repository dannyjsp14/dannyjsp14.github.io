# dannyjsp14.github.io
Data Science Projects

# Danny Sepulveda — Data Science Projects
Chemical Engineering, University of Florida

---

## Project 1: Predicting the Cavity-Size Distribution of PIM-1

**The question.** Can machine-learning regression models learn the smooth
cavity-size distribution of a PIM-1 membrane from a noisy histogram, and how
close can they get to the limit set by the noise in the data?

**The data.** 2,551 cavity diameters (in Å) from `PIM_1.unq`, binned into a
normalised histogram of 420 bins (0.025 Å wide). The models have 1 input
variable (bin-centre diameter) and 1 output (fraction of cavities per bin).

**What I did.**
1. Built the cavity-diameter histogram, with an adjustable bin width
2. Tuned and fitted seven regression models (Polynomial + Ridge, SVR, kNN,
   Random Forest, Gradient Boosting, MLP, Gaussian Process) using grid search
   inside nested cross-validation
3. Tested them on bins the models had never seen, compared the scores with the
   noise limit of the data, and ran an extrapolation stress test

**What I found.** The best model, Gradient Boosting, reaches R² = 0.861 on
unseen bins, against a noise ceiling of 0.893 (its error is only 1.29x the
unavoidable noise). kNN, the Gaussian Process, SVR and the MLP also come within
0.05 of the ceiling, so the choice of algorithm mattered far less than the
noise in the histogram. The models interpolate well but cannot extrapolate to
diameters outside the sampled range.

### Notebooks
- [1. ML analysis of the cavity-size distribution](notebooks/PIM1_ML_Analysis_V5.ipynb)

### Results
![Fitted curves, parity plot and residuals](figures/fitted_curves.png)

---

## About me
Second-year Chemical Engineering student interested in molecular dynamics
simulations of PIM membranes. Contact: sepulvedad.danny@ufl.edu

