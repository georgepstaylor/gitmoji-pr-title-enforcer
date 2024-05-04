# gitmoji-enforcer

A simple action to enforce the use of gitmoji in PR titles.

It will leave a comment on the PR like so:
https://github.com/georgepstaylor/gitmoji-pr-title-enforcer/pull/2#issuecomment-2094373552
or 
https://github.com/georgepstaylor/gitmoji-pr-title-enforcer/pull/2#issuecomment-2094373635
Depending on whether the PR title is valid or not.

## Usage
```yaml
name: Enforce gitmoji PR
on:
  pull_request:
    types: [opened, edited, reopened, synchronize]
permissions:
  pull-requests: write
jobs:
  gitmoji-pr-title:
    runs-on: ubuntu-latest
    steps:
      - name: Enforce gitmoji PR title
        uses: georgepstaylor/gitmoji-pr-title-enforcer@v1.0.0
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

Using the above example verbatim, you can use the job title `gitmoji-pr-title` as a required check.