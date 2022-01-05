+++
title = "バグ"
date = 2022-01-21
+++

## 詰んでいないのに投了 {#resign}

COM玉が詰んでいないのにCOMが投了することがある。これの原因は 2 通りある:

* 詰みを逃れる手はあるが、それらが全て駒捨てと判定されて却下されたため([末端局面評価 第 1 段階](@/engine/index.md#leaf-evaluation-first) を参照)。
* [取り返しフラグ補正](@/advantage-disadvantage/index.md#disadvantage) により、[候補手と最善手の比較](@/engine/index.md#compare-candidate-and-best) を行う際の自殺手判定が機能せず、さらに自殺手が最善手に取って代わったため。

後者のケースは取り返しフラグ補正があっても稀にしか起こらない(具体例は [平手 13 手勝利](@/kifu-minply-hirate/index.md) などを参照)。自殺手は一般に総駒損価値が大きく、最善手として採用されにくいため。  
自殺手が総駒損価値の不利を覆して最善手となるためには、以下の条件を満たす必要がある:

* ルート局面での [COM power](@/engine/index.md#root-evaluation) が 18 または 19
* 自殺手と比較対象の最善手がどちらも駒取りでない(捕獲する駒の価値が 0)
* 自殺手の方が総駒得価値が大きく、`(総駒得価値の差分) > (総駒損価値の差分)` である

なお、ルート局面での COM power が 20 以上ならば自殺手は最善手にならない。[末端局面評価 第 2 段階](@/engine/index.md#leaf-evaluation-second) において、COM power が 20 以上かつ捕獲する駒の価値が 2 未満ならば総駒得価値に応じて捕獲する駒の価値を増やす補正がかかり、上記の 2 番目の条件を満たさなくなるため。

## 玉で王手 {#check-with-king}

[再現用ムービー (.fm2)](check-with-king.zip)

序盤(定跡内)では玉で王手できることがある。[駒得マス](@/advantage-disadvantage/index.md#advantage) を参照。

## 王手放置 {#player-suicide}

[再現用ムービー (.fm2)](player-suicide.zip)

二枚落ち上手ではプレイヤー側が王手放置できる手順がある。[定跡処理と最終的な指し手決定](@/engine/index.md#book) を参照。

## COM玉を取る {#capture-com-king}

[再現用ムービー (.fm2)](capture-com-king.zip)

[取り返しフラグ補正](@/advantage-disadvantage/index.md#disadvantage) が大量にかかると、COM玉の詰み判定に失敗してCOM玉が取れてしまうことがある。[定跡処理と最終的な指し手決定](@/engine/index.md#book) を参照。

## COMが王手放置して詰ましてくる {#com-suicide-mate}

[再現用ムービー (.fm2)](com-suicide-mate.zip)

[取り返しフラグ補正](@/advantage-disadvantage/index.md#disadvantage) が大量にかかると、プレイヤー玉の詰み判定を行う際に自殺手を弾き損ねて、自殺手によってプレイヤー玉が詰まされて負けになることがある。[末端局面評価 第 1 段階](@/engine/index.md#leaf-evaluation-first) を参照。

## スタックポインタ設定ミス {#stack-pointer}

時間切れ負け時のスタックポインタ設定コード(`$C32F`)は `ldx $7F` となっているが、正しくは `ldx #$7F` と思われる。  
しかし、この後スタックから値を取り出すことはないのでたまたま壊れていない。
