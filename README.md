# Stochastic Process Calibration using Bayesian Inference and Probabilistic Programs

Stochastic processes are used extensively throughout quantitative finance - for example, to simulate asset prices in risk models that aim to estimate key risk metrics such as Value-at-Risk (VaR), Expected Shortfall (ES) and Potential Future Exposure (PFE). Estimating the parameters of a stochastic processes - referred to as 'calibration' in the parlance of quantitative finance -usually involves:

- computing the distribution of price returns for a financial asset;
- deriving point-estimates for the mean and volatility of the returns; and then,
- solving a set of simultaneous equations to back-out the parameters of the process.

The purpose of this Python notebook is to demonstrate how Bayesian Inference and Probabilistic Programming (using [PYMC3](https://docs.pymc.io)), is an alternative and more powerful approach that can be viewed as a unified framework for:

- exploiting any available prior knowledge on market prices (quantitative or qualitative);
- estimating the parameters of a stochastic process; and,
- naturally incorporating parameter uncertainty into risk metrics. 

## Reproducing these Results - Managing Project Dependencies

We use [pipenv](https://docs.pipenv.org) for managing project dependencies and Python environments (i.e. virtual environments). All of the direct packages dependencies required to run the code (e.g. NumPy for arrays/tensors and Pandas for DataFrames), as well as all the packages used during development (e.g. Jupyter and IPython for interactive console and sessions and serving notebooks), are described in the `Pipfile`. Their **precise** downstream dependencies are described in `Pipfile.lock`.

### Installing Pipenv

To get started with Pipenv, first of all download it - assuming that there is a global version of Python available on your system and on the PATH, then this can be achieved by running the following command,

```bash
pip3 install pipenv
```

Pipenv is also available to install from many non-Python package managers. For example, on OS X it can be installed using the [Homebrew](https://brew.sh) package manager, with the following terminal command,

```bash
brew install pipenv
```

For more information, including advanced configuration options, see the [official pipenv documentation](https://docs.pipenv.org).

### Installing this Projects' Dependencies

Make sure that you're in the project's root directory (the same one in which the `Pipfile` resides), and then run,

```bash
pipenv install --dev
```

This will install all of the direct project dependencies as well as the development dependencies (the latter a consequence of the `--dev` flag).

### Running Python, IPython and JupyterLab from the Project's Virtual Environment

In order to continue development in a Python environment that precisely mimics the one the project was initially developed with, use Pipenv from the command line as follows,

```bash
pipenv run python3
```

The `python3` command could just as well be `ipython3` or the JupterLab, for example,

```bash
pipenv run jupyter lab
```

This will fire-up a JupyterLab *where the default Python 3 kernel includes all of the direct and development project dependencies*. This is how we advise that the notebooks within this project are used.

### Pipenv Shells

Prepending `pipenv` to every command you want to run within the context of your Pipenv-managed virtual environment, can get very tedious. This can be avoided by entering into a Pipenv-managed shell,

```bash
pipenv shell
```

which is equivalent to 'activating' the virtual environment. Any command will now be executed within the virtual environment. Use `exit` to leave the shell session.
