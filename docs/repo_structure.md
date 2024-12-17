

# Repository Structure for Python Projects
## MORE TO COME

This document outlines the recommended structure for Python projects within our organization. Following this structure will help maintain consistency, readability, and maintainability across our projects.

## General Structure
The top-level directory of your project should look like this:
```
repo_name/
├── src/
│   ├── module_name/
│   │   ├── __init__.py
│   │   ├── submodule1.py
│   │   ├── submodule2.py
│   │   └── ...
│   └── ...
├── docs/
│   ├── index.md
│   ├── api/
│   │   ├── module_name.md
│   └── user_guides/
│       ├── guide1.md
│       └── ...
├── tests/
│   ├── test_module1.py
│   ├── test_module2.py
│   └── ...
├── containers/
│   ├── podman/
│   │   ├── Dockerfile
│   │   └── podman-compose.yml
│   ├── singularity/
│   │   ├── Singularity.def
│   │   └── run_script.sh
├── config/
│   ├── settings.ini
|   ├── ....    
├── .gitignore
├── README.md
├── requirements.txt
├── setup.sh
└── setup.py
```
## Detailed Structure

### `src/`
This directory contains all the source code for your Python project.

- **Module Organization**: Each module should be placed in its own subdirectory within `src/`. Each subdirectory should contain an `__init__.py` file to indicate that it is a Python package.
- **Submodules**: Modules can have submodules, organized in the same way. Each submodule should have a clear and specific purpose. Ideally organization of submodules should be categorized by function and as indpendent from other submodules as possible.
- **Naming Conventions**: Use lowercase names with underscores for directories and file names, following PEP 8 guidelines.

Example:
```
src/
├── data_processing/
│   ├── __init__.py
│   ├── load_data.py
│   ├── preprocess_data.py
│   └── ...
├── models/
│   ├── __init__.py
│   ├── train_model.py
│   ├── evaluate_model.py
│   └── ...
└── utils/
    ├── __init__.py
    ├── helper_functions.py
    └── ...
```
### `docs/`
This directory contains all documentation related to the project.

- **Index**: The `index.md` file serves as the entry point for your documentation.
- **API Documentation**: The `api/` directory should contain detailed documentation for each module.
- **User Guides**: The `user_guides/` directory should contain tutorials and how-to guides.

Example:
```
docs/
├── index.md
├── api/
│   ├── data_processing.md
│   ├── models.md
│   └── utils.md
└── user_guides/
    ├── getting_started.md
    └── advanced_usage.md
```
### `tests/`
This directory contains all the tests for your project.

- **Test Organization**: Tests should be organized in a way that mirrors the structure of the `src/` directory.
- **Naming Conventions**: Test files should start with `test_` followed by the name of the module or submodule they are testing.

Example:
tests/
├── test_data_processing.py
├── test_models.py
└── test_utils.py

### `containers/`
This directory contains configuration files for containerization using Podman or Singularity.

#### `podman/`
Contains files for creating and managing Podman containers.

- **Dockerfile**: Defines the environment and dependencies for the container.
- **podman-compose.yml**: Defines the services and their configurations.

#### `singularity/`
Contains files for creating and managing Singularity containers.

- **Singularity.def**: Defines the environment and dependencies for the Singularity container.
- **run_script.sh**: Script to run the Singularity container.

Example:
```
containers/
├── podman/
│   ├── Dockerfile
│   └── podman-compose.yml
└── singularity/
    ├── Singularity.def
    └── run_script.sh
```
### `config/`
This directory contains configuration files for the project which can include. 

- **settings.ini**: Configuration settings for the project.

Example:
```
config/
├── settings.ini
```
### Root-Level Files

- **`.gitignore`**: Specifies files and directories that should be ignored by Git.
- **`README.md`**: Provides an overview of the project, including how to set up and use it.
- **`requirements.txt`**: Lists the dependencies required to run the project.
- **`setup.py`**: Sets up and runs python package.
- **`setup.sh`**: command line run to set up everything, ideally this should call setup.py and also be called by the container instructions.

