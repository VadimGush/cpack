# cpack
C++ package manager. 
Manages dependencies for your C++ project by storing them in one place.

## Why do I need that?

You have C++ project with a lot of dependencies and you want to have them in one place and distribute them with your project.  
That's way new developers will not spend any time for installing dependencies or searching for required version of specific library.

## How does it work?
If you want to package dependencies for your project:
 1. Create an empty directory in the project directory
 2. Initialise it as a package storage with `cpack init`
 3. Add libraries to the package storage with `cpack <env> <library> add header|library <file>`
 4. Upload libraries to a remote repository by running `cpack push`

If you have a project with the package storage:
 1. Load all libraries required for the project with `cpack pull`
 2. Set include and lib path to libraries inside of the package storage

## Structure of package storage
Package storage is the directory that contains all libraries for every environment and information about them.

```
<package directory>
|- libraries.json       # contains all information about all libraries
|- env1                 # directory for certain environment ('linux', 'darwin', etc.)
|   |- include          # header files
|   |- lib              # static and dynamic libraries
|- env2
|   ...
```

## How to store libraries remotely
Find any server and launch `cpack-server` on it. It will act as a repository for all libraries that you need for the project.

Then just add host of that server to `libraries.json` and run `cpack pull`.

