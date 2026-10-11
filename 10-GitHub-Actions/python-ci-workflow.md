# ⚙️ GitHub Actions: Python CI Workflow

Continuous Integration (CI) ensures that every commit or pull request to your repository is automatically tested. This is a basic GitHub Actions workflow for a Python project (like a Flask backend or AI model script).

## 1. Setup Instructions
Create a folder named `.github` in the root of your repository. Inside it, create another folder named `workflows`, and add a file named `python-app.yml`.

## 2. Workflow Code (`python-app.yml`)
Copy and paste this YAML code into the file:

```yaml
name: Python Application CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

permissions:
  contents: read

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v4
    
    - name: Set up Python 3.10
      uses: actions/setup-python@v3
      with:
        python-version: "3.10"
        
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install flake8 pytest
        if [ -f requirements.txt ]; then pip install -r requirements.txt; fi
        
    - name: Lint with flake8
      run: |
        # stop the build if there are Python syntax errors or undefined names
        flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
        
    - name: Test with pytest
      run: |
        pytest
```

This action will automatically set up Python, install your dependencies, check for syntax errors, and run your tests every time someone contributes to the project.
