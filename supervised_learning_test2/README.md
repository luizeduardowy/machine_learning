# Experiment 2: Text Generation Prototype

This folder contains the second version of a neural-network text generation experiment. Compared with the first version, the code describes a larger population, more layers, explicit character encoding, and several planned training stages.

## File

- [`sl2.py`](./sl2.py): contains the network configuration, vocabulary, encoding and scoring functions, and the main loop that is under development.

## Design described in the code

The configuration specifies 32 candidate networks, each with:

- 10 input values: five for the prompt, one for the target text length, and four for the recent generation context;
- four hidden layers with 10 neurons each;
- two outputs: one to select the character and another to indicate whether a letter should be uppercase.

The vocabulary includes lowercase letters, digits, spaces, and basic punctuation. The encoding and decoding functions convert between characters and numeric identifiers, which are used as network values.

The script's constants and comments describe four intended training stages:

1. **Prediction:** train with example sentences, attempting to predict the next characters;
2. **Questions:** generate responses to predefined prompts and use automatic scoring criteria;
3. **User ratings:** incorporate the ratings given to the responses;
4. **Final training:** combine automatic criteria and ratings to rank and update the population.

The automatic score is intended to consider letter frequency, the number of spaces, and consecutive character repetition. The code also defines an elite network fraction and mutation parameters to guide candidate updates.

## Current status and how to run

This file is still incomplete: the training-stage blocks in the main loop have not been implemented. Therefore, the script is not ready to run as a functional program. The stages above describe the intent recorded in the code, not a completed training workflow.

The external library imported is NumPy; `math`, `os`, and `random` are part of the Python standard library. Once implementation is complete, run the script from the repository root with:

```powershell
python .\supervised_learning_test2\sl2.py
```

If needed, install NumPy with:

```powershell
python -m pip install numpy
```

## Notes and limitations

- This is an experimental prototype with no external dataset.
- The weights are initialized randomly, and the code does not define persistence for trained models.
- The design of the stages, scoring criteria, and mutations is documented in the script, but the main loop must be implemented before the experiment can be used.
