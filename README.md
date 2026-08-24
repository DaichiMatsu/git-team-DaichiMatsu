# git-team-DaichiMatsu

# PartA

## A1.

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % ls .git/refs/heads/

    dev-anna	dev-ben		dev-you		main

ファイル数:4つ

## A2.

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % cat .git/refs/heads/dev-anna .git/refs/heads/dev-ben .git/refs/heads/dev-you

    2dc6040da9b1e45ab67988f459131993476afb53
    2dc6040da9b1e45ab67988f459131993476afb53
    2dc6040da9b1e45ab67988f459131993476afb53

### 3つのファイルのSHAが同じ理由

今回用意した三つのファイルは同じ分岐元のmainから分岐しており、さらにそれぞれのファイルから新しい分岐が存在しないため全て同じコミットの位置を指している。したがってSHAの値は同じとなる。

## A3.

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline --graph --all

    * 0504968 (HEAD -> dev-you) feat: signup
    | * af52dde (dev-ben) feat: dark theme
    |/  
    | * 065c494 (dev-anna) feat: login
    |/  
    * 2dc6040 (origin/main, origin/HEAD, main) Initial commit

### 図の説明

この図はmainブランチを元として"dev-anna"、"dev-ben"、"dev-you"の三つのブランチが分岐している状態を表している。

# Part B

## Task3

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline --graph --all

    *   ec1c6fa (HEAD -> main) merge 'dev-anna'
    |\  
    | * 065c494 (dev-anna) feat: login
    * | af52dde (dev-ben) feat: dark theme
    |/  
    | * 0504968 (dev-you) feat: signup
    |/  
    * 2dc6040 (origin/main, origin/HEAD) Initial commit

## Task5

### 変更前ログ

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline -n 5

    e92b531 (HEAD -> dev-anna) ccc
    f959d5b bbb
    013db50 aaa
    065c494 feat: login
    2dc6040 (origin/main, origin/HEAD) Initial commit

### 変更後ログ

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline -n 5

    e6b9fd9 (HEAD -> dev-anna) feat: login
    2dc6040 (origin/main, origin/HEAD) Initial commit

# Part C

### コンフリクトブロック
(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % cat app.txt

    <<<<<<< HEAD
    login feature
    =======
    signup feature
    >>>>>>> dev-you

### 最終グラフ

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline --graph --all

    *   131d61b (HEAD -> main) resolve conflict
    |\  
    | * 0504968 (dev-you) feat: signup
    * |   ec1c6fa merge 'dev-anna'
    |\ \  
    | * | 065c494 (dev-anna) feat: login
    | |/  
    * / af52dde (dev-ben) feat: dark theme
    |/  
    * 2dc6040 (origin/main, origin/HEAD) Initial commit


# Part D

### ログ

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % git log --oneline -n 3

    afc6574 (HEAD -> main) helper
    131d61b resolve conflict
    ec1c6fa merge 'dev-anna'

### mainにbroken.txtがない証拠

(base) daichi.matsumoto@matsumotodaichinoMacBook-Air git-team-DaichiMatsu % ls

    README.md	app.txt		helper.txt	style.txt

