## General flow

There will be always 4 main branches:
1. `master`
2. `staging`
3. `preprod`
4. `develop`

`master` is the branch on ==`192.168.2.110`==
`staging` has no server
`preprod` is the branch on ==`192.168.8.160`==
`develop` is the branch on ==`192.168.8.150`==

#### After release

After each release when the latest code is on `master`, it should automatically make 3 copies of itself and name them `staging`, `preprod` and `develop`. The old `staging`, `preprod` and `develop` should be lost (rewritten).

## Feature development

#### Creating new branch

When starting to work on a new task you should make a copy of `master` and work on that branch:

```bash
git checkout master
git pull origin master
git checkout -b 'feature/FO-1111-your-task-name'
```

Every branch should begin with `feature/` or `bug/` followed by the Jira task id and the human readible name delimited with hyphen (-) ==not== underscore (\_)

#### Commiting your work

Try to commit your work several times a day.

```bash
git add -A
git commit -m 'FO-1111: Fix the name of the model'
```

The commit messages should begin with the task id followed by colon (:) and than space-delimeted sentence describing your work briefly. The first word should start with capital letter and should be a verb in imperative/infinitive: e.g. `Fix`, `Add`, `Remove`, `Implement`, `Refactor`, etc. (and ==not== fixed, added, or fixes and adds). 

#### Testing your work

When you think your work is ready for testing environment, you should push it and merge it on the `develop` branch with merge request.

```bash
git push origin feature/FO-1111-your-task-name
```

It will generate a link to the merge request, something like this:

```bash
remote: Resolving deltas: 100% (131/131), completed with 2 local objects.
remote: 
remote: To create a merge request for feature/FO-1111-your-task-name, visit:
remote:   https://gitlab.innosoft.ge/developers/swisscapital/-/merge_requests/new?merge_request%5Bsource_branch%5D=feature%2FFO-1111-your-task-name
remote: 
To gitlab.innosoft.ge:developers/swisscapital.git
 * [new branch]          feature/test/FO-1111-your-task-name -> feature/test/FO-1111-your-task-name
```

Visit this link 