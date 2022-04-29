# cppdep
C++ dependency packager.  
Packs all your C/C++ libraries into one package and allows you to easily manage them.

## Why do I need that?

You have C++ project with a lot of dependencies and you want to ship them with your project as a single package.  

It allows new developers to not spend any time installing and searching for required libraries for your project. They can just
load package with all dependencies by using `cppdep`.

## How does it work?
If you want to pack dependencies then you need to do the following:
 1. Create an empty directory
 2. Initialise it as a package directory with `cppdep init`
 3. Add include and lib files for every library with `cppdep <env> <library> add header|library <file>`
 4. Create zip package with all dependencies with `cppdep pack` or upload to remote storage with `cppdep push`

If you want to use the already created package with dependencies:
 1. Unpack that zip package with `cppdep unpack` or load from remote storage with `cppdep pull`
 2. Set include and lib path to libraries inside of package directory

## Structure of package directory
Package directory is the directory that contains all libraries for every environment and information about them.

```
<package directory>
|- info.json            # contains all information about all libraries
|- env1                 # directory for certain environment ('linux', 'darwin', etc.)
|   |- include          # header files
|   |- lib              # static and dynamic libraries
|- env2
|   ...
```

## What about remote storage?
You can tell `cppdep` to use remote storage to load or save package with dependencies.  
Just make simple file `remote.json` in your package directory (or empty directory) and run `cppdep push` to upload
current package to a remote storage or `cppdep pull` to load latest package state.

