[English](README.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · **日本語** · [中文](README.zh.md) · [हिन्दी](README.hi.md)

# U-MA Atari Punk

画面上で組み立てる Atari Punk Console。2 つの NE555 のうち、ひとつはクロック、もうひとつはパルスが終わるまで再トリガーされないワンショット。2 つの 555 以外のすべての部品を変更でき、4 チャンネルのオシロスコープで観察し、結果をリアルタイムで聴けます。

**▶ アプリを開く：** https://buenosairesfront.github.io/ataripunk/

インストール不要。画面はスペイン語です。

## 使い方

### オシロスコープ
上部に 4 本の波形：C1 の電圧（IC1 の 6 番ピン）、IC1 の出力、C2 の電圧（IC2 の 6 番ピン）、スピーカー信号。クロック周波数、パルス幅、分周 ÷n、出力音名を表示。

### 01 · 回路
回路図全体。部品をタップして編集：電池（4.5–15 V）、R1・R2・R3、ポット VR1・VR2（値、軸の位置、A/B カーブ）、C1・C2・C3、スピーカー。スライダー、E12/E6 の標準値、または基板表記での入力（`4k7`、`10n`、`100u`、`2M2`）。2 つの NE555 は固定。プリセット 5 種。

### 02 · 演奏
XY パッド（X = VR1、Y = VR2）。背景は分周のピクセルマップで、色が ÷n、明るさが音の高さ。VR1・VR2・音量のノブと Gate モード。

### 03 · 階段
VR1 の軸位置に対する出力周波数。点線はクロック、太線は実際に鳴る音で、分周が変わる所で途切れます。これが Atari Punk の階段状の音です。

### 04 · 基板
実物風の部品で描いたイメージ基板。抵抗のカラーコード、セラミックコンデンサの表記（103 = 10 nF）、ポットの軸が値に合わせて変化。1 µF 以上は電解コンデンサになります。

### 05 · 部品表
現在の値と表記つきの部品リスト。コピーできます。

## 中身

依存関係なしの `index.html` ひとつ。音は 2 つの 555 をイベント単位で正確にモデル化し、AudioWorklet でサンプルごとに計算、C3 と負荷によるハイパスを通しています。近似であり、555 出力の負荷は考慮していません。

## ローカルで動かす

`index.html` をダウンロードして開くか、フォルダを配信：

```
python3 -m http.server 8000
```

<!-- u-ma:more -->
**U-MA のほかの作品：** すべての楽器とツールをひとつに → [U-MA ショーケース](https://github.com/buenosairesfront/U-ma/blob/main/README.ja.md)
<!-- /u-ma:more -->

## クレジット

Atari Punk Console：Forrest M. Mims III によるオリジナル設計（Stepped Tone Generator）。アプリ：U-MA サウンド · [Buenos Aires Front](https://www.instagram.com/buenos.aires.front/)。
