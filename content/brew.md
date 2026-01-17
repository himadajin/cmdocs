---
title: brew
tags:
  - macos
  - package-manager
---

**基本操作**

```bash
# パッケージをインストールする
brew install {package}
# パッケージをアンインストールする
brew uninstall {package}
# すべてのキャッシュを削除する
brew cleanup --prune=all
```

**リポジトリ**

```bash
# パッケージのリストを更新する
brew update
# 追加済みのリポジトリを表示する
brew tap
# リポジトリを追加する
# (リポジトリを "$(brew --prefix)/Library/Taps" にクローンする。)
brew tap {username}/{repository}
# リポジトリを削除する
brew untap {username}/{repository}
```

**検索**

```bash
# 手動でインストールしたパッケージを列挙する
brew leaves
# 古いバージョンのパッケージを列挙する
brew outdated
# 指定したパッケージの情報を表示する
brew info {package}
# パッケージを検索する
brew search {keyword}
```

## See also
- [[apt]]
- [[scoop]]
