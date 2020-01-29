# new-repo-instructions

1. Create repo from template
1. `yarn`
1. `yarn remove autopublish-template`
1. `yarn add --dev name-of-your-repo`
1. Find and replace all instances of `autopublish-template` with `name-of-your-repo`
1. Find and replace all instances of `index.js` with the desired name of the output file
1. Modify rollup config however is needed. Run `yarn build` to test
1. Modify tests until `narn test:unit` and `narn test:browser` both work
1. Add GITHUB_USERNAME, GITHUB_TOKEN, NPM_TOKEN environment variables to Travis
1. Push and verify it is published correctly
1. Modify description in package.json