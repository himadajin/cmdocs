---
title: clang
tags:
  - compiler
  - llvm
---

```bash
# C言語のソースコードをLLVM IRにコンパイルする
clang -emit-llvm -S -o test.ll test.c

# 言語標準を指定してコンパイルする
clang -std=c23 main.c

# サポートされているターゲットの一覧を表示する
clang --print-targets

# デフォルトのtarget-tripleを表示する
clang --print-target-triple
clang -dumpmachine
```

## See also
- [Clang command line argument reference](https://clang.llvm.org/docs/ClangCommandLineReference.html)
- [[opt]]
