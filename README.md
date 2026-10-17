# Machine Learning

This repository contains small experimental machine-learning projects. Each project is kept in its own folder.

## Folder structure

```text
machine_learning/
├── README.md
├── reinforcement_learning_test1/
│   └── rl1.py
├── supervised_learning_test1/
│   └── sl1.py
└── supervised_learning_test2/
    └── sl2.py
```

## Folder descriptions

| Folder | Contents and purpose |
| --- | --- |
| `reinforcement_learning_test1/` | A basic learning experiment that adjusts a linear model's weight and bias to fit example input/output values, then prints predictions for new inputs. |
| `supervised_learning_test1/` | An early character-based text-generation experiment using a group of small neural networks. It includes character encoding, network updates, and scoring/training logic. |
| `supervised_learning_test2/` | A more developed text-generation experiment using a group of neural networks, a character vocabulary, prompt-based training, and scoring criteria such as character frequency, spacing, repetition, and user feedback. |

## Main scripts

- `reinforcement_learning_test1/rl1.py` — trains a single linear predictor on a small set of numeric examples.
- `supervised_learning_test1/sl1.py` — implements the first supervised text-generation prototype.
- `supervised_learning_test2/sl2.py` — implements the second supervised text-generation prototype, with multiple training phases and text-quality scoring.

The Python scripts use NumPy. Run a script from the repository root with `python <path-to-script>`.
