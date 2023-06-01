<h1>LassoPredictiveModeling</h1>

<p>A function for performing LASSO (Least Absolute Shrinkage and Selection Operator) predictive modeling in R.</p>

<h2>Description</h2>

<p>The <code>LassoPredictiveModeling</code> function automates the process of training a LASSO model, selecting the optimal lambda value using cross-validation, evaluating model performance on the training and test sets, and extracting non-zero coefficient variables.</p>

<h2>Usage</h2>

<pre><code>results &lt;- LassoPredictiveModeling(data, train_prop, folds, a, b, lambda_min)
</code></pre>

<h2>Arguments</h2>

<ul>
  <li><code>data</code>: The input dataset for modeling.</li>
  <li><code>train_prop</code>: The proportion of data to use for training (between 0 and 1).</li>
  <li><code>folds</code>: The number of folds for cross-validation.</li>
  <li><code>a</code> and <code>b</code>: The column indices indicating the range of predictor variables.</li>
  <li><code>lambda_min</code>: A logical value indicating whether to use lambda.min (TRUE) or lambda.1se (FALSE) as the optimal lambda value.</li>
</ul>

<h2>Output</h2>

<p>The function returns a list of results, including:</p>

<ul>
  <li><code>optimal_lambda</code>: The selected optimal lambda value.</li>
  <li><code>names_nonzero_coefs</code>: The names of the predictor variables with non-zero coefficients.</li>
  <li><code>nonzero_coefs</code>: The values of the non-zero coefficients.</li>
  <li><code>MSE_train</code>: The mean squared error on the training set.</li>
  <li><code>MSE_test</code>: The mean squared error on the test set.</li>
  <li><code>R_squared</code>: The R-squared value indicating model fit.</li>
</ul>

<h2>Example</h2>

<pre><code># Load required packages
library(glmnet)

# Create a sample dataset
data &lt;- mtcars

# Run LassoPredictiveModeling
results &lt;- LassoPredictiveModeling(data, train_prop = 0.8, folds = 5, a = 2, b = 6, lambda_min = TRUE)

# Print the results
print(results)
</code></pre>

<h2>License</h2>

<p>This project is licensed under the <a href="LICENSE">MIT License</a>.</p>
