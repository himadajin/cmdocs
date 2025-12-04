---
title: wsl
tags:
  - windows
  - linux
---

```bash
# シャットダウンする
wsl --shutdown

# 指定したディストリビューションを起動する
# --distribution(-d) {distribution name}
wsl -d Ubuntu-22.04

# インストールされているディストリビューションを列挙する
# --list (-l): リスト表示する, --verbose (-v): 詳細表示する
wsl -l -v

# デフォルトのディストリビューションを設定する
wsl --set-default Ubuntu-22.04

# ディストリビューション(ext4ファイル)を削除する
wsl --unregister Ubuntu-20.04

# ディストリビューションをtarにエクスポートする
# --export {distribution name} {tar file}
wsl --export Ubuntu-22.04 Ubuntu-22.04.tar

# tarからディストリビューションをインポートする
# --import {distribution name} {install dir} {tar file}
wsl --import Ubuntu-22.04 "C:/wsl/Ubuntu-22.04" "C:/path/to/Ubuntu-22.04.tar"
```

## See also
- [[docker]]
