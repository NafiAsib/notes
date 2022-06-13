---
description: Git hooks for Node.js
---

# husky

git provides a way to execute scripts before or after an event such as commit, push. These scripts are called git hooks. git hooks run locally on developers machine.

Every git repository by default has script for each hook you can bind to. These can be found at `.git/hooks` directory. We can update these scripts as per our need and git will execute them automatically.

Now, if we want to maintain some conventions or rules for a team through git hooks, we'll need to share it between the team.&#x20;

For example, I want to make sure none of my team mates can commit without proper linting. Suppose I test my linting with `yarn lint`

So, I'll create a pre-commit hook which'll execute exactly before a commit and execute what it's told to. I'll add `yarn lint` to my pre-commit hook.

Now for the sharing part, [husky](https://typicode.github.io/husky/#/) comes in the play. We can add the hooks through husky and add it to the version control system. Voila! We're done

**Installation**

```bash
yarn add --dev husky
npm set-script prepare "husky install"  # adds prepare script on package.json
yarn prepare                            # prepares husky
```

**Add a pre-commit hook**

```bash
yarn husky add .husky/pre-commit "yarn lint"
```

Now, `yarn lint` will run every time on git commit. If it passes linting, then commit will be made otherwise not.

A list of all available git hooks & how it works with some projects and guides can be found [here](https://githooks.com/).



[Automatic Next.js Code Linting with ESLint & Husky Git Hooks](https://www.youtube.com/watch?v=2C8WoV--lxs)

**Recourses**&#x20;

* [husky doc](https://typicode.github.io/husky/#/)
* [githooks.com](https://githooks.com/)
* [githooks official documentation](https://git-scm.com/docs/githooks)
