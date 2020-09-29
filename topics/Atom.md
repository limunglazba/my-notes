# Installation
- Install Atom packages from a predefined (exported) list[[1]](https://discuss.atom.io/t/installed-packages-list-into-single-file/12227) via cmd
- Create your package list:
```cmd
apm list --installed --bare > package-list.txt
```
- Install the package list:
```cmd
apm install --packages-file package-list.txt
```
