# gpt2-japanese
Japanese GPT2 Generation Model

# GPT2日本語モデル

***<font color='red'>New</font>***
- モデルファイルを外部からダウンロードするようにしました
- [独自コーパス](corpus.md)で学習させたモデルを追加しました
  - 汎用モデル、小説生成モデルを追加しました
- 文章のベクトル化用コードを追加しました
- 生成文章からスペースを除去しました
- top_kのデフォルト値を40にしました
- top_k,top_p,temperatureを引数から設定出来るようにしました
- [クラウドファウンディングでより大きなモデルのトレーニングのためのサーバー代の支援を求めています](https://camp-fire.jp/mypage/projects/320938/)

## GPT2に日本語コーパスを学習させたものです

## 日本語文章の生成モデルです

- 現在、3つの学習済みのモデルを公開しています
  - モデル1：汎用日本語生成モデル
    - https://www.nama.ne.jp/models/ja-117M.tar.bz2
    - 汎用的に使えるモデルです
  - モデル2：小説生成モデル
    - https://www.nama.ne.jp/models/ja-117M_novel.tar.bz2
    - Web小説を学習させたモデルです
  - モデル3：Wikipediaモデル
    - https://www.nama.ne.jp/models/ja-117M_wiki.tar.bz2
    - 最初に公開したモデルです。新しい汎用モデルの方が良いので、基本使いません
- パラメーター数117Mの一番小さなモデルのみです
  - より大きなモデルは手持ちのRTX2080tiではメモリが足りず、学習出来ません
  - クラウドファウンディングでサーバー代を募集する予定です

### 学習させたコーパスについて

[corpus.md](corpus.md)

### TODO

✓大規模コーパスの作成（2020/8/20）<br>
✓小説生成モデルの作成（2020/8/20）<br>
✓生成パラメーターの修正（2020/8/20）<br>
□分かち書き部分の修正<br>

### 使い方

最初に、モデルファイルをダウンロードします

```sh
$ wget https://www.nama.ne.jp/models/ja-117M.tar.bz2
$ tar xvfj ja-117M.tar.bz2
```

GitHubからコードをクローンしてモデルファイルをコピーします

```sh
$ git clone https://github.com/tanreinama/gpt2-japanese
$ cd gpt2-japanese
$ cp ../ja-117M ./
```

モデルを指定して実行します

```sh
$ python3 gpt2-generate.py --model ja-117M --num_generate 1
```

### サンプル

```
$ python3 gpt2-generate.py
実行例えばデバッグの際の実行コマンドってなにものです。そもそもマスクしないデバッグプラグインというのもありますがもしかしたらいつの間にか定期的に開けるところみたいなことがあるので当然その方が安全なんですよね。
なかなかログアウトできない人が多いですが(;^_^A

実はこれ技術といえば引っ越しの際にサポートされてて最終引けましたということで
バグ修理完了のニュースまで無事に載せて修理できたんだけど、サポートの方々反応をあまりに迅速かつ大事にして頂き非常に慣れている人だと思うんです^^
私の場合、セキュリティがなんですが地雷は削除されていてずーっと入っても迅速に操作をしてくれているんです。
悪質ならこの程度より実行コマンドがどんな弊�
になっても良い行為なんだろうなぁ。(^_^;)
敷居にもなってそれが微妙でした!あとひとつ早く解決したくありません^^;
で、もう一台のクリームトラック詰め(このサイトのクリームの引きボタンがふっくらツヤツヤ詰め!)をすべて引きで巻いておこう!
このクリームと同じで、反応がありますが誤って前後に引っ張られて落下する危険があります。
また、セキュリティも大切です。反応がある時に引っ越し(略)の際にごまかすかも?シェイプにすり替えてれば
ホコリが気になるのか?衛生面?玄関先ですが子供達と話してみてください
なので今のトラックをひっかければ面倒になると思います。
修理の内容に関しては他に良い経験がありますか?

（・・・略）
```

- 以前のWikipediaのみ学習させたモデルよりも、自然な文章が生成されるようになりました
- ブログ記事、ニュースリリース、百科事典サイトなどの要素を含んだ汎用的な文章生成が出来ます

```
$ python3 gpt2-generate.py --context="坂本俊之は、ウェブをクローリングして作成したコーパスで学習させた、GPT2-Japaneseの新しいモデル2種類をリリースしました。"
これらの作成全てに、ユーザーは対応した物理学とコンピューターやリンクそしてインタラクティブな操作を定義します。コーパスの使用にはパラメータがあり、ショックケースとクラスの類似モデルが用意されています。ユーザーはプログラミング言語初めてのGPT2をレクチャーします。
ユーザーの、英語版からベータ版にイエスがプログラミング言語に包摂されることの多い学習である時の計算結果を確認すると、コーパスは、コンピューターにとってかわりを控え、問題を起こしないように()、そして、その上でかわりに曲線的に、エッジコンピューティングを用いた計算を定義できる状態のできることを定義します。

「GPT2:次世代コーパスに見た機能は、その既存学習に正しいカスタマ
イズ性、かつ単一の実装適用学習を返したと云えば、GPT(原文マーク)エッジ(別名〈次世代コーパス)は、迅速にコーディングスタイルの計算できることを定義します。」
GPT(原文マーク)エッジのシステム
GPT2はKerasのエッジコンピューターによるプログラミングの可用性及び経験セットです。

GPT(原文マーク)エッジに関する言葉
言わば「モリースピース(<PRICE>)」です。
「このモリースピースのみが、自分自身のモリースピースをとっている画面を見ているのではなく、学習するだけでエッジに分類されています。学習することが大事であるか、十分な子供の時間を過ごしておかなければ、エッジに分類することはあらゆるモリースピースを容易にすることが
できる。」
```

- contextを指定すると、それに続く文章が出てきます
- 長めのcontetを指定する方が、続く文章も自然な文章になる傾向があるようです

```
$ python3 gpt2-generate.py --model ja-117M_novel --context="俺の名前は坂本俊之さん。何処にでもいるサラリーマンだ。"
能力って奴も僕が使えたらいいなぁ。
「あぁ、どうぞ。ご用意はっ。」
「いただきまぁす。」
「あわわわ・・・」
召喚されると、皆目見当がつかない。相当気まずそうだ。シチュエーションを理解するにも理由って一番不思議だ。
しかし、この神殿がくっ付く前にあの黒い兵士を使えば救けないか
「国王、今戦わなきゃと思いましたが、一体どこに行けば?・・・あれはもともとあの黒い兵ですよね。第1小隊1体とその兵で構成する第1小隊隊長のアイビの部隊を縛り上げなかろ。そろそろ第1小隊の追手が引き千切れば。」
そりゃシンカの部隊がいるものだから被害は無いよな。
「ハァ、話を今付けるとしましょう。
その聖剣を持っているのは元自衛官のエクセリスさんですよ。タクシーを待ちますか?人形が現れないので話をすればいいのでしょう。速やかに聖剣が封印されてしまいました。離陸後に戻って来ます。」
「ほほほ〜・・・何にせよ見違えるほどに広範囲に焼却されるわずかなのに無事でよかった。」
「エクセリスさん部隊では真新しい制服・・・」
エクセリスの現代語聞こうによるあの速さにアイビが文句ばかり上げている。
「なんの攻撃が・・・うーん、視界がぐんと悪くなりつつある・・・よく見ると皆の制服?そうは見えないっすね・・・でもやっぱり引きずっていたら血だらけでも見えるか少し目立ってし......並みの魔術師だとしたらやっぱり新かな幻
覚っぽいっすね。」
```

- 小説生成モデルを使用すれば、異世界召喚されることもできます

### 文章ベクトル生成

```
$ python3 gpt2-transform.py --context="江戸時代のインターネット回線"
[ 1.10667396e+00 -1.32296407e+00  3.68696272e-01 -8.89108360e-01
  6.70326054e-01  1.46573734e+00  6.14574385e+00  1.69398114e-02
  1.41465652e+00 -4.86905873e-01  1.44136465e+00  7.09628284e-01
  7.76252687e-01  2.27544069e+00  9.44801420e-02  1.90467823e+00
 （・・・略）
```

- 文章のベクトル化を行います

