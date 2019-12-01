[![Build Status](https://travis-ci.org/kmedian/lagmat.svg?branch=master)](https://travis-ci.org/kmedian/lagmat)
[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/kmedian/lagmat/master?urlpath=lab)
[![Gitpod - Code Now](https://img.shields.io/badge/Gitpod-code%20now-blue.svg?longCache=true)](https://gitpod.io#https://github.com/kmedian/lagmat)

# lagmat
Lagmatrix. Create array with time-lagged copies of the features


## Table of Contents
* [Installation](#installation)
* [Usage](#usage)
* [Commands](#commands)
* [Support](#support)
* [Contributing](#contributing)


## Installation
The `lagmat` [git repo](http://github.com/kmedian/lagmat) is available as [PyPi package](https://pypi.org/project/lagmat)

```
pip install lagmat
```


## Usage

```
import numpy as np
A = (np.random.rand(7,3) * 10 + 10).round(1)

from lagmat import lagmat
B = lagmat(A, lags=[0,1,2])  # 0: copy itself, 1: one time-lag, 2: two time-lags
```


Check the [examples](http://github.com/kmedian/lagmat/examples) folder for notebooks.


## Commands
Install a virtual environment

```
python3 -m venv .venv  # see note below
source .venv/bin/activate
pip3 install --upgrade pip
pip3 install -r requirements.txt
pip3 install jupyterlab  # and other packages required for demo
```

(If your git repo is stored in a folder with whitespaces, then don't use the subfolder `.venv`. Use an absolute path without whitespaces.)

Python commands

* Jupyter for the examples: `jupyter lab`
* Check syntax: `flake8 --ignore=F401 --exclude=$(grep -v '^#' .gitignore | xargs | sed -e 's/ /,/g')`
* Run Unit Tests: `python -W ignore -m unittest discover`
* Upload to PyPi with twine: `python setup.py sdist && twine upload -r pypi dist/*`

Clean up 

```
find . -type f -name "*.pyc" | xargs rm
find . -type d -name "__pycache__" | xargs rm -r
rm -r .pytest_cache
rm -r .venv
```

## Debugging
* Notebooks to profile python code are in the [profile](http://github.com/kmedian/lagmat/profile) folder


## Support
Please [open an issue](https://github.com/kmedian/lagmat/issues/new) for support.


## Contributing
Please contribute using [Github Flow](https://guides.github.com/introduction/flow/). Create a branch, add commits, and [open a pull request](https://github.com/kmedian/lagmat/compare/).
