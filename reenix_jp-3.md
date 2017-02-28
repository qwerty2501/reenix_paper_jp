<style type="text/css">
li.L0, li.L1, li.L2, li.L3, li.L4, li.L5, li.L6, li.L7, li.L8, li.L9
{
    list-style-type: decimal;
}
</style>
<script src="https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js?autoload=true&amp;skin=desert&amp;lang=rust" defer="defer"></script>
[ここ](http://scialex.github.io/reenix.pdf)の翻訳になります  
原文は2015年に書かれたものなので現在のRustの仕様と異なることが書いてある場合があります  
本文章は[Github](https://github.com/qwerty2501/reenix_paper_jp)で管理されています    
  
# 3 Rustの評価  
  
小節1.2で言及した通り、Rustはかなり新しく、メモリと型安全に注目したシステム指向型プログラミング言語である。Rustのより包括的な型とメモリ分析は、ますます速度と安全性の両方を求められるようになった状況に置かれているCの素晴らしい代替にするためにある。以前はRustでOS作成など誰も真剣に試みたことはなかったし、Reenix実装を通して私はこの界隈でのRustの強みと弱みの深い認識を得ることができた。また、私は様々な分野においてRustが変更されてこの領域での利便性が向上するのを体験することができた。  
ここではRustを使うことによる利点とプロジェクト全体を通して発見したことについて解説する。次に、Rust使用上の問題について検証し、現在起こっている言語上の主要な問題について見ていく。最後に、RustのパフォーマンスをCと比較して短い検証をして終える。  
  
## 3.1 Rustの利点  
  
このプロジェクトの過程で、私はシステムプログラミングにおいてRustを使うことは、CまたはC++を超える沢山の利点があることを見つけた。これらを並べると、利便性における問題が簡単であること、可用性における主要な進歩の明快であること、正確なコード作成のための機能からなる。