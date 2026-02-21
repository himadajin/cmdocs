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
# origin/main の位置でローカルに main ブランチを作成して移動する
git checkout -B main origin/main
```

```bash
# 現在のブランチに origin/main を取り込む
git pull origin main
# 現在のブランチを origin/main にリセットする
git reset --hard origin/main
```

```bash
# 全ての設定を表示する
git config --list
# 名前とメールアドレスの設定を確認する
git config user.name
git config user.email
# 名前とメールアドレスをグローバル(~/.gitconfig)に設定する
git config --global user.name "HARADA Taiki"
git config --global user.email "email@example.com"
```

## `.git` directory

- `.git/config`: リポジトリ単位の設定ファイル
- `.git/info/exclude`: ローカルのみで無視するファイルを設定するファイル
