# WanderWise 🌍

Your AI-powered guide to the perfect destination—anywhere, anytime.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Tech Stack](tech-stack)
- [Getting Started](getting-started)
- [Development Approach](development-approach)
- [Contributing](contributing)
- [License](licence)

## Introduction

WanderWise leverages predictive modeling and AI to recommend the best travel destinations tailored to your preferences. From real-time weather updates to event recommendations, WanderWise ensures your next trip is unforgettable.

## Features
- Personalized Recommendations: Tailored suggestions based on user preferences.
- Dynamic Itineraries: Generate travel plans including hotels, activities, and local insights.
- Predictive Analytics: Stay ahead of trends with cutting-edge forecasting.
- Real-time Updates: Get data-driven insights on weather, events, and travel trends.

## File structure
This project is structured as follows:
```aiignore
wanderwise/
├── api/                    # Backend API
│   ├── app.py              # Flask app entry point
│   ├── auth                # Auth & Auth logic
│   ├── database/           # Database models
│   ├── models/             # API routes
│   ├── routes/             # Helper functions
│   ├── services/           # Unit tests for the API
│   ├── tests/              # Business logic and services
│   └── utils/              # database models and stuff
│
├── mobile/                 # Mobile app source code
│   ├── android/            # Android-specific code
│   ├── ios/                # iOS-specific code
│   └── shared/             # Shared logic for both platforms
│
├── docs/                   # Documentation
│   ├── README.md           # Project documentation
│   ├── API.md              # API details
│   └── CONTRIBUTORS.md     # List of contributors
│
├── data/                   # Sample or training data
├── notebooks/              # Jupyter notebooks for exploratory analysis
├── requirements.txt        # Python dependencies
├── .gitignore              # Git ignore rules
├── LICENSE                 # License file
└── README.md               # Project overview and setup instructions
```

## Tech Stack
- Backend: Python, Flask, FastAPI, TensorFlow, PyTorch
- Frontend: React Native (for mobile apps)
- Data Collection: Beautiful Soup, Scrapy, APIs (Weather, Events)
- Database: PostgreSQL
- Testing: Pytest, Postman
- Deployment: Docker containers

## Getting Started

### Prerequisites
- Python 3.12+
- Node.js (for mobile app development)
- Docker (for containerized development)

## Installation
1. Clone the repository:
```
git clone https://github.com/yourusername/wanderwise.git
cd wanderwise

```
2. Set up a virtual environment for the backend:
```aiignore
python app.py
```
3. Run the backend:
```aiignore
python app.py
```

4. Navigate to the mobile/ folder for mobile app setup.


## Development approach
- Agile Workflow: Using GitHub Projects for sprint planning and issue tracking.
- Testing:
- Backend: Pytest for unit and integration tests.
- API: Postman for endpoint testing.
- Frontend: React Native testing tools.
- CI/CD: Automated pipelines for building, testing, and deployment.

### Tools

#### Poetry
Poetry is used for managing dependencies, packaging, and publishing Python projects. This project uses Poetry to manage dependencies and virtual environments.

Setting Up Poetry
1. Install Poetry
```aiignore
curl -sSL https://install.python-poetry.org | python3 -
```
2. Install project dependencies
```aiignore
poetry install
```
This will install all the dependencies listed in the pyproject.toml file.

Dependencies

Here are some of the key dependencies in the pyproject.toml file:
```aiignore
[tool.poetry]
name = "wanderwise"
version = "0.1.0"
description = ""
authors = ["MightContainNuts <mightcontainnuts@icloud.com>"]
readme = "README.md"
license = "MIT"
package-mode = false

[tool.poetry.dependencies]
python = "^3.13"
pre-commit = "^4.0.1"
pytest-cov = "^6.0.0"
pytest-sugar = "^1.0.0"
flake8 = "^7.1.1"

[tool.poetry.group.dev.dependencies]
pytest = "^8.3.4"
```
Poetry also manages development dependencies like pytest, flake8, and pre-commit hooks.

#### Pre-commit
Pre-commit is used to run checks automatically before commits are made, ensuring that your code adheres to standards like proper formatting and no trailing whitespace.

Setting Up Pre-commit (it should be setup automatically with poetry and this step should be redundant)
1. Install pre-commit:
```aiignore
pip install pre-commit
```
2. Install the hooks defined in the .pre-commit-config.yaml file:
```aiignore
pre-commit install
```
This will install the hooks and configure Git to use them. The hooks currently in the project include:
- check-yaml: Checks YAML files for syntax errors.
- end-of-file-fixer: Ensures files end with a newline.
- trailing-whitespace: Removes any trailing whitespace.
- black: Automatically formats Python code using the Black code formatter.
- flake8: Runs flake8 for Python code style checking.
- pytest: Runs pytest to execute tests before commits.

Configuration

The configuration file .pre-commit-config.yaml includes the following repositories and hooks:

```aiignore
repos:
  - repo: git@github.com:pre-commit/pre-commit-hooks
    rev: v5.0.0
    hooks:
      - id: check-yaml
      - id: end-of-file-fixer
      - id: trailing-whitespace
  - repo: https://github.com/psf/black
    rev: 22.10.0
    hooks:
      - id: black
        additional_dependencies: [ black ]
        args: [ '--config=pyproject.toml' ]
  - repo: local
    hooks:
      - id: flake8
        name: flake8
        entry: flake8 --exclude=venv/*
        language: python
        files: \.py$
        args: [ '--config=pyproject.toml' ]
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.4.0
    hooks:
      - id: end-of-file-fixer
      - id: trailing-whitespace
      - id: check-yaml
      - id: detect-private-key
  - repo: local
    hooks:
      - id: pytest
        name: pytest
        entry: pytest
        language: system
        types: [ python ]
        pass_filenames: false
        always_run: true
```

## Contributing
We welcome contributions from everyone! To get started:
1. Fork the repository.
2. Create a feature branch:
```aiignore
git commit -m "Add your message here"
```
3. Commit your changes
```aiignore
git commit -m "Add your message here"
```
4. Push to your branch
```aiignore
git push origin feature/your-feature-name
```
5. Submit a pull request

## Licence
This project is licensed under the [MIT](https://github.com/MightContainNuts/wanderwise?tab=MIT-1-ov-file#readme) License. See the LICENSE file for details.

## Contact

For any questions or suggestions, feel free to reach out:
- Email: mightcontainnuts@icloud.com
- Hub: [MightContainNuts](https://github.com/MightContainNutss)


Happy traveling with WanderWise! ✈️
