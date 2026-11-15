# [NarraMaker](https://github.com/narramaker/narramaker/wiki)

PowerPoint でナレーション・アニメーション付きの動画作成を支援するツールです。  
スライドノートに記載したナレーション指示に基づいて、音声ナレーションやアニメーションを生成します。

<p><span style="font-size: 2em; color: #8B0000;"><strong>*** リリース準備中 ***</strong></span></p>

## 概要

- テキストでナレーション指示を作成（読み上げテキスト、アニメーション、効果音など）
- ナレーションに合わせて視線を誘導するモーションポインターを実装
- 手作りでは難しい移動・変形・回転を伴うモーションアニメーションを手軽に作成
- PowerPointアニメーションと統合しPowerPointだけで再生可能
- プレゼンテーションの実行は手動進行・自動進行の両方をサポート
- 保守性の高い制作サイクル (ナレーション指示の編集 → 生成 → 出力)
- 音声合成エンジン（AivisSpeech / VOICEVOX）との連携 (音声合成利用時は必須)
- コンテンツの出力形式: pptm、ppsx、mp4
- MP4再生アプリ、または PowerPoint のみでコンテンツ再生

## デモ動画
[デモ動画を見る（YouTube）](https://www.youtube.com/embed/MPhPZ0nfNtY?autoplay=1) &nbsp;&nbsp;音声が再生されます。ご注意ください。

<br>
<img width="300" alt="NarraMaker紹介 GIF-1" src="https://github.com/user-attachments/assets/d91f0262-8c15-4093-aee9-e8e6349f2bb4" /><br>

## ダウンロード
- [Download](https://github.com/narramaker/narramaker/releases)
<br>

## 現在の公開内容

- `NarraMaker.ppam`（PowerPointアドイン形式）
  - 初期機能を含むバイナリ版
  - ソースコードは整理がつき次第、別途公開予定

## 利用方法

1. PowerPointで `.ppam` を読み込み、アドインとして登録
2. リボンに追加された「NarraMaker」タブから操作
3. 詳細な使い方は今後ドキュメント化予定

