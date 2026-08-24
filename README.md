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
