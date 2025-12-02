---
title: brew
tags:
  - macos
  - package-manager
---

```bash
# パッケージのリストを更新する
brew update

# 手動でインストールしたパッケージを列挙する
brew leaves

# 古いバージョンのパッケージを列挙する
brew outdated

# すべてのキャッシュを削除
brew cleanup --prune=all

# リポジトリを追加
brew tap riscv-software-src/riscv
# リポジトリを削除
brew untap riscv-software-src/riscv
```

`brew tap riscv-software-src/riscv`としたときは暗黙的に
```
https://github.com/riscv-software-src/homebrew-riscv.git
```
を参照する。