---
title: nvm
---

```bash
# リモートのLTSバージョンを表示する
nvm ls-remote --lts

# 特定のバージョンの Node.js をインストールする
nvm install v24.11.1

# インストールされているバージョンを列挙する
nvm ls

# Node.js のバージョンを一時的(現在のシェル)に切り替える
nvm use v24.11.1

# Node.js のバージョンを永続的(デフォルト)に切り替える
nvm alias default v24.11.1

# 使用中の Node.js のバージョンの表示する
nvm current
```
