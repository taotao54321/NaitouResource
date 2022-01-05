+++
title = "平手 13 手勝利"
date = 2022-01-21
+++

全探索した結果、12 手以下の解はなかった。

ここで示す手順は時間制限の有無によらず成立する。


## 97角型

SFEN: `startpos moves 7g7f 3c3d 9g9f 9c9d 8h9g 2b9i+ 7i8h 9i8i 6i7h N*6d 9g6d 6c6d N*6c`

{{ shogi_playground(src="https://play.mogproject.com/?u=~0.7ku2jm7ty3ay8ug1dh9uwa4e9qcboa7ss2xabns.r&embed=true&sz=30&layout=s&p=jp1&bi=ja&ve=true&se=false") }}

初出は[緑SM64氏の動画](https://www.nicovideo.jp/watch/sm39739725)。

[投了バグ](@/bug/index.md#resign) を利用。投了図では候補手58香が最善手52玉を上書きしている。  
71地点で取り返しフラグが立っている。


## 18香型

SFEN: `startpos moves 7g7f 3c3d 8h2b+ 3a2b 1i1h B*1i 5i6h 8b7b 3i4h 1i2h+ 4g4f 2h2i B*1e`

{{ shogi_playground(src="https://play.mogproject.com/?u=~0.7ku2jm8rl09k93ibzi9ls20u9co93l776842bxi.r&embed=true&sz=30&layout=s&p=jp1&bi=ja&ve=true&se=false") }}

[投了バグ](@/bug/index.md#resign) を利用。投了図では候補手56桂が最善手42金を上書きしている。  
29馬の利きにより、56地点で取り返しフラグが立っている。
