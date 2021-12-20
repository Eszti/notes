# Python

## Environment

- [pyenv](https://github.com/pyenv/pyenv)
  - different versions
	  - `pyenv install 3.8.3`
	  - `pyenv uninstall 3.8.3`
	  - `pyenv global 3.8.3`
  - [pyenv-virtualenv](https://github.com/pyenv/pyenv-virtualenv)
  	- `pyenv virtualenvs`
  	- `pyenv virtualenv myenv`
    - `pyenv activate myenv`
- [venv](https://docs.python.org/3/library/venv.html)
  - to manage different virtual environments (install different packages) of a single python version
    - `python -m venv ./venv`
    - `source ./venv/bin/activate`
  - only works for Python3.3+

## Dependencies

- to list dependencies
  - `pip freeze`
- requirements 
  - store in `requirements.txt`
  - install with `pip install -r requirements.txt`
- `install.py`
  - install with editable `pip install -e .`
- uninstall all
  - `pip freeze | xargs pip uninstall -y`
  - if you installed with `-e` call `pip freeze | xargs pip uninstall -y` before

## Package managers

### pip

- [pip](https://pypi.org/project/pip/)
- to delete all dependencies
  - `pip freeze | xargs pip uninstall -y`

### conda

- [conda](https://docs.conda.io/en/latest/)

## Build distribution formats

- egg
  - introduced by setuptools
- wheel
  - introduced by PEP (Python Enhancement Proposal)
  - supported by pip
  - currently standard for build and binary packaging

## Libraries

- [jinja](https://jinja.palletsprojects.com/en/2.11.x/)
  - web template language
  - can also generate markup and source code
- [flask](https://flask.palletsprojects.com/en/1.1.x/)
  - simple web framework
  - no  database abstraction layer, nor form validation...

## Useful

- [wtfpython](https://github.com/satwikkansal/wtfpython)
- [urldecode](https://dev.to/k4ml/python-urldecode-on-command-line-2ek9)
- use cache out of the box (LRU cache)

```python
import functools

@functools.lru_cache
def calculate_num_steps(n):
  pass
```