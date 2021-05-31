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
git remote add origin git@github.com:mesbah-uddin/random.git
git branch -M master
git push -u origin master