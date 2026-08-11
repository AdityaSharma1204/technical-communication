# pip Package Manager

`pip` is the standard package manager for Python and is used to install, upgrade, and remove third-party libraries from the Python Package Index (PyPI).

## Common Commands

* `pip install package_name` - installs a package.
* `pip uninstall package_name` - removes a package.
* `pip list` - shows all installed packages.
* `pip show package_name` - displays details about a specific package.
* `pip freeze > requirements.txt` - exports installed packages and their versions to a file.
* `pip install -r requirements.txt` - installs all packages listed in a requirements file.

The `requirements.txt` workflow is the Python equivalent of a `pom.xml` in Maven, allowing a project's dependencies to be reproduced consistently across different machines.
