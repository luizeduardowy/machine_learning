# Experiment 1: Supervised Text Generation

This folder contains the first version of a prototype that attempts to generate text character by character using a population of small neural networks. The experiment combines manual evaluation with an automatic score based on the frequency of certain letters.

## File

- [`sl1.py`](./sl1.py): defines the networks, generates text, collects ratings, and updates parameters between epochs.

## How it works

The script creates 24 neural networks. Each network receives information about the initial prompt, the text it has generated so far, and the desired text length. The architecture declared in the code has two hidden layers with two neurons each and one output neuron. A custom character table encodes and decodes the values used by the prototype.

The main workflow is:

1. initialize random weights and biases for each network;
2. pass values through the layers and append characters to the responses;
3. start responses with the `Hi!` prompt, limiting the text to a maximum of 20 characters;
4. rank the networks by their scores;
5. ask the user to rate the text on a scale from 0 to 10, while also calculating a bonus related to the frequency of common letters;
6. move the parameters of lower-scoring networks toward the average parameters of the top-ranked networks, applying small random mutations.

The program runs epochs continuously. It asks for ratings when the counter reaches 50,000 epochs or after an interruption with `Ctrl+C`.

## How to run

Python and NumPy are required. From the repository root:

```powershell
python .\supervised_learning_test1\sl1.py
```

If NumPy is not installed:

```powershell
python -m pip install numpy
```

## Notes and limitations

- This is an exploratory experiment, not a production-ready natural language generator.
- The networks are initialized randomly on each run; the script does not save or restore trained parameters.
- Training runs continuously and may require user interaction to rate the responses.
- Character encoding and the update strategy are simplified implementations intended for learning.
