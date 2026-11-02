*This project has been created as part of the 42 curriculum by scamlett.*

# Python Module 08: Welcome to the Matrix

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![Poetry](https://img.shields.io/badge/Poetry-managed-60A5FA?logo=poetry&logoColor=white)
![42](https://img.shields.io/badge/42-Málaga-000000)

## Description

A module about the environment a Python program runs in: virtual
environments, installing third-party packages, and keeping configuration
and secrets out of the code. The theme is The Matrix.

| Exercise | File | Topic |
|----------|------|-------|
| ex0 | `ex0/construct.py` | Detects whether it is running inside a virtual environment and prints where packages get installed |
| ex1 | `ex1/loading.py` | Simulates 100 rolls of two dice with `numpy`, counts them with `pandas` and plots the result with `matplotlib`. Installable with pip (`requirements.txt`) or Poetry (`pyproject.toml`) |
| ex2 | `ex2/oracle.py` | Reads settings from a `.env` file with `python-dotenv` and environment variables, with safe defaults |

## Instructions

```bash
# ex0: compare outside and inside a venv
python3 ex0/construct.py
python3 -m venv .venv && source .venv/bin/activate
python3 ex0/construct.py

# ex1 with pip
pip install -r ex1/requirements.txt
python3 ex1/loading.py

# ex1 with Poetry
cd ex1 && poetry install && poetry run python loading.py && cd ..

# ex2
pip install python-dotenv
cp ex2/.env.example ex2/.env
python3 ex2/oracle.py
```

## What I learned

- A virtual environment is an isolated copy of Python with its own
  packages, and `sys.prefix != sys.base_prefix` tells you if you are in one
- Why you never install project packages into the system Python
- Two ways to declare dependencies: a flat `requirements.txt` for pip, or a
  `pyproject.toml` for Poetry, which also locks exact versions
- Checking for a dependency before importing it, so the program can explain
  what is missing instead of crashing
- Configuration belongs in environment variables or a `.env` file that is
  listed in `.gitignore`, never hardcoded. A committed `.env.example` shows
  which settings exist without leaking real values
