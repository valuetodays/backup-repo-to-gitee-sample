backup-repo-to-gitee-sample

## 配置如下

此文件内容在.github/workflows/backup-repo-to-gitee.yml中。

```yml
name: Sync Github Repos To Gitee

on:
  push:
    branches: 
      - master
      - main

jobs:
  build:
    runs-on: ubuntu-20.04
    steps:
    - name: backup-repo-to-gitee
      uses: valuetodays/backup-repo-to-gitee@master
      with:
        # default is github repo name
        giteerepo: sync-gitee-mirror-test1
        # default is github user name
        giteeuser: valuetodays
        # must not be empty
        giteetoken: ${{ secrets.GITEE_TOKEN }}
        
```