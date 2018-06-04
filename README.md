# git-submodule-expt
An experiment for replacing a git submodule with a fork of that submodule.

```bash
$ git submodule add https://github.com/pydicom/pynetdicom3
$ cat .gitmodules
[submodule "pynetdicom3"]
  path = pynetdicom3
  url = https://github.com/pydicom/pynetdicom3
```