# cppdep
C++ dependency manager.  
Packs all your C/C++ libraries which your project depend upon into one package and allows you to easily manage them.

## Why do I need that?
Let's say you have a big C++ project with a lot of dependencies. But you don't want to force every developer who is working
with this project to install those dependencies from zero from different package managers or to spend time searching for the required
version or fixing your project to use more modern version of some library.

Instead of that you can package all your libraries required for the project and then distribute that package with your project. And `cppdep` is the tool to do that.

## How does it work?
If you want to pack dependencies then you need to do the following:
 1. Create an empty directory
 2. Initialise it as a package directory with `cppdep init`
 3. Add include and lib files for every library with `cppdep <env> <library> add header|library <file>`
 4. Turn the package directory into a new separate zip package with `cppdep pack`

If you want to use the already created package with dependencies:
 1. Unpack that package with `cppdep unpack`
 2. Set include and lib path to packaged libraries

## Structure of package directory
```
<package directory>
|- info.json            # contains all information about all libraries
|- env1                 # directory for certain environment ('linux', 'darwin', etc.)
|   |- include          # header files
|   |- lib              # static and dynamic libraries
|- env2
|   ...
```

