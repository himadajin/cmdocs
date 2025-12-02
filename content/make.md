---
title: make
tags:
  - build-system
---

```bash
# 並列ビルドを実行する
make -j$(nproc) all

# デバッグ時にルールの実行過程を確認する
make --trace target

# 強制的に全てを再ビルド（make clean; make と同等）
make -B all

# コマンドを実行せず、実行過程を表示する(ドライラン)
make -n clean
```

## コマンドラインオプション

- `-n`: ドライランする(コマンドを実行せずに表示のみ行う)
- `-j$(nproc)`: プロセッサの数だけ並列実行する
- `-f FILE`: 指定したMakefileを使用する
    - `make -f Makefile.debug`
- `-C DIR`: ディレクトリを変更してから make を実行
    - `make -C ./build`
- `-B`: 強制再ビルド (全てのターゲットを無条件で作成)
    - `make -B all`

| オプション     | 説明                     | 使用例                        |
| :-------- | :--------------------- | :------------------------- |
| `-k`      | エラーが発生しても可能な限り継続       | `make -k all`              |
| `-s`      | サイレントモード（コマンドを表示しない）   | `make -s clean`            |
| `-p`      | データベース情報を出力（変数やルールの確認） | `make -p \| grep CXXFLAGS` |
| `-d`      | デバッグ情報を出力              | `make -d target`           |
| `--trace` | ターゲットの処理過程を表示          | `make --trace`             |

## 事前に定義された変数

- [Makefile 事前に定義された変数一覧 - Qiita](https://qiita.com/keitean/items/7b5fb6b562d8dc92dc20)
- [GNU make](https://www.gnu.org/software/make/manual/make.html#Implicit-Variables)

| 変数名   | 説明                        | デフォルト値 |
| :------- | :-------------------------- | :----------- |
| CC       | C コンパイラ                | cc           |
| CXX      | C++コンパイラ               | g++          |
| CFLAGS   | C コンパイラに与えるフラグ  | なし         |
| CXXFLAGS | C++コンパイラに与えるフラグ | なし         |
| LDFLAGS  | リンカ ld に与えるフラグ    |              |
| RM       | ファイルを削除するコマンド  | rm -f        |

---
## サンプル

### 単一の cpp プログラム

```makefile
CXX = clang++
CXXFLAGS = -std=c++11 -Wall --pedantic-errors

program: main.cpp
	$(CXX) $(CXXFLAGS) $< -o $@

run: program
	./program

all: clean program

clean:
	rm -f ./program

.PHONY: run clean
```

### 2 つのファイルをコンパイル&リンクする

```bash
> tree
.
├── Makefile
├── hello.cpp
├── hello.hpp
└── main.cpp

1 directory, 4 files
```

```makefile
CXX=/opt/llvm/llvm@19/bin/clang++
CXXFLAGS=-std=c++17 -Wall -O3

all: a.out

run: a.out
	./a.out

a.out: main.o hello.o
	$(CXX) $(CXXFLAGS) -v $^ -o $@ > $(addsuffix .log, $@) 2>&1

main.o: main.cpp
	$(CXX) $(CXXFLAGS) -v -c $< -o $@ > $(@:%.o=%.log) 2>&1

hello.o: hello.cpp hello.hpp
	$(CXX) $(CXXFLAGS) -v -c $< -o $@ > $(@:%.o=%.log) 2>&1

clean:
	$(RM) *.o *.log a.out
.PHONY: clean
```

## See also
- [[cmake]]
- [[ninja]]
