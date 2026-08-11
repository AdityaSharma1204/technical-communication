# virtualenv

`virtualenv` is a tool used to create isolated Python environments. Each environment has its own installation directory and package set, which prevents dependency conflicts between different projects running on the same machine. This is particularly important when different projects require different versions of the same library.

## Basic Usage

```bash
pip install virtualenv
virtualenv myenv
source myenv/bin/activate   # On Linux/macOS
myenv\Scripts\activate      # On Windows
deactivate
```

Python 3 also includes a built-in equivalent module called `venv`, which can be used without installing anything extra:

```bash
python3 -m venv myenv
```

Using isolated environments is considered a best practice for any real-world Python project, similar to how a Java project keeps its dependencies scoped through Maven or Gradle.
