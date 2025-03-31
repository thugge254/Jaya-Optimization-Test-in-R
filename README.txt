Jaya Optimization in R

Project Overview

This project demonstrates the usage of the Jaya optimization algorithm in R, 
implemented via the Jaya package. The Jaya algorithm is a population-based, 
gradient-free optimization method that requires no hyperparameter tuning, 
making it simple yet effective for solving both single-objective and multi-objective optimization problems.

Installation

To install the Jaya package in R:
install.packages("Jaya", repos = "https://cloud.r-project.org")

Usage

The project optimizes the following function:

Objective

Minimize  with two variables:

 ranging from -10 to 10

 ranging from -10 to 10

Implementation

The optimization process is implemented in an R Markdown file. Below is an overview of the main function:
# Define the objective function
objective_function <- function(x) {
  (x[1] - 3)^2 + (x[2] + 2)^2
}

# Define the bounds
lower_bounds <- c(-10, -10)
upper_bounds <- c(10, 10)

# Run the Jaya algorithm
library(Jaya)
result <- jaya(
  fun = objective_function,
  lower = lower_bounds,
  upper = upper_bounds,
  popSize = 20,
  maxiter = 100,
  n_var = 2,
  opt = "minimize"
)

# Print and visualize results
print(summary(result))
plot(result)

Results

The Jaya finds the optimal values for  and  that minimize . The output includes:
The best solution found (optimal variable values and objective function value).
A plot showing the convergence of the optimization process.

Repository Structure

├── Jaya-Optimization-Test-in-R.Rmd  # R Markdown file for the test
├── README.md                         # Project documentation


License

Since the project is open-source, the license is available under the MIT license.

