---
title: svn
tags:
  - vcs
---

```bash
# 現在のリビジョン情報を表示する
svn info

# 作業コピーを指定したリビジョンに更新する
svn update -r 12345

# 最新の5件のログを表示する
svn log -r HEAD:1 -l 5

# 特定のリビジョンのログを表示する
svn log -r 12345

# リポジトリをチェックアウトする
svn checkout "https://svn-example.com/repo/path/to/project/trunk"
```
