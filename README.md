[![Go Report Card](https://goreportcard.com/badge/github.com/vpayno/CHANGEME-REPONAME)](https://goreportcard.com/report/github.com/vpayno/CHANGEME-REPONAME)
[![Go Workflow](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/go.yml/badge.svg)](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/go.yml)
[![Bash Workflow](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/bash.yml/badge.svg)](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/bash.yml)
[![Git Workflow](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/git.yml/badge.svg)](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/git.yml)
[![Link Check Workflow](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/links.yml/badge.svg)](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/links.yml)
[![Woke Workflow](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/woke.yml/badge.svg)](https://github.com/vpayno/CHANGEME-REPONAME/actions/workflows/woke.yml)

![Coverage](./reports/.octocov-coverage.svg)
![Code2Test Ratio](./reports/.octocov-ratio.svg)

# CHANGEME_PROJECT_LABEL

This isn't a "real" project in the sense that it accepts PRs, etc. It's a project template (used to create new repos).

How to use this repo:

- Use the [GitHub Cli](https://github.com/cli/cli#installation) to create a new repo without commits (or do it by hand on the website).

```
$ gh repo create deleteme --description "New Repo Description" --homepage "Project URL (optional)" --public --team your-org-name --template https://github.com/vpayno/template-golang
```

- Clone the template repo and modify it to match the new commit-less repo name.

```
$ git clone https://github.com/vpayno/template-golang new-repo-name

$ cd new-repo-name
```

- Create a new branch to create your first pull-request to get the GitHub actions to run to update the badge statues.

```
$ git switch -C rename_template
```

- Edit files to reflect the new repo.

```
$ git grep -R --files-with-matches CHANGEME-REPONAME | xargs sed -r -i -e 's/CHANGEME-REPONAME/new-repo-name/g'

$ git grep -R --files-with-matches CHANGEME_PROJECT_LABEL-REPONAME | xargs sed -r -i -e 's/CHANGEME_PROJECT_LABEL-REPONAME/New Repo Name/g'

$ git grep -R --files-with-matches CHANGEME | xargs sed -r -i -e 's/CHANGEME/cliname/g'

$ git grep -R --files-with-matches changeme | xargs sed -r -i -e 's/CHANGEME/cliname/g'

$ git add -u .

$ git commit -m 'chore: rename template'
```

- Edit the remote to point to your new repo. You can use sed or `git remote set-url origin https://github.com/your-org/new-repo-name`.

```
$ git remote -v

$ sed -r -i -e 's:vpayno:template-golang:your-org/new-repo-name:g' .git/config

$ git remote -v
```

- Push the new commit to the new branch (or use `git push origin main` if you chose not to make a new PR).

```
$ git push -u origin rename_template
```

- Either use the URL returned by the `git push` command or use the [GitHub Cli](https://github.com/cli/cli#installation) to create the pull-request.

```
$ gh pr create
```
