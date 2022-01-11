# Decipad documentation

Welcome to our docs

## How they were created

In Decipad we use a monorepo. This is how we keep these notes in sync

### In the monorepo

```
git clone git@github.com:decipad/decipad.git
cd decipad
git subtree split -P apps/docs/docs -b docs-sync.v1
```

### To create these docs

```
cd documentation
git init
mkdir docs
echo "hello" > readme.me
git commit -a -m 'One commit"
git branch main
git checkout main
git branch -D master
git remote add local ../decipad
git subtree add -P docs local docs-sync.v1 --squash
```

## Updating docs

First create a new subtree branch in the monorepo, as above

Then in this repo

```
git subtree pull -P docs local docs-sync.v1 --squash
```
