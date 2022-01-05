+++
title = "二枚落ち上手 15 手勝利"
date = 2022-01-21
+++

全探索した結果、13 手以下の解はなかった。

SFEN: `sfen lnsgkgsnl/1r5b1/ppppppppp/9/9/9/PPPPPPPPP/9/LNSGKGSNL b - 1 moves 7g7f 3c3d 7i8h 2b8h+ 4g4f 8h8i 2g2f 8i9i 5i5h N*2g 5h4g 2g3i+ 4i3i 6c6d N*6c`

{{ shogi_playground(src="https://play.mogproject.com/?u=lnsgkgsnl_1r5b1_ppppppppp_9_9_9_PPPPPPPPP_9_LNSGKGSNL.b.-~0.7ku2jm9uw1cx7768ve6y29zy9lqbpk8go6zn9hm2xabns.r&embed=true&sz=30&layout=s&p=jp1&bi=ja&ve=true&se=false") }}

[投了バグ](@/bug/index.md#resign) を利用。投了図では候補手58銀が最善手52玉を上書きしている。  
71地点で取り返しフラグが立っている。
