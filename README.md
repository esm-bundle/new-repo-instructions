# Instructions for creating a new repo

## What is this?

https://medium.com/@joeldenning/an-esm-bundle-for-any-npm-package-5f850db0e04d

## Okay how do I do it

*If this is your first time working on esm-bundle, please [create a Github issue](https://github.com/esm-bundle/new-repo-instructions/issues/new) to be added to [this esm-bundle Github team](https://github.com/orgs/esm-bundle/teams/repo-authors). Once you are on the team, you will be able to create repositories into the esm-bundle organization. Until then, create repositories in your own Github account and then transfer them once you are given access.*

1. Create repo from https://github.com/esm-bundle/autopublish-template. You do this by going there and clicking on "Use this template"
1. `yarn`
1. `yarn remove autopublish-template`
1. `yarn add --dev name-of-your-repo`
1. Find and replace all instances of `autopublish-template` with `name-of-your-repo`
1. Find and replace all instances of `index.js` with the desired name of the output file
1. Modify the Readme to point to the correct "upstream repo"
1. Modify rollup config however is needed. Run `yarn build` to test
1. Modify tests until `yarn test:unit` and `yarn test:browser` both work
1. If you are publishing multiple files, link to them in the readme
1. Add GITHUB_USERNAME, GITHUB_TOKEN, NPM_TOKEN environment variables to Travis. Make sure only available on master branch.
1. Push and verify it is published correctly
1. Modify description in package.json
