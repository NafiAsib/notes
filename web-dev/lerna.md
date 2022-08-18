# Lerna

Create monoreopo&#x20;

npx lerna init



Create package in monorepo

lerna crate first-package-name



to user yarn workspace

in package.json

"workspaces": \["packages/\*"]

in lerna.json

"npmClient": "yarn",

"useWorkspaces": true &#x20;



install dependencies in packages

lerna add --dev jest

lerna add --dev jest --scope package-name



execute command in all packages

lerna exec --npx jest

lerna run test - to run script from package.json



lerna bootstrap all packages in the repository&#x20;

