# Experiment 1: Fitting a Linear Model

This folder contains a small numerical learning experiment. Although the folder name mentions *reinforcement learning*, the script does not implement reinforcement learning: it fits a linear model to known input/output examples.

## File

- [`rl1.py`](./rl1.py): creates and trains a linear predictor with one weight and one bias.

## How it works

The model calculates a prediction using the formula:

```text
prediction = weight * input + bias
```

The script uses inputs `1` through `5` and targets `13`, `16`, `19`, `22`, and `25`, which follow the relationship `3 * input + 10`. The weight and bias start with random values. Then, over 2,500 epochs, the program:

1. calculates predictions for the training examples;
2. measures the absolute errors and determines whether each prediction is above or below its target;
3. adjusts the weight and bias using the average error signs and a fixed learning rate;
4. prints the parameters and the average error for the epoch.

After training, it calculates predictions for inputs `6` and `7` and compares them with targets `28` and `31`.

## How to run

Python and NumPy are required. From the repository root:

```powershell
python .\reinforcement_learning_test1\rl1.py
```

If NumPy is not installed:

```powershell
python -m pip install numpy
```

## Notes

- The initial values are random, so intermediate parameters may vary between runs.
- The program prints one line per epoch, for a total of 2,500 progress lines, followed by the final predictions.
- This is a teaching example of fitting a linear model; it has no environment, actions, rewards, or policy, which are typical elements of reinforcement learning.
