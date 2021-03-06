# Open Terms Archive - Stats

Generate statistics on [Open Terms Archive - versions](https://github.com/ambanum/OpenTermsArchive-versions).

## Get Started :rocket:
### Get the data and code on your local machine
```sh
# Clone the latest version of the OpenTermsArchive-versions repository
git clone git@github.com:ambanum/OpenTermsArchive-versions.git
# Clone the latest version of this repository
git clone git@github.com:ambanum/OpenTermsArchive-stats.git
```
The default assumption is that both repos are side-by-side in the same folder on your local machine — though you can always point to a different path.

### Setup
- Make sure that you have [python 3.9](https://www.python.org/downloads/release/python-390/) installed on your machine. We recommend that you use a [virtual environment](https://docs.python.org/3/tutorial/venv.html) before installing this tool.
- Install python dependencies into your virtual environment with `pip install -r requirements.txt`
- Add your virtual environment as a Jupyter kernel `python -m ipykernel install --name=${your_kernel}`

### Run

You should set your `PYTHONPATH` to the root of the repo so that everything runs smoothly.

```sh
cd OpenTermsArchive-stats # if not already there
export PYTHONPATH=.
```

To get help:
```
python bin/generate_stats.py --help
```

To generate a json report:
```
python bin/generate_stats.py --path ../OpenTermsArchive-versions --outdir reports
```

To generate a HTML page

```sh
jupyter nbconvert --ExecutePreprocessor.kernel_name=${your_kernel} --execute --to html --no-input notebooks/report_page.ipynb
```

The output HTML file will be `notebooks/report_page.html`

### Testing

We use `pytest` for testing which allows for test autodiscovery. Simply run:

```
python -m pytest
```

to run the test suite.