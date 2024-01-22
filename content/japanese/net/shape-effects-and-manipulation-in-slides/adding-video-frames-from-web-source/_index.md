---
title: Aspose.Slides for .NET を使用したビデオ フレームの埋め込みチュートリアル
linktitle: Aspose.Slides を使用して Web ソースからプレゼンテーション スライドにビデオ フレームを追加する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、ビデオ フレームを PowerPoint スライドにシームレスに埋め込む方法を学びます。マルチメディアを使用してプレゼンテーションを簡単に強化します。
type: docs
weight: 20
url: /ja/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---
## 導入
ダイナミックなプレゼンテーションの世界では、マルチメディア要素を組み込むことでエンゲージメントが大幅に向上し、インパクトのあるメッセージを伝えることができます。これを実現する強力な方法の 1 つは、ビデオ フレームをプレゼンテーション スライドに埋め込むことです。このチュートリアルでは、Aspose.Slides for .NET を使用してこれをシームレスに実現する方法を検討します。 Aspose.Slides は、開発者が PowerPoint プレゼンテーションをプログラムで操作できるようにする堅牢なライブラリであり、スライドの作成、編集、拡張のための広範な機能を提供します。
## 前提条件
チュートリアルに入る前に、次のものが整っていることを確認してください。
1.  Aspose.Slides for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Slides for .NET ドキュメント](https://reference.aspose.com/slides/net/).
2. サンプル ビデオ ファイル: プレゼンテーションに埋め込むビデオ ファイルを準備します。提供されている例は、「Wildlife.mp4」という名前のビデオで使用できます。
## 名前空間のインポート
.NET プロジェクトに、Aspose.Slides 機能を活用するために必要な名前空間を含めます。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Aspose.Slides for .NET を使用してプレゼンテーション スライドにビデオ フレームを埋め込むプロセスを管理しやすい手順に分けてみましょう。
## ステップ 1: ディレクトリをセットアップする
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
//ディレクトリが存在しない場合は作成します。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
「Your Document Directory」と「Your Media Directory」をプロジェクト内の適切なパスに置き換えてください。
## ステップ 2: プレゼンテーション オブジェクトを作成する
```csharp
using (Presentation pres = new Presentation())
{
    //最初のスライドを取得する
    ISlide sld = pres.Slides[0];
```
新しいプレゼンテーションを初期化し、ビデオ フレームを埋め込むための最初のスライドにアクセスします。
## ステップ 3: プレゼンテーションにビデオを埋め込む
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
を活用してください。`AddVideo`プレゼンテーションにビデオを埋め込むメソッドを使用して、ファイル パスと読み込み動作を指定します。
## ステップ 4: ビデオ フレームを追加する
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
スライド上にビデオ フレームを作成し、その位置と寸法を定義します。
## ステップ 5: ビデオ設定を構成する
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
ビデオ フレームを埋め込みビデオに関連付け、再生モードを設定し、好みに応じて音量を調整します。
## ステップ 6: プレゼンテーションを保存する
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
変更したプレゼンテーションを埋め込みビデオ フレームとともに保存します。
## 結論
おめでとう！ Aspose.Slides for .NET を使用してプレゼンテーション スライドにビデオ フレームを埋め込む方法を学習しました。この機能により、聴衆を魅了するダイナミックで魅力的なプレゼンテーションを作成するためのエキサイティングな可能性が開かれます。
## よくある質問
### Aspose.Slides を使用してさまざまな形式のビデオを埋め込むことはできますか?
はい、Aspose.Slides はさまざまなビデオ形式をサポートしているため、プレゼンテーションの柔軟性が保証されます。
### 埋め込みビデオの再生設定を制御するにはどうすればよいですか?
を調整します。`PlayMode`そして`Volume`ビデオ フレームのプロパティを使用して、再生動作をカスタマイズします。
### Aspose.Slides は .NET の最新バージョンと互換性がありますか?
Aspose.Slides は、最新の .NET フレームワークとの互換性を維持するために定期的に更新されます。
### Aspose.Slides を使用して 1 つのスライドに複数のビデオを埋め込むことはできますか?
はい、スライドに追加のビデオ フレームを追加することで、複数のビデオを埋め込むことができます。
### Aspose.Slides 関連のクエリのサポートはどこで見つけられますか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのために。