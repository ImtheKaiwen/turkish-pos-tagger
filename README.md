# Turkish POS Tagger

An experimental Turkish part-of-speech tagging project built with TensorFlow/Keras. The training script reads a CoNLL-U corpus, trains a bidirectional LSTM sequence model, saves the model and lookup dictionaries, and demonstrates predictions for a sample sentence.

## Files

| File | Purpose |
| --- | --- |
| [`train.py`](train.py) | Parse the corpus, prepare sequences, train the model, save artifacts, and plot training history |
| [`validation.py`](validation.py) | Load saved artifacts and tag sentences in an interactive loop |

## Required inputs

The training corpus is not included. `train.py` expects a UTF-8 CoNLL-U file named:

```text
tr_boun-ud-train.conllu
```

Place that file in the repository root before training. Confirm the corpus's source, version, and license independently; they are not recorded in this repository.

## Generated artifacts

Training writes the following files:

```text
pos_tag.h5
word2idx.pkl
tag2idx.pkl
```

`validation.py` requires all three artifacts.

## Run

Use a Python environment with compatible versions of TensorFlow/Keras, NumPy, conllu, scikit-learn, Matplotlib, and Seaborn.

Start training:

```bash
python train.py
```

After training completes, start the interactive tagger:

```bash
python validation.py
```

## Reproducibility status

Dependency versions, the corpus source/version, and benchmark results are not included. Training was not rerun during the documentation refresh. The validation script also uses a fixed sequence length of 50, while training calculates its sequence length from the corpus; this assumption may need review before comparing results.
