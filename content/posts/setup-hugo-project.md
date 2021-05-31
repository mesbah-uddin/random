---
title: "Setup Hugo Project"
date: 2021-05-31T20:18:01+09:00
draft: true
---

# @random
## Initialize hugo repo
```shell
hugo new site random -f yaml # use yaml
cd random
git init
git branch -M master
git commit --allow-empty -m "Initialize repo"
```

## Add initial site templates
```shell
git add .
git commit -m "Add hugo templates"
```

## Initialize hugo modules
```shell
hugo mod init github.com/mesbah-uddin/random
```

## Add theme
```shell
hugo mod get -u github.com/theNewDynamic/gohugo-theme-ananke
echo "theme: github.com/theNewDynamic/gohugo-theme-ananke" >> config.yaml # also change baseURL
git add .
git commit -m "Add theme as go submodule"
```
## Push to remote
```shell
git remote add origin git@github.com:mesbah-uddin/random.git
git branch -M master
git push -u origin master
```

## [Create gh-pages branch](https://jiafulow.github.io/blog/2020/07/09/create-gh-pages-branch-in-existing-repo/)
```shell
git checkout --orphan gh-pages
git reset --hard
git commit --allow-empty -m "Initialize gh-pages branch"
git push origin gh-pages
git checkout master
```

## Add gh-pages deploy workflow from [actions-hugo](https://github.com/peaceiris/actions-hugo)
Add workflow .github/workflows/gh-pages.yml.
Change  branch to `master` and use `extended` hugo.
