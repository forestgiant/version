# version
Tool for version repositories. Forked from https://github.com/skelterjohn/vendor

Currently supports git and mercurial.

```
Usage: version [-d DIR] -s [-a PATH=REPO]* CONFIG_FILE_NAME  # save
       version [-d DIR] -r CONFIG_FILE_NAME  # restore
```

Ex. to version all repositories in project `version -s version.json`

Ex. to restore all repositories in project `version -r version.json`

Default for `DIR` is the current working directory.

`version -s` searches through `DIR` looking for repositories, making a record of all that it finds, and writes it to `CONFIG`.

Zero or more additional repositories that exist outside of subdirectories of `DIR` may be vendored using the `-a PATH=REPO` flag. `PATH` is the location within `DIR` that it will be put on a restore, and REPO is the absolute path of the repository root.

`version -r` looks at `CONFIG`, and clones all the recorded repositories into `DIR`.

`version` prints the local directories of the repositories it processes. This printing makes it easy to update a .gitignore or .hgignore file.
```
$ version -s >> .gitignore
```
