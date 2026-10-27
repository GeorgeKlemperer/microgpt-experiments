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

Setup:

```bash
git init
```

```bash
curl -fL \
  https://gist.githubusercontent.com/karpathy/8627fe009c40f57531cb18360106ce95/raw/microgpt.py \
  -o microgpt.py
```
