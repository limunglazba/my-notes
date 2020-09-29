# Installation
- Install Atom packages from a predefined list of packages via cmd[[1]](https://discuss.atom.io/t/installed-packages-list-into-single-file/12227)
    1. Create your package list:
    ```cmd
    apm list --installed --bare > package-list.txt
    ```
    2. Install the package list:
    ```cmd
    apm install --packages-file package-list.txt
    ```
