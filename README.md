# Instructions for creating a new repo

## What is this?

https://medium.com/@joeldenning/an-esm-bundle-for-any-npm-package-5f850db0e04d

## Okay how do I do it

You need to install [pnpm](https://pnpm.js.org/).

1. Create a [github issue](https://github.com/esm-bundle/new-repo-instructions/issues/new), following the template
1. Make sure you know the name of the Github repo that you will create. This should be exactly the same as the package name on npm. If the package has an npm scope (`@`), use the [syntax](https://github.com/DefinitelyTyped/DefinitelyTyped#what-about-scoped-packages) used by DefinitelyTyped (`__`) to name the package. Do not put `@` in the repo name.
1. An esm-bundle maintainer will create a new repository for your package, by using the Github template repository https://github.com/esm-bundle/autopublish-template. This is done by going there and clicking on "Use this template." **Make sure to create the new repo under the esm-bundle organization instead of your personal Github**
1. Fork the repo. Clone your fork.
1. Ensure you are using node@>=13.2.0. You can check by doing `node --version`. If you use [nvm](https://github.com/nvm-sh/nvm), you can switch to the correct version of node via `nvm use`
1. `pnpm install`
1. `pnpm uninstall autopublish-template`
1. `pnpm install --dev name-of-your-repo`
1. Find and replace all instances of `autopublish-template` with `name-of-your-repo`
1. Find and replace all instances of `index.js` with the desired name of the output file
   - It is encouraged to match the upstream package's output and naming convention for its UMD bundles
1. Modify the Readme to point to the correct "upstream repo"
1. Modify the `version` in the package.json to `0.0.0-unpublished.0` in order to trigger release-it plugin on first merge
1. Modify description in package.json
1. Modify rollup config however is needed. Run `pnpm run build` to test that the build works
1. Modify tests until `pnpm run test:unit` and `pnpm run test:browser` both work
1. If you are publishing multiple files, link to them in the readme
1. Add a [github branch protection rule](https://help.github.com/en/github/administering-a-repository/configuring-protected-branches) for the master branch. This is required by Kodiak. You should protect the master branch by requiring a pull request approval and successful CI before merges. See picture below for what that configuration looks like.
1. Push a branch to your fork. Create a pull request. Tag @joeldenning or another maintainer of esm-bundle, to ensure they get a notification to review the pull request. They will merge the PR which will cause the first version to be published. From then on, new versions will be automatically published.

## Protecting the main branch
![image](https://user-images.githubusercontent.com/5524384/112045569-9de99280-8b10-11eb-9b14-959af8189576.png)
