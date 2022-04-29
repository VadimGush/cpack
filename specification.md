# Specification

## dependencies.json

`dependencies.json` contains JSON object with fields: "repository", "environment", and "libraries".

Fiels "repository" contains host to the remote repository which is used to load libraries.  

Field "environment" is the name of the current environment.  

Field "libraries" contains the list of all libraries as JSON objects. 
Every JSON object inside of the list should have the following fields:
 * `name` - name of the library
 * `version` - version of the library in any format

For example:
```json
{
  "repository": "<host of the repository>",
  "environment": "<name of the current environment>",
  "libraries": [
    {
      "name": "<library name>",
      "version": "<library version>",
    },
  ]
}
```
