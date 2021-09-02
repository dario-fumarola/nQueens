# nQueens

This repository shows different algorithms to solve the [nQueens](https://en.wikipedia.org/wiki/Eight_queens_puzzle) problem.

## Description

A perceptron is a mathematical function modeled similarly to a biological neuron. It takes inputs, weighs them independently, adds them together, and passes the sum to a nonlinear function. Since it is the simplest form of artificial neuron, perceptrons are used for supervised learning of binary classifiers. The model learns the weights of the inputs to draw a linear decision boundary.



Perceptron work based on the Perceptron Learning Rule: an algorithm will automatically learn the optimal weight coefficient. As the model receives several inputs, it computes the sum and decides whether it reaches a certain threshold, so outputting a binary classification.

In this project, we are classyfing structured data using a perceptron following these steps:
* Inputs and weights are considered as matrices and multiplied
* The product is added to the bias
* Loss function calculates the error and optimizes with gradient discend

## Getting Started

### Dependencies

We will need:
* Keras
* NumPy
* SciPy
* Pandas
* Matplotlib
* Tensorflow
* Scikit-Learn


### Installing

The program runs through Jupyter Notebook, and requires a set of .csv data with a pair of values per input.

### Executing program

Upload both the .ipynb notebook and the dataset to a new Jupyter folder. Then, run the script cell-by-cell.
The program should output a visualization of the data, a final loss, and a confusion matrix. If all the values in this matrix fall in the diagonal, the model is accurate with an accuracy score of 1.0.





## Help

To load correctly the data run the command:
```
dataframe = pd.read_csv('data.csv')
dataframe.head()
```
If correct, it will display the first few lines as such:



Make sure you have installed all dependencies.


## License

This project is licensed under The Unlicense - see the LICENSE.md file for details


## Version History

* 0.1
    * Initial Release



