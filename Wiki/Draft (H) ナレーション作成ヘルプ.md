  ナレーション作成ヘルプ
  <a id="index"/>
  # 📚 目次

  ## [1. 準備](#1)  
  ナレーションつくりの準備を説明します。

  ## [2. ナレーションの作成](#2)  
  テキストを音声化するまでの基本操作を説明します。

  ## [3. 各種の調整](#3)  
  読み仮名の調整や話速の調整などを説明します。
  -  [3.1 クローズドキャプションの長さ](#3.1)
  -  [3.2 読点「、」の調整](#3.2)
  -  [3.3 読点「、」・中黒「・」が多い文](#3.3)
  -  [3.4 音声の変更](#3.4)
  -  [3.5 声の速さや音量を調整](#3.5)
  -  [3.6 読み上げの余白時間の調整](#3.6)
  -  [3.7 読み仮名の調整](#3.7)
  -  [3.8 アクセントの調整](#3.8)
  -  [3.9 音声を作り直す](#3.9)
  -  [3.10 クローズドキャプションの ON/OFF 設定](#3.10)

  ## [4. ナレーション小技](#4)  
  音声を使った演出効果を紹介します。
  - [4.1 クローズドキャプションで音声とは別な事を言う](#4.1)
  - [4.2 音声にエコーをかける](#4.2)
  - [4.3 複数の人が同時に話す・話を被せる](#4.3)

  ## [5. 共有と制約](#5)  
  制作したプレゼンテーションファイルを共有する場合の注意事項を説明します。

  ---
  <a id="1"></a>
  # 1. 準備

  ナレーション作成の準備として下記２点を説明します。  
  - 音声合成アプリの起動・ピン止め  
  - 音声合成の基本設定  


  [目次に戻る](#index)<br><br>

  ## 1.1 音声合成アプリの起動・ピン止め
  音声ナレーションを作成するためには、音声合成アプリが起動している必要があります。  
  また、音声の生成速度が落ちないようにアブリのウィンドウが前面に出ている必要があります。

  1. **音声合成アプリを起動**  
      <img width="300" alt="image" src="https://github.com/user-attachments/assets/56b51a02-1bab-486b-b5a2-05e68270f396" />  


  2. **音声合成アプリのウィンドウを ピン止め**（前面に設定）  
      ピン止めすると音声合成アプリのウィンドウが常に前面に表示されるようになります。たいていの場合、PowerPoint画面を操作しにくくなります。  
      <img width="300" alt="image" src="https://github.com/user-attachments/assets/39cdfc77-6614-475c-beae-bb0a9a96780d" />  

  3. **ウィンドウを小さくする**  
      ウィンドウを限りなく小さくして画面の隅に置いておくと、邪魔になりません。  
      ウィンドウの最小化も試す価値はあります。（最小化しても性能が落ちないことが多いです）  
      <img width="240" height="28" alt="image" src="https://github.com/user-attachments/assets/5ffb85fe-887a-475e-b977-1e5d7a9a222c" />  

  <br><br>

  > [!IMPORTANT]  
  > - VOICEVOX系音声合成アブリは、他のウィンドウの背面にいると処理性能が落ちてしまいます。これは、WindowsによってCPU/GPUの優先順位を下げられてしまうためです。

  [目次に戻る](#index)<br><br>

  ## 1.2 音声合成の基本設定

  デフォルトで使用する **音声合成アプリ** や **音声合成モデル**、その他の調整項目を設定します。  
  このデフォルト値はプレゼンテーションファイル内だけに適用され、ほかのプレゼンテーションファイルには影響しません。


  1. NarraMaker の設定画面を開きます（リボン [設定等] > [基本設定] ）  
      <img width="622" height="98" alt="ribbon_config" src="https://github.com/user-attachments/assets/2b812302-c060-4228-adc8-7927632fe180" />  

      <img width="400" alt="image" src="https://github.com/user-attachments/assets/da650e95-2aa7-4fb2-8b86-b499a34a8bd4" />

  2. **音声合成エンジン** を選択      

  3. **音声合成モデル** を選択 ... [変更]ボタン押下  

  4. 必要に応じて話速などの調整項目を設定します  

  5. **[保存]** ボタン を押します 

  <br><br>

  > [!WARNING]  
  > - **[保存]** は、設定内容をプレゼンテーションの中に埋め込みます。  
  > プレゼンテーションファイルの保存は行いません。

  > [!NOTE]  
  > - 話速などの **調整項目** は、音声成合成アプリの設定項目を NarraMaker で入力できるようにしているものです。調整項目の説明は、音声合成アプリのヘルプで確認できます。  

  [目次に戻る](#index)<br><br>

  <a id="2"></a>
  # 2. 作成
  この章では以下のステップを説明します。
  - 読み上げるテキストの入力（スライドノート編集）
  - 音声合成処理の実行（アニメーション生成）
  - 生成した音声の確認（プレビュー）

  [目次に戻る](#index)<br><br>

  ## 2.1 読み上げるテキストの入力


  1. **[スライドノート編集]** を押してスライドノートエディターを開きます。  
      <img width="274" height="98" alt="ribbon_slide_note_editor" src="https://github.com/user-attachments/assets/7090b4c8-068e-48ef-85c2-b426c41ee7d3" />  
      <img width="274" alt="image" src="https://github.com/user-attachments/assets/12550195-be2e-4c2b-82b7-19c32f1d9983" />
      

  2. 読み上げたい文章を入力して、**[生成]** または **[保存]** ボタンを押します。  
    **[生成]** を押した場合は、自動的に 次項 2.2 に進みます。

  <br><br>

  > [!WARNING]  
  > - **[保存]** は、テキストをスライドノートに埋め込みます。プレゼンテーションファイルの保存は行いません。

  > [!NOTE]  
  > - **[生成]** ボタンを押すと、保存とアニメーション生成が同時に実行されます。  
  > - 右上の **[+] [-]** ボタンで文字サイスを変更できます。

  [目次に戻る](#index)<br><br>

  ## 2.2 音声合成の実行（アニメーション生成）
  1. 音声生成ダイアログを開く ... リボン **[アニメーション生成]** を押下  
      <img width="274" height="98" alt="ribbon_generate_animation" src="https://github.com/user-attachments/assets/d965d832-ced4-4929-85bf-4a515f3d6462" />  

      <img width="274" alt="image" src="https://github.com/user-attachments/assets/c7818641-b06c-4843-a40f-9470a472f585" />    

    ※ 音声合成が済んでいる場合は表示されません。  
      
  2. 音声合成を開始する ... オレンジ色の **[生成する]** ボタンを押下    

  3. 進捗を眺めながら終わるのを待つ

  > [!NOTE]  
  > スライドノート内のテキストが音声合成済みの場合は、「NarraMaker 音声生成」ダイアログは表示されません。

  [目次に戻る](#index)<br><br>

  ## 2.3 合成した音声の確認（プレビュー）
  - リボンの **[プレビュー]** を押すと生成した音声が再生されます。  
    <img width="274" height="98" alt="ribbon_preview" src="https://github.com/user-attachments/assets/8e81ff19-125c-48be-bb0f-61ddeeabb298" />  

  - この音声はスライドショーでも同じように再生されます。

  > [!WARNING]  
  > - 音声合成したスライドは、自動進行のスライドになります。  
  > - 手動進行のスライドにしたい場合は `[#Click]` ディレクティブを追加します。

  > [!TIP]  
  > - 次のような場合は **音声合成アプリ** の画面で音声合成と視聴を行うと効率的です。  
  >   - 大きなテキストの一部分だけを繰り返し視聴・調整したい  
  >   - 音声合成モデルや話速などの調整を色々試したい  

  [目次に戻る](#index)<br><br>

  <a id="3"></a>
  # 3. 調整

  -  3.1 クローズドキャプションの長さ
  -  3.2 読点「、」の調整
  -  3.3 読点「、」・中黒「・」が多い文
  -  3.4 音声の変更
  -  3.5 声の音量を調整
  -  3.6 読み上げの余白時間の調整
  -  3.7 読み仮名の調整
  -  3.8 アクセントの調整
  -  3.9 音声を作り直す
  -  3.10 クローズドキャプションの ON/OFF 設定

  <a id="3.1"></a>
  ## 3.1 クローズドキャプションの長さ

  クローズドキャプションのテキストが長いと感じるときは、**[#ConcatSpeech]** を使って調整できます。また、**行中ポインター** を使用した場合もクローズドキャプションが調整されます。

  - **[#ConcatSpeech]** の使用例  
    音声は一行の文として読み上げられますが、クローズドキャプションは行単位に表示されます。
    ```
    [#ConcatSpeech]
      合成された音声の
      息継ぎや
      イントネーションは、
      音声合成アプリによって
      違いがあります。
    [#EndConcatSpeech]
    ```
  - 行中ポインター の使用例  
    [#P]はモーションポインターのディレクティブで、行の途中にいれた[#P]を行中ポインターと呼びます。行中ポインターはクローズドキャプションの区切りになります。
    ```
    合成された音声の[#P]息継ぎや[#P]イントネーションは、[#P]音声合成アプリによって[#P]違いがあります。
    ```
    
  > [!IMPORTANT]
  > **[#ConcatSpeech]** には、いくつかの制約があります。（[ディレクティブヘルプ]()を参照）

  [目次に戻る](#index)<br><br>

  <a id="3.2"></a>
  ## 3.2 読点「、」の調整
  息継ぎの間が多い、または息継ぎなしで話しているような違和感を持ったら、読点「、」の有無・位置を調整します。  
  音声合成アプリによっては、読点が「、」がなくても全体的に自然な読み上げになりますが、読点が「、」がなければ息継ぎなしになるアプリもあります。

  - 間が多くてぎこちない。または、息継ぎしていない印象。  
    　↓
  - いったん読点「、」を全部抜いて聴いてみる。
  - 適度に読点「、」を入れる。

  <a id="3.3"></a>
  ## 3.3 読点「、」・中黒「・」が多い文
  「赤、青、黄色」や「白・黒」のように単語を列挙する文は、読点「、」や中点「・」が多くなりがちです。そのまま読ませると、間が多くて気になることがあります。
  - 読ませる文としては、「や」・「または」などの接続詞に置き換えてみます。
    ```
    選択肢は 赤、青、黄色 です。
    　↓
    選択肢は 赤や青、黄色 です。  
    ```

    ```
    使えるのは 白・黒 どちらかです。
    　↓
    使えるのは 白か黒、どちらかです。
    使えるのは 白または黒、どちらかです。
    ```
  [目次に戻る](#index)<br><br>


  <a id="3.4"></a>
  ## 3.4 音声の変更
  ナレーションの途中で音声を変えたい場合は、[#Speaker] ディレクティブを使用します。音声合成アプリも変更する場合は [#Engine] または [#Port] を使用します。

    ```
    [#Speaker:モデル名:スタイル名]
    ```

    ```
    [#Engine:AivisSpeech]
    [#Speaker:にせ:ノーマル]
    これは AivisSpeech の「にせ」の声です。

    [#Speaker:morioki:ノーマル]
    これは AivisSpeech の「morioki」の声です。

    [#Engine:VOICEVOX]
    [#Speaker:ずんだもん:ノーマル]
    これは VOICEVOX の「ずんだもん」の声です。
    
    ```

  [目次に戻る](#index)<br><br>

  <a id="3.5"></a>
  ## 3.5 声の速さや音量を調整
    ```
    [#Volume:音量]
    ```

  [目次に戻る](#index)<br><br>

  <a id="3.6"></a>
  ## 3.6 読み上げの余白時間の調整
  音声合成アプリやモデルによっては、行間の無音時間が短くてせっかちに聞こえる場合があります。違和感があるときに調整しましょう。
  また、大事なことをゆっくり言う場面では、無音時間を少し長めにすると良いでしょう。  
  - **[#PreGap][#PostGap]** は、それ以降のテキストに反映されます。
    ```
    音声の後に0.5秒の間を置く。
    [#PostGap:0.5]

    元に戻す。
    [#PostGap]  
    ```

  - **[#Quiet]** はその場だけの無音時間です。
    ```
    [#Quiet:1]
    ```

  [目次に戻る](#index)<br><br>

  <a id="3.7"></a>
  ## 3.7 読み仮名の調整
  音声合成アプリが意図通りに単語を読まない場合は、読み仮名を指定しましょう。 スライドノート内で音読み仮名を指定する方法と、音声合成アプリの辞書を使う方法があります。

  1. **スライドノート内で読み仮名を指定する**  
      ```
      このアプリは {NarraMaker|ならめーかー} と言います。  
      こんにちは、{渡部|わたなべ} です。 
      こんにちは、{渡部|わたべ} です。 
      ```

    1. **音声合成アプリの辞書を使う**  
      頻繁に使用する読み仮名は辞書に登録しておくと効率的です。  
      音声合成アプリの [設定] > [読み方アクセント辞書] を開いて登録します。
      <img width="300" alt="image" src="https://github.com/user-attachments/assets/5474f1c1-33c6-474e-9506-878dbca9cea6" /> 

  > [!IMPORTANT]
  > **読み方＆アクセント辞書**を変更した後は、その単語を使っているスライドの音声を作り直す必要があります。
    
  [目次に戻る](#index)<br><br>


  <a id="3.8"></a>
  ## 3.8 アクセントの調整
  単語のイントネーションに違和感がある場合は、音声合成アプリの **読み方＆アクセント辞書** に単語を登録してアクセントを調整します。

  - 音声合成アプリの **読み方＆アクセント辞書**
  <img width="300" alt="image" src="https://github.com/user-attachments/assets/17de8dff-cec6-4ae6-87e4-ee7f8b6d3b90" />

  > [!IMPORTANT]
  > **読み方＆アクセント辞書**を変更した後は、その単語を使っているスライドの音声を作り直す必要があります。

  [目次に戻る](#index)<br><br>

  <a id="3.9"></a>
  ## 3.9 音声を作り直す
  **読み方＆アクセント辞書**を変更した後は、その単語を使っているスライドの音声を作り直す必要があります。  

  - リボンの **[音声合成]** を使用すると、生成済みの音声を破棄して改めて音声が生成されます。  

    <img width="622" height="98" alt="ribbon_generate_audio" src="https://github.com/user-attachments/assets/6fda778b-32b6-4d1e-ba61-3cdfdf5223e5" />

  [目次に戻る](#index)<br><br>

  <a id="3.10"></a>
  ## 3.10 クローズドキャプションの ON/OFF 設定
  クローズドキャプションは、プレゼンテーションファイル全体で ON/OFF する方法と、スライドノート内で局所的に ON/OFF することができます。

  - プレゼンテーションファイル全体で設定する  
    NarraMaker基本設定を開いて、「クローズドキャプションを生成しない」のチェックをON/OFFします。 
      <img width="622" height="98" alt="ribbon_config" src="https://github.com/user-attachments/assets/2b812302-c060-4228-adc8-7927632fe180" />  

    <img width="691" height="316" alt="image" src="https://github.com/user-attachments/assets/60966eb2-b3ce-447d-a629-1c35cc3d0642" />

  - スライドノート内で局所的に ON/OFF を変更
    ```
    [#Cc:off]
    ここからの読み上げは、クローズドキャプションがありません。

    [#Cc:on]
    ここからの読み上げは、クローズドキャプションが表示されます。

    [#Cc]
    on/offを省略するとプレゼンテーションファイル全体の設定に戻ります。
    ```

  [目次に戻る](#index)<br><br>

  <a id="4"></a>
  # 4. 小技

  - クローズドキャプションで音声とは別な事を言う
  - 音声にエコーをかける
  - 複数の人が同時に話す・話を被せる

  <a id="4.1"></a>
  ## 4.1 クローズドキャプションで音声とは別な事を言う
  - 読み仮名指定の {表示文字列|読み仮名} 構文を使います。  
    ```
    {そろそろ帰れ|その時計さん、仕事がはかどってますなあ。}
    ```
  - 実はカナを指定する機能ではなく、表示する文字列と音声合成に入れる文字列を分けて指定する機能なのです。上記はクローズドキャプションに「そろそろ帰れ」と表示されます。

  [目次に戻る](#index)<br><br>

  <a id="4.2"></a>
  ## 4.2 音声を反響させる（リバーブ/エコー）
  - リバーブ(残響)  
    **[#Speech]** ディレクティブで、同じテキストをほんの少し時間をずらして読み上げます。
    ```
    [#Speaker:阿井田 茂:ノーマル]
    西暦2025年、そう遠くない未来
    [#Speech:西暦2025年、そう遠くない未来:0.02::With]
    ```
  - エコー(反響)  
    **[#Speech]** **[#Volume]** ディレクティブで、声を小さくしながら徐々に時間をずらします。
    ```
    [#Speaker:morioki:ノーマル]
    終わってた！
    [#Volume:0.3]  [#Speech:終わってた！:0.2::With]
    [#Volume:0.2]  [#Speech:終わってた！:0.6::With]
    [#Volume:0.1]  [#Speech:終わってた！:1.2::With]
    [#Volume:0.05] [#Speech:終わってた！:2::With]
    [#Volume]
    ```
  > [!NOTE]
  > - ずらし加減と音量調節がポイントです。
  > - 用途がかなり限定的です。
  
  [目次に戻る](#index)<br><br>

  <a id="4.3"></a>
  ## 4.3 複数の人が同時に話す・話を被せる
    - **[#Speaker]** と **[#Speech]** で、複数名の声を重ねて再生します。  
      ```
      [#Speaker:にせ:ノーマル]
      [#Speech:今日も一日頑張りましょう:::With]

      [#Speaker:阿井田 茂:ノーマル]
      [#Speech:今日も一日頑張りましょう:::With]

      [#Speaker:morioki:ノーマル]
      [#Speed:1.2]
      [#Speech:{(早く帰ろ...)|今日も一日頑張りましょう}:::With]
      ```

  [目次に戻る](#index)<br><br>

  <a id="5"></a>
  # 5. 共有と制約
  制作中または完成したプレゼンテーションファイルを、他の人と共有する場合、以下の点にご注意ください。 なお、PowerPoint for Mac はアニメーションの機能差が大きいため対象外です。

  1. スライドショー  
      ほかのコンピューター上でもスライドショーやスライドの編集が可能です。 NarraMaker で生成された音声・アニメーションは、完全に PowerPoint の機能だけ使用しており、音声データもプレゼンテーションファイルに埋め込まれています。
  2. スライド編集
  3. 
  4. 

  - プレゼンテーションファイル(.pptx)は、ほかの Windows コンピューター上でも、PowerPoint がインストールされていれば、そのままスライドショーが可能です。
  - アニメーションだけであればほかの
  - コンピューター環境に依存する情報
  - 音声合成のキャッシュファイル
  - 音声合成のキャッシュファイルの復元

  - SharePoint/Teams上のプレゼンテーションファイル
  - 読み取り専用モードのプレゼンテーションファイル

  [目次に戻る](#index)<br><br>



  <img width="622" height="98" alt="ribbon_add_pointer" src="https://github.com/user-attachments/assets/ba8323f4-833c-4b7d-be01-9c2301e8b0c7" />
  <img width="622" height="98" alt="ribbon_cancellation_pointer" src="https://github.com/user-attachments/assets/1c64b8a5-cbeb-41f8-8723-d70ab2ce05f8" />
  <br><br>


  <img width="274" height="98" alt="ribbon_export_data" src="https://github.com/user-attachments/assets/14a6e0e9-f58c-42b3-ab92-378f8cb2077f" />
  <img width="274" height="98" alt="ribbon_export_movie" src="https://github.com/user-attachments/assets/5220d4f5-7d5f-4fea-8076-df42bfb935b6" />
  <img width="622" height="98" alt="ribbon_filter" src="https://github.com/user-attachments/assets/8a04f056-4b58-435d-8e87-b02818da7f1b" />
  <img width="622" height="98" alt="ribbon_filter_text" src="https://github.com/user-attachments/assets/126807dc-72ca-4c55-919f-3a1b72f1a801" />
  <img width="274" height="98" alt="ribbon_fit_to_window" src="https://github.com/user-attachments/assets/1ff6c098-83e4-47ba-9347-85fec0191d0e" />


  <img width="622" height="98" alt="ribbon_group_pointer" src="https://github.com/user-attachments/assets/99623476-949b-4116-83e6-5dd641f3e118" />
  <img width="274" height="98" alt="ribbon_information" src="https://github.com/user-attachments/assets/dab0b7c1-8180-490b-9b0b-6e6870b0eaac" />
  <img width="622" height="98" alt="ribbon_motion_paths" src="https://github.com/user-attachments/assets/094967b0-0e48-4382-a2d4-0c5ab8bf5366" />

  <img width="274" height="98" alt="ribbon_remove_animation" src="https://github.com/user-attachments/assets/bff9dea4-d681-46d6-8945-cc4ffeedef88" />
  <img width="622" height="98" alt="ribbon_rename" src="https://github.com/user-attachments/assets/88a977ac-b125-42a5-95f1-77143ccc5665" />
  <img width="622" height="98" alt="ribbon_reset_filter" src="https://github.com/user-attachments/assets/869d5b96-b9f9-4006-88f5-bb459fa55f45" />
  <img width="622" height="98" alt="ribbon_shape_position" src="https://github.com/user-attachments/assets/cc3d3c60-7e44-4f79-8bc8-9761562e4870" />
  <img width="622" height="98" alt="ribbon_show_names" src="https://github.com/user-attachments/assets/dac4022d-6fec-4b10-b20c-5846e20ede79" />
  <img width="622" height="98" alt="ribbon_show_pointer_order" src="https://github.com/user-attachments/assets/cbf12dd6-66a6-42af-9b84-72ec7e6e4e4d" />
  <img width="274" height="98" alt="ribbon_show_work_window" src="https://github.com/user-attachments/assets/fa6c1c33-2417-4d0e-a414-e95a1025e454" />
