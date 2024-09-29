# Cookiecutter template for a minimal OCaml executable

## Usage

**NB**: The [cookiecutter documentation](https://cookiecutter.readthedocs.io/en/stable/usage.html) will always be the most up-to-date regarding cookiecutter usage. The following instruction are just a quickstart helper.

```console
$ cookiecutter gh:https://github.com/NyuB/ocaml-exec-minimal
[1/7] name (main): my-awesome-tool
[2/7] main_name (my_awesome_tool):
...
$ ls my-awesome-tool
```

## Template variables

- **name**: Your project's name, and the generated folder's name.
- **main_name**: The executable name. Used in dune files as package name and as the base of the single ocaml source code. Should be valid for a `(name <main_name>)` stanza in a `dune` file.
- **description**: A description of the executable
- **libraries**: Space separated ocaml package to include as dependency. Should be valid for a `(libraries <libraries>)` stanza in a `dune` file.
- **author**: Your name
- **repository**: Your git repo formatted as `user/repo`
- **repository_url**: Full url to your git repo

