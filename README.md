# LAME

## Create a new org-scoped project

1. Initialize the project directory:
    1. `mkdir lame`
1. Create the `lame` project on github
1. Initialize the git project locally:
    1. `git init`
1. Associate the local project with github:
    1. `git remote add origin https://github.com/brainthinks/lame-test.git`
1. Add some stuff to the project
    1. `touch README.md`
    1. `touch .gitignore`
    1. `touch .npmrc`
1. Add the `.npmrc` file with the following:
    1. `scope=bandress-dumbasses`
    1. `access=public`
1. Initialize the node project:
    1. `yarn init`
    1. Provide the name of the project as `@bandress-dumbasses/lame`
1. Commit and push all the files:
    1. `git add .`
    1. `git commit -m "message"`
    1. `git push -u origin master`
1. Version the project:
    1. `yarn version --new-version 0.0.1`
    1. `git push --tags`
1. Publish the project
    1. `npm publish`

Observe that the project was published to the org's namespace.


## Modify an existing project to have an org scope

1. Add the `.npmrc` file that contains the `scope` and `access` configurations
1. Add the `repository` property to the `package.json` file, where the value is the git url
    1. e.g. `"repository": "https://github.com/brainthinks/lame-test.git",`
1. Find all instances in the project where the `name` property from the `package.json` is used
    1. You may need to change them from `name` to `name.split('/').pop()`
1. Commit and push all changes
1. Version the project:
    1. `yarn version --new-version 0.0.1`
1. Publish the project
    1. `npm publish`

## References

* [https://docs.npmjs.com/creating-and-publishing-an-org-scoped-package](https://docs.npmjs.com/creating-and-publishing-an-org-scoped-package)
* [https://docs.npmjs.com/configuring-your-npm-client-with-your-org-settings](https://docs.npmjs.com/configuring-your-npm-client-with-your-org-settings)
