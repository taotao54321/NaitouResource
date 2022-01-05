+++
title = "飛車落ち上手 15 手勝利"
date = 2022-01-21
+++

全探索した結果、13 手以下の解はなかった。

SFEN: `sfen lnsgkgsnl/1r5b1/ppppppppp/9/9/9/PPPPPPPPP/1B7/LNSGKGSNL b - 1 moves 7g7f 3c3d 9g9f 9c9d 8h9g 2b9i+ 6i6h 9i8i 4i3h N*6d 6h7g 8i9h 9g6d 6c6d N*6c`

{{ shogi_playground(src="https://play.mogproject.com/?u=lnsgkgsnl_1r5b1_ppppppppp_9_9_9_PPPPPPPPP_1B7_LNSGKGSNL.b.-~0.7ku2jm7ty3ay8ug1dh9qaa4e9h4boa8lc9zg7ss2xabns.r&embed=true&sz=30&layout=s&p=jp1&bi=ja&ve=true&se=false") }}

[投了バグ](@/bug/index.md#resign) を利用。投了図では候補手68銀が最善手52玉を上書きしている。  
71地点で取り返しフラグが立っている。
