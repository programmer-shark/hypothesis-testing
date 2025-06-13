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
poetry run python -m ipykernel install --user --name=$(basename $PWD) --display-name "Python (hypothesis-testing-kernel)"
poetry run jupyter lab

touch .gitignore

poetry add jupyterlab-widgets for widgets to work

MONGODB SETUP & IMPORT:
=======================
brew tap mongodb/brew
brew install mongodb-community@6.0

which mongod
which mongoimport
mongod --version
mongoimport --version

brew services start mongodb-community@6.0


mongoimport --uri "mongodb://localhost:27017" \
  --db abtest-db \
  --collection ds-applicants \
  --file ds_applicants.json \
  --jsonArray


After Experiment
mongoimport --uri "mongodb://localhost:27017" \
  --db abtest-db \
  --collection ds-applicants-after-exp \
  --file ds_applicants_after_experiment.json \
  --jsonArray



