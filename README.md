<h1 align="center">House Price Prediction</h1>

<p align="center">
  <a href="https://www.python.org/">
    <img src="https://img.shields.io/badge/python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  </a>
  <a href="https://numpy.org/">
    <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy">
  </a>
  <a href="https://matplotlib.org/">
    <img src="https://img.shields.io/badge/Matplotlib-ffffff?style=for-the-badge&logo=matplotlib&logoColor=black" alt="Matplotlib">
  </a>
  <a href="LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-darkred?style=for-the-badge" alt="License">
  </a>
</p>


<p align="center">
  A high-performance implementation of <b>Linear Regression</b> using <b>Gradient Descent</b>. This project focuses on predicting house prices by optimizing model weights through iterative gradient updates, featuring data standardization and a comparative analysis against the pseudo-inverse (Normal Equation) solution.
</p>

<p align="center">
  <a href="#technical-architecture">
    <img src="https://img.shields.io/badge/Architecture-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#project-structure">
    <img src="https://img.shields.io/badge/Structure-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#mathematical-foundations">
    <img src="https://img.shields.io/badge/Math-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#technical-specifications">
    <img src="https://img.shields.io/badge/Specs-222222?style=flat" />
  </a>
  <span> ° </span>
  <a href="#deployment--installation">
    <img src="https://img.shields.io/badge/Deploy-222222?style=flat" />
  </a>
</p>

---
<br>

<h2 align="center">Technical Architecture</h2>

The system implements a classic machine learning workflow optimized for regression tasks. It emphasizes numerical stability and performance benchmarking:

1.  **Feature Standardization:** Implements Z-score normalization (via `scaling.py`) to center feature distributions, which is critical for the convergence speed of Gradient Descent.
2.  **Gradient Descent Optimization:** An iterative approach that calculates the direction of steepest descent to minimize the Mean Squared Error (MSE).
3.  **Model Validation:** Continuous monitoring of Root Mean Squared Error (RMSE) across both Training and Test datasets to detect potential overfitting.
4.  **Benchmarking:** Includes a direct comparison with the `np.linalg.pinv` solution, providing a reference for the accuracy of the iterative gradient descent method.

---
<br>

<h2 align="center">Project Structure</h2>

```
House_Price_Prediction/
├── LICENSE                                   # MIT License
├── README.md                                 # Project documentation
├── .gitattributes                            # Git configuration
├── Project Report.pdf                        # Technical research report
│
└── Code/                                     # Implementation scripts
    ├── simple_regression.py                  # Core logic (Training, GD, Plots)
    ├── scaling.py                            # Data normalization utilities
    ├── train.txt                             # Training dataset (House Prices)
    └── test.txt                              # Test dataset for validation
```

---
<br>

<h2 align="center">Mathematical Foundations</h2>

### 1. Hypothesis Function
The linear model used to predict the house price given input feature `x`.
```text
h_w(x) = w₀ + w₁x
```

### 2. Objective Function (MSE)
The "Least Squares" cost function that calculates the average squared error.
```text
J(w) = (1 / 2n) * Σ [h_w(x⁽ⁱ⁾) - y⁽ⁱ⁾]²
```

### 3. Gradient Calculation
The partial derivative of the cost function with respect to weights, used for updates.
```text
∇J(w) = (1 / n) * XT(Xw - y)
```

### 4. Root Mean Squared Error (RMSE)
Used as the primary metric for evaluating model performance in the original units.
```text
RMSE = sqrt( (1 / n) * Σ [h_w(x⁽ⁱ⁾) - y⁽ⁱ⁾]² )
```

---
<br>

<h2 align="center">Technical Specifications</h2>

<table align="center">
  <tr>
    <th align="center">Parameter</th>
    <th align="center">Configuration Details</th>
  </tr>
  <tr>
    <td align="center"><b>Algorithm</b></td>
    <td align="center">Linear Regression</td>
  </tr>
  <tr>
    <td align="center"><b>Optimization</b></td>
    <td align="center">Batch Gradient Descent</td>
  </tr>
  <tr>
    <td align="center"><b>Learning Rate (λ)</b></td>
    <td align="center">0.1 (Optimized for convergence)</td>
  </tr>
  <tr>
    <td align="center"><b>Epochs</b></td>
    <td align="center">500 Iterations</td>
  </tr>
  <tr>
    <td align="center"><b>Scaling</b></td>
    <td align="center">Z-Score (Standardization)</td>
  </tr>
  <tr>
    <td align="center"><b>Evaluation</b></td>
    <td align="center">RMSE comparison vs. Pseudo-Inverse</td>
  </tr>
</table>

---
<br>

<h2 align="center">Deployment & Installation</h2>

### Repository Acquisition
Clone the repository and enter the project directory:

```bash
git clone https://github.com/Zer0-Bug/House_Price_Prediction.git
```
```bash
cd House_Price_Prediction
```

### Environment Setup
Create a virtual environment and install the required numerical libraries:

```bash
# Environment initialization
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install numpy matplotlib
```

### Running the Project
The main implementation script will process the data, perform training, and generate visualization plots:

```bash
python Code/simple_regression.py
```

---
<br>

<h2 align="center">Contribution</h2>

Contributions are always appreciated. Open-source projects grow through collaboration, and any improvement—whether a bug fix, new feature, documentation update, or suggestion—is valuable.

To contribute, please follow the steps below:

1. Fork the repository.
2. Create a new branch for your change:  
   `git checkout -b feature/your-feature-name`
3. Commit your changes with a clear and descriptive message:  
   `git commit -m "Add: brief description of the change"`
4. Push your branch to your fork:  
   `git push origin feature/your-feature-name`
5. Open a Pull Request describing the changes made.
<br>
All contributions are reviewed before being merged. Please ensure that your changes follow the existing code style and include relevant documentation or tests where applicable.

---
<br>
<h2 align="center">References</h2>

1. **Breiman, L. (2001)** - [Statistical Modeling: The Two Cultures](https://doi.org/10.1214/ss/1009213726). *Statistical Science*.  
2. **Hastie, T., Tibshirani, R., & Friedman, J. (2009)** - [The Elements of Statistical Learning](https://web.stanford.edu/~hastie/ElemStatLearn/). *Springer*.  
3. **Goodfellow, I., Bengio, Y., & Courville, A. (2016)** - [Deep Learning, MIT Press](https://www.deeplearningbook.org/).  

---
<br>
<p align="center">
  <a href="mailto:777eerol.exe@gmail.com">
    <img src="https://cdn.simpleicons.org/gmail/D14836" width="40" alt="Email">
  </a>
  <span> × </span>
  <a href="https://www.linkedin.com/in/eerolexe/">
    <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png"
         width="40"
         alt="LinkedIn">
  </a>
</p>

---

<p align="center" style="margin-top:10px; letter-spacing:4px;">
  ∞
</p>
