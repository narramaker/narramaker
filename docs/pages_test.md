# NarraMaker ディレクティブ ヘルプ

### 適用バージョン 
- NarraMaker 2.7

# 目次

- [0. 記法と共通ルール](#0)
- [1. ディレクティブ一覧](#1)
- [2. ナレーションと字幕](#2)
- [3. 音声合成設定](#3)
- [4. ポインター](#4)
- [5. アニメーション](#5)
- [6. 動画・効果音](#6)
- [7. ブロック・その他](#7)
- [8. パラメーター仕様](#8)

---

## 0. 記法と共通ルール

### 構文の読み方

<pre><code>[#ディレクティブ名:(<a href="#param-optional">引数1</a>):&lt;<a href="#param-required">引数2</a>&gt;]</code></pre>

- `[#` で始まり `]` で終わる部分がディレクティブです。
- `:` は引数の区切りです。引数を省略して後続の引数を指定するときも、区切りの `:` を残してください。
- 書式中の `<パラメーター>` は必須、`(パラメーター)` は省略可能です。括弧や山括弧は実際に入力しません。
- 書式中のパラメーター名をクリックすると、[パラメーター仕様](#8)の説明へ移動します。
- ディレクティブ名と予約値（トリガーやオプション）は大文字・小文字を区別しません。図形名や音声エンジン名などは、実際の登録名を指定してください。
- 必須引数を省略したり、定義より多くの引数を指定したりすると、検証時にエラーまたは警告になります。

例：

```text
[#show:タイトル:0.2:1.0:With]

[#speech:こんにちは:0.5::Click]

[#motion:図形A:図形B:0:1:After:HideFrom::KeepSize]
```

### コメント

| 書式 | 説明 |
|---|---|
| `[コメント]` | 1行コメント。`[#` で始まらない角括弧内はコメントとして扱われます。 |
| `[##<]`<br>コメントする行<br>`[##>]` | ブロックコメント。開始から終了までの内容を読み飛ばします。 |

ブロックコメントは入れ子にせず、開始と終了を対にしてください。コメントではない文章に角括弧を使うと、コメントとして取り除かれることがあります。

### 通常の文章

ディレクティブではない行の文章は、ナレーションとして読み上げられます。文章の途中に `[#p]` を置くと、その位置でポインターを実行できます。

```text
ここを説明します。[#p]次の図形を見てください。
```

明示的に `#speech` を使う場合、読み上げテキスト中の `:` は引数区切りと解釈されます。文章中の字幕と読み上げ内容を変える書式は「[ナレーションと字幕](#2)」を参照してください。

---

## 1. ディレクティブ一覧

既定トリガーは、個別の引数で指定しなかった場合に使われる実行条件です。`With` は直前の動作と同時、`After` は直前の動作の後、`Click` はクリックまたは Enter 待ちです。

### コメント

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `[コメント]` | 1行コメント | なし |
| `[##<]` / `[##>]` | ブロックコメントの開始／終了 | なし |

### ナレーション

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#speech` | 読み上げ音声を生成 | テキスト、遅延、トリガー |
| `#cc` | クローズドキャプションの生成を切り替え | On / Off |
| `#quiet` | 指定時間、無音で待機 | 期間 |
| `#click` | クリックまたは Enter を待つ | なし |

### ポインター

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#p` | 次のモーションポインター動作 | 遅延、期間、トリガー、オプション、滑らかさ、強調効果 |
| `#pDef` | 後続の `#p` の既定値を設定 | 遅延、期間、トリガー |
| `#pHide` | ポインターを非表示にする | 遅延、期間、トリガー |

### アニメーション

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#show` / `#hide` | 図形をフェードイン／フェードアウト | 図形名、遅延、期間、トリガー |
| `#anim` | 図形に設定されたユーザー作成アニメーションを実行 | 図形名、遅延、期間、トリガー |
| `#slideIn` / `#slideOut` | 図形を指定方向でスライドイン／アウト | 図形名、方向、遅延、期間、トリガー |
| `#motion` | 図形Aから図形Bへのモーション | From名、To名、遅延、期間、トリガー、各種オプション |
| `#motionIn` / `#motionOut` | 図形AからBへ移動しながらフェードイン／アウト | From名、To名、遅延、期間、トリガー、滑らかさ |
| `#move` | 図形Aを図形Bの位置へ移動（拡大縮小・回転を含む） | From名、To名、遅延、期間、トリガー、滑らかさ、強調効果 |

### 動画・効果音

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#se` | 音声オブジェクトを再生 | 音声名、遅延、トリガー |
| `#play` | 動画オブジェクトを再生 | 動画名、遅延、トリガー |
| `#playWith` | 動画を直前の動作と同時に再生（旧書式） | 動画名、遅延、トリガー欄 |
| `#playPause` | 動画を一時停止／再開 | 動画名、遅延、トリガー |

### 音声合成

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#engine` / `#port` | 音声合成エンジン／ポートを変更 | エンジン名／5桁のポート番号 |
| `#speaker` | 音声モデル／スタイルを変更 | モデル名、スタイル名 |
| `#speed` / `#tempoDynamics` | 話速／テンポの緩急を変更 | 数値 |
| `#pitch` / `#volume` | 音高／音量を変更 | 数値 |
| `#preGap` / `#postGap` | 音声の開始前／終了後の無音時間を変更 | 秒数 |
| `#speechIntonation` / `#speechPause` | 抑揚・感情表現の強さ／音声中の間を変更 | 数値 |

### 参照資料

| ディレクティブ | 用途 | 引数 |
|---|---|---|
| `#noCopy` | 指定オブジェクトを参照資料に出力しない | オブジェクト名 |
| `#noCopySlide` | スライドを参照資料に出力しない | なし |

### 既定トリガー

| ディレクティブ | 既定トリガー |
|---|---|
| `#speech` | `After` |
| `#quiet` | `After` |
| `#p` | `With` |
| `#pDef` | `With` |
| `#pHide` | `After` |
| `#show` | `With` |
| `#hide` | `With` |
| `#anim` | `With` |
| `#slideIn` | `With` |
| `#slideOut` | `With` |
| `#motion` | `With` |
| `#motionIn` | `With` |
| `#motionOut` | `With` |
| `#move` | `With` |
| `#se` | `After` |
| `#sound`（旧書式） | `After` |
| `#play` | `After` |
| `#playWith`（旧書式） | `With` |
| `#playPause` | `With` |
| `#click` | `Click` |

`#playWith` は旧書式で、トリガー欄を指定しても `With` で実行されます。表にないディレクティブにはトリガー引数がありません。

---

## 2. ナレーションと字幕

### `#speech`

<pre><code>[#speech:(<a href="#param-speech-text">読み上げテキスト</a>):(<a href="#param-delay">遅延</a>)::(<a href="#param-trigger">トリガー</a>)]</code></pre>

テキスト、遅延、トリガーは省略できます。トリガーは4番目の引数です。3番目の引数は未使用のため、トリガーを指定するときも空欄にします。

```text
[#speech:おはようございます]

[#speech:読み上げを少し遅らせる:0.5]

[#speech:クリックで読み上げ:::Click]
```

通常の文章行も `#speech` として処理されます。字幕と読み上げる文を分ける場合は、テキスト内に `{字幕|読み上げ}` と記述します。

```text
[#speech:{本日の予定|きょうのよてい}]
```

`:` は引数の区切り、`[` と `]` はコメント／ディレクティブの記号として使われます。明示的な `#speech` のテキストにこれらの記号をそのまま含めないでください。

### `#cc`

```text
[#cc:On]

[#cc:Off]
```

`On` でクローズドキャプションを生成し、`Off` で生成しません。引数を省略すると、NarraMaker の設定に従います。

### `#quiet` と `#click`

<pre><code>[#quiet:(<a href="#param-duration">期間</a>)]

[#click]</code></pre>

`#quiet` は指定した秒数だけ無音で待機します。期間を省略すると既定の待機時間を使います。`#click` はクリックまたは Enter が入力されるまで待ちます。

---

## 3. 音声合成設定

これらの設定はスライドノート内で後続の読み上げに適用されます。値を省略した項目は既定の音声合成設定を使います。

| ディレクティブ | 書式 | 許容値・説明 |
|---|---|---|
| `#engine` | `[#engine:(エンジン名)]` | NarraMaker に設定されているエンジン名 |
| `#port` | `[#port:(ポート番号)]` | 5桁の数字 |
| `#speaker` | `[#speaker:<モデル名>:(スタイル名)]` | モデル名は必須、スタイル名は省略可 |
| `#speed` | `[#speed:(数値)]` | 0.50～2.00 |
| `#tempoDynamics` | `[#tempoDynamics:(数値)]` | 0.00～2.00 |
| `#pitch` | `[#pitch:(数値)]` | -0.15～0.15 |
| `#volume` | `[#volume:(数値)]` | 0.00～2.00 |
| `#preGap` / `#postGap` | `[#preGap:(秒数)]` | 0.00～1.50秒 |
| `#speechIntonation` | `[#speechIntonation:(数値)]` | 0.00～2.00。抑揚／感情表現の強さ。既定値は1.00。 |
| `#speechPause` | `[#speechPause:(数値)]` | 0.00～2.00。音声中の間の長さ。既定値は1.00。 |

---

## 4. ポインター

### `#p`

<pre><code>[#p:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-options">オプション</a>):(<a href="#param-smoothing">滑らかさ</a>):(<a href="#param-emphasis">強調効果</a>)]</code></pre>

すべての引数を省略できます。遅延・期間・トリガーを省略した場合は、`#pDef` で設定した既定値を使います。オプションには `KeepFrom` を指定できます。

```text
[#p]

[#p:0.2:0.4:Click]

[#p:::After:KeepFrom]
```

### `#pDef` と `#pHide`

<pre><code>[#pDef:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>)]

[#pHide:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>)]</code></pre>

- `#pDef` は後続の `#p` の既定値を変更します。省略した項目は既定値のままです。
- `#pHide` はポインターをフェードアウトします。
- `#p` と `#pDef` の既定トリガーは `With`、`#pHide` の既定トリガーは `After` です。

### 行中でのポインター

通常の文章中に `[#p]` を置くと、その前後の文章を読み上げながら指定位置でポインターを実行します。

```text
最初の図形です。[#p]次の図形です。[#p]最後の図形です。
```

---

## 5. アニメーション

### 表示・非表示

<pre><code>[#show:&lt;<a href="#param-shape-name">図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-emphasis">強調効果</a>)]

[#hide:&lt;<a href="#param-shape-name">図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>)]</code></pre>

### スライドイン・スライドアウト

<pre><code>[#slideIn:&lt;<a href="#param-shape-name">図形名</a>&gt;:&lt;<a href="#param-direction">方向</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-emphasis">強調効果</a>)]

[#slideOut:&lt;<a href="#param-shape-name">図形名</a>&gt;:&lt;<a href="#param-direction">方向</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>)]</code></pre>

方向は `Left`、`Right`、`Up`、`Down` です。図形名と方向は必須です。

### 図形間のモーション

<pre><code>[#motion:(<a href="#param-shape-name">From図形名</a>):&lt;<a href="#param-shape-name">To図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-motion-options">Fromオプション</a>):(<a href="#param-motion-options">Toオプション</a>):(<a href="#param-motion-options">サイズオプション</a>):(<a href="#param-smoothing">滑らかさ</a>):(<a href="#param-emphasis">強調効果</a>)]

[#motionIn:(<a href="#param-shape-name">From図形名</a>):&lt;<a href="#param-shape-name">To図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-smoothing">滑らかさ</a>):(<a href="#param-emphasis">強調効果</a>)]

[#motionOut:(<a href="#param-shape-name">From図形名</a>):&lt;<a href="#param-shape-name">To図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-smoothing">滑らかさ</a>)]

[#move:(<a href="#param-shape-name">From図形名</a>):&lt;<a href="#param-shape-name">To図形名</a>&gt;:(<a href="#param-delay">遅延</a>):(<a href="#param-duration">期間</a>):(<a href="#param-trigger">トリガー</a>):(<a href="#param-smoothing">滑らかさ</a>):(<a href="#param-emphasis">強調効果</a>)]</code></pre>

To図形名は必須、From図形名は省略できます。図形Aから図形Bへ移るアニメーションでは、Aの位置・サイズ・回転などを基準にBへ動かします。`#motionIn` は移動しながら表示し、`#motionOut` は移動しながら非表示にします。`#move` は図形A自体を図形Bの位置へ移動します。

#### From／To／サイズのオプション（`#motion`）

| 引数 | 値 | 動作 |
|---|---|---|
| Fromオプション | `HideFrom` | From図形を表示せずに開始 |
| Fromオプション | `KeepFrom` | 終了後もFrom図形を残す |
| Toオプション | `HideTo` | 終了後にTo図形を表示しない |
| サイズオプション | `KeepSize` | 図形の拡大・縮小を行わない |

空欄にした場合は各オプションを指定しない動作になります。

#### 滑らかさ

`#p`、`#motion`、`#motionIn`、`#motionOut`、`#move` で指定できます。

| 値 | 動作 |
|---|---|
| `SmoothStart` | 滑らかに開始 |
| `SmoothEnd` | 滑らかに終了 |
| `SmoothBoth` | 滑らかに開始・終了 |
| `SmoothBounce` | 滑らかに開始し、行き過ぎて戻る |
| `BounceEnd` | 行き過ぎて戻る |

#### 強調効果

`#show`、`#slideIn`、`#motion`、`#motionIn`、`#move` など、書式に強調効果欄があるディレクティブで指定できます。

| 値 | 効果 |
|---|---|
| `Pulse` | パルス |
| `ColorPulse` | カラーパルス |
| `Spin` | スピン |
| `Seesaw` | シーソー |
| `Wave` | ウェーブ |

`#move` では `Wave` を指定できません。

---

## 6. 動画・効果音

<pre><code>[#se:&lt;<a href="#param-sound-name">音声オブジェクト名</a>&gt;:(<a href="#param-delay">遅延</a>)::(<a href="#param-trigger">トリガー</a>)]

[#play:&lt;<a href="#param-movie-name">動画オブジェクト名</a>&gt;:(<a href="#param-delay">遅延</a>)::(<a href="#param-trigger">トリガー</a>)]

[#playWith:&lt;<a href="#param-movie-name">動画オブジェクト名</a>&gt;:(<a href="#param-delay">遅延</a>)::(<a href="#param-trigger">トリガー</a>)]

[#playPause:&lt;<a href="#param-movie-name">動画オブジェクト名</a>&gt;:(<a href="#param-delay">遅延</a>)::(<a href="#param-trigger">トリガー</a>)]</code></pre>

`#se` と `#play` の既定トリガーは `After`、`#playWith` と `#playPause` の既定トリガーは `With` です。3番目の引数は未使用のため、トリガーを指定する場合も空欄にします。`#playWith` は旧書式のため、トリガー欄の値にかかわらず `With` で実行されます。

```text
[#se:拍手:0.2::With]

[#play:紹介動画:::Click]
```

`#sound` は旧書式で、`#se` と同じ音声再生として扱われます。新しく書く場合は `#se` を使用してください。`#playWith` も旧書式です。`#play` のトリガーに `With` を指定する書き方を推奨します。

---

## 7. ブロック・その他

### `#parallel`

```text
[#parallel]
  ...
[#endParallel]
```

ブロックを開始・終了します。ブロックは入れ子にできません。旧書式の `#para` / `#endpara` も `#parallel` / `#endParallel` と同じ扱いです。

### `#concatSpeech`

```text
[#concatSpeech]
[#speech:最初の文]
[#speech:次の文]
[#endConcatSpeech]
```

ブロック内の複数の読み上げテキストを1つの読み上げにまとめます。読み上げの途中でポインターを動かす場合は、ブロック内に `[#p]` を記述します。ブロックは入れ子にできません。

### 内部ディレクティブ

`#divSpeech` / `#endDivSpeech` は、文章中のポインターや `#concatSpeech` の処理で内部的に使われるディレクティブです。通常はノートに直接記述する必要はありません。

`#concat` / `#endConcat` は旧ディレクティブです。現在の処理では動作を定義していないため、新しいノートでは使用せず、読み上げの結合には `#concatSpeech` を使用してください。

### 参照資料への出力

<pre><code>[#noCopy:&lt;<a href="#param-shape-name">オブジェクト名</a>&gt;]

[#noCopySlide]</code></pre>

- `#noCopy` は指定したオブジェクトを参照資料に出力しません。
- `#noCopySlide` はそのスライドを参照資料に出力しません。

---

## 8. パラメーター仕様

<a id="param-required"></a>
<a id="param-optional"></a>
### 必須・省略可能

書式では `<パラメーター>` が必須、`(パラメーター)` が省略可能です。省略可能な引数は、指定しない場合でも後続の引数を使うために `:` の位置を保ちます。以下の書式表記は `clsNarraSyntax` の構文定義に従っています。

<a id="param-speech-text"></a>
### 読み上げテキスト

`#speech` の読み上げ内容です。省略すると、ノート本文などから処理されたテキストが使われます。

<a id="param-shape-name"></a>
### 図形名

対象となるスライド上の図形名です。モーション系では From図形名は省略可能、To図形名は必須です。

<a id="param-movie-name"></a>
### 動画オブジェクト名

スライド上にある動画オブジェクトの名前です。動画ディレクティブでは必須です。

<a id="param-sound-name"></a>
### 音声オブジェクト名

プレゼンテーション内にある音声オブジェクトの名前です。音声ディレクティブでは必須です。

<a id="param-delay"></a>
### 遅延・期間

遅延はアニメーションや再生を開始するまでの秒数です。`0`～`59` の数値を指定できます。省略した場合は、ディレクティブごとの既定値を使用します。

<a id="param-duration"></a>
### 期間

アニメーションまたは無音待機の長さを秒数で指定します。`0`～`59` の数値を指定できます。省略した場合は、ディレクティブごとの既定値を使用します。

<a id="param-trigger"></a>
### トリガー

| 値 | 意味 |
|---|---|
| `After` | 直前の動作が終わってから実行 |
| `With` | 直前の動作と同時に実行 |
| `Click` | クリックまたは Enter で実行 |

既定トリガーはディレクティブごとに異なります。各節の説明を参照してください。`#speech`、`#se`、`#play`、`#playWith`、`#playPause` では、引数の間に空欄が必要です。トリガーだけを指定する例：

```text
[#speech:文章:::Click]

[#se:効果音:::With]

[#show:図形名:::Click]
```

<a id="param-direction"></a>
### 方向

`#slideIn` と `#slideOut` で使う方向です。`Left`、`Right`、`Up`、`Down` のいずれかを指定します。

<a id="param-options"></a>
### ポインターオプション

`#p` のオプションには `KeepFrom` を指定できます。ポインターの移動元を残して終了します。

<a id="param-motion-options"></a>
### モーションオプション

`#motion` で指定できるオプションです。

| 引数 | 値 | 動作 |
|---|---|---|
| Fromオプション | `HideFrom` | From図形を表示せずに開始 |
| Fromオプション | `KeepFrom` | 終了後もFrom図形を残す |
| Toオプション | `HideTo` | 終了後にTo図形を表示しない |
| サイズオプション | `KeepSize` | 図形の拡大・縮小を行わない |

<a id="param-smoothing"></a>
### 滑らかさ

`#p`、`#motion`、`#motionIn`、`#motionOut`、`#move` で指定できます。

| 値 | 動作 |
|---|---|
| `SmoothStart` | 滑らかに開始 |
| `SmoothEnd` | 滑らかに終了 |
| `SmoothBoth` | 滑らかに開始・終了 |
| `SmoothBounce` | 滑らかに開始し、行き過ぎて戻る |
| `BounceEnd` | 行き過ぎて戻る |

<a id="param-emphasis"></a>
### 強調効果

効果欄があるアニメーションディレクティブで指定できます。

| 値 | 効果 |
|---|---|
| `Pulse` | パルス |
| `ColorPulse` | カラーパルス |
| `Spin` | スピン |
| `Seesaw` | シーソー |
| `Wave` | ウェーブ |

`#move` では `Wave` を指定できません。

<a id="param-engine"></a>
### 音声合成エンジン・ポート・話者

- エンジン名は NarraMaker に設定されている名前を指定します。
- ポート番号は5桁の数字です。
- `#speaker` のモデル名は必須、スタイル名は省略可能です。

<a id="param-numeric"></a>
### 音声合成の数値設定

| パラメーター | 許容範囲 |
|---|---|
| 話速（`#speed`） | 0.50～2.00 |
| テンポの緩急（`#tempoDynamics`） | 0.00～2.00 |
| 音高（`#pitch`） | -0.15～0.15 |
| 音量（`#volume`） | 0.00～2.00 |
| 開始前／終了後の無音時間（`#preGap` / `#postGap`） | 0.00～1.50秒 |
| 抑揚・感情表現の強さ（`#speechIntonation`） | 0.00～2.00。既定値は1.00。 |
| 音声中の間（`#speechPause`） | 0.00～2.00。既定値は1.00。 |

### 図形名・オブジェクト名

スライド上の図形名を指定します。`#show`、`#hide`、`#slideIn`、`#slideOut` などは対象図形が必要です。音声・動画ディレクティブには、それぞれ該当するメディアオブジェクト名を指定します。
