# git-submodule-expt
An experiment for replacing a git submodule with a fork of that submodule.

```bash
$ git submodule add https://github.com/pydicom/pynetdicom3
$ cat .gitmodules
[submodule "pynetdicom3"]
  path = pynetdicom3
  url = https://github.com/pydicom/pynetdicom3
$ git add .
$ git commit -m "Initial commit ..."
$ git push -u origin master
```

Updated `pynetdicom3/README.rst` with a minor addition and `.gitmodules` with a new url.
```bash
$ cat .gitmodules
[submodule "pynetdicom3"]
  path = pynetdicom3
  url = https://github.com/gnedivad/pynetdicom3
$ git submodule sync
Synchronizing submodule url for 'pynetdicom3'
$ cd pynetdicom3
$ git add .
$ git commit -m "Updated README.rst"
$ git push origin master
$ cd ..
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   .gitmodules
  modified:   README.md
  modified:   pynetdicom3 (new commits)

no changes added to commit (use "git add" and/or "git commit -a")
```