# microgpt-experiments

This project uses the existing Pipenv environment in the parent directory; no
local virtual environment or additional dependencies are needed.

Run the program with:

```bash
pipenv run python microgpt.py
```

After the 20 generated samples, a table shows the average training loss for each
100-step block (including any shorter final block). The loss history is also saved
to `learning_curve.csv`, and its plot is saved as `learning_curve.svg` in the
project directory. These generated files are overwritten on each run and ignored
by Git.

## Choosing a dataset

Set `input_file` near the top of `microgpt.py` to a text file containing one
training example per line. Paths are relative to the directory you run from.
The default `input.txt` contains people's names and is downloaded if missing.
Custom files must already exist and contain at least one non-empty line.

To try a smaller corpus, set:

```python
input_file = 'flowers.txt'
```

The included `flowers.txt` contains 189 lowercase flower names, all short enough
for the model's 16-token context. With 1,000 training steps, these examples repeat
about 5 times, whereas the default corpus supplies a different name at each step.
A lower training loss may therefore reflect memorization; changing the vocabulary
and subject matter also means this is not a controlled test of corpus size alone.

Setup:

```bash
git init
```

```bash
curl -fL \
  https://gist.githubusercontent.com/karpathy/8627fe009c40f57531cb18360106ce95/raw/microgpt.py \
  -o microgpt.py
```
