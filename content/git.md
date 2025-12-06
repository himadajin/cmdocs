---
title: git
tags:
  - vcs
---

```bash
# リモートリポジトリから最新の変更を取得する
git fetch

# 新しいブランチを作成して移動する
git switch -c feat-XXXX

# 特定のタグにチェックアウトする
git checkout llvmorg-21.1.7

# 変更を一時的に退避する
git stash

# main ブランチを origin/main の位置に強制的に作成・移動する
git checkout -B main origin/main
```

```bash
# ローカルの main ブランチにチェックアウトし、
# リモートの origin/main を取り込む
git checkout main
git pull origin main
```
