# Instructions for creating a new repo

## What is this?

https://medium.com/@joeldenning/an-esm-bundle-for-any-npm-package-5f850db0e04d

## Okay how do I do it

_If this is your first time working on esm-bundle, please [create a Github issue](https://github.com/esm-bundle/new-repo-instructions/issues/new) to be added to [this esm-bundle Github team](https://github.com/orgs/esm-bundle/teams/repo-authors). Once you are on the team, you will be able to create repositories into the esm-bundle organization. Until then, create repositories in your own Github account and then transfer them once you are given access._

1. Make sure you know the name of the Github repo that you will create. This should be exactly the same as the package name on npm. If the package has an npm scope (`@`), use the [syntax](https://github.com/DefinitelyTyped/DefinitelyTyped#what-about-scoped-packages) used by DefinitelyTyped (`__`) to name the package. Do not put `@` in the repo name.
1. Create a repo from https://github.com/esm-bundle/autopublish-template. You do this by going there and clicking on "Use this template." **Make sure to create the new repo under the esm-bundle organization instead of your personal Github**
1. Ensure you are using node@>=13.2.0. You can check by doing `node --version`. If you use [nvm](https://github.com/nvm-sh/nvm), you can switch to the correct version of node via `nvm use`
1. `yarn`
1. `yarn remove autopublish-template`
1. `yarn add --dev name-of-your-repo`
1. Find and replace all instances of `autopublish-template` with `name-of-your-repo`
1. Find and replace all instances of `index.js` with the desired name of the output file
   - It is encouraged to match the upstream package's output and naming convention for its UMD bundles
1. Modify the Readme to point to the correct "upstream repo"
1. Modify the `version` in the package.json to `0.0.0-unpublished.0` in order to trigger release-it plugin on first merge
1. Modify description in package.json
1. Modify rollup config however is needed. Run `yarn build` to test
1. Modify tests until `yarn test:unit` and `yarn test:browser` both work
1. If you are publishing multiple files, link to them in the readme
1. Add a [github branch protection rule](https://help.github.com/en/github/administering-a-repository/configuring-protected-branches) for the master branch. This is required by Kodiak. You should protect the master branch by requiring a pull request approval and successful CI before merges. See picture below for what that configuration looks like.
1. Add GITHUB_USERNAME, GITHUB_TOKEN, NPM_TOKEN environment variables to Travis. Make sure only available on master branch.
1. Push and verify it is published correctly

## Protecting the master branch

![image](https://user-images.githubusercontent.com/5524384/75733136-b262af00-5cb1-11ea-9583-db93e06de0c0.png)
