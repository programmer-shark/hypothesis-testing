# hypothesis-testing
Analyze applicant data and run an A/B test to measure if reminder emails improve admissions exam completion rates for Applied Data Science Lab.

SETUP 

Poetry Setup: (Package manager)
curl -sSL https://install.python-poetry.org | python3 -
export PATH="$HOME/.local/bin:$PATH"
source ~/.zshrc
poetry --version

pyenv install 3.11.8
pyenv local 3.11.8
poetry init
poetry env use $(pyenv which python)
poetry install

poetry add notebook ipykernel
poetry run python -m ipykernel install --user --name=$(basename $PWD) --display-name "Python (earthquake-prediction-model)"
poetry run jupyter lab

touch .gitignore

poetry add jupyterlab-widgets for widgets to work