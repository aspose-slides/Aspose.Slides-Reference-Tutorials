---
title: Aspose.Slides - .NET プレゼンテーションへの埋め込みビデオの追加
linktitle: Aspose.Slides - .NET プレゼンテーションへの埋め込みビデオの追加
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、埋め込みビデオでプレゼンテーションを強化します。シームレスな統合については、ステップバイステップのガイドに従ってください。
type: docs
weight: 19
url: /ja/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## 導入
ダイナミックなプレゼンテーションの世界では、マルチメディア要素を統合することでエンゲージメントを大幅に高めることができます。 Aspose.Slides for .NET は、埋め込みビデオ フレームをプレゼンテーション スライドに組み込むための強力なソリューションを提供します。このチュートリアルでは、シームレスなエクスペリエンスを確保するために各ステップを詳しく説明し、プロセスをガイドします。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
-  Aspose.Slides for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[リリースページ](https://releases.aspose.com/slides/net/).
- メディア コンテンツ: プレゼンテーションに埋め込みたいビデオ ファイル (例: 「Wildlife.mp4」) を用意します。
## 名前空間のインポート
まず、.NET プロジェクトに必要な名前空間をインポートします。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ステップ 1: ディレクトリをセットアップする
プロジェクトにドキュメント ファイルとメディア ファイルに必要なディレクトリがあることを確認してください。
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
//ディレクトリが存在しない場合は作成します。
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## ステップ 2: プレゼンテーション クラスをインスタンス化する
PPTX ファイルを表す Presentation クラスのインスタンスを作成します。
```csharp
using (Presentation pres = new Presentation())
{
    //最初のスライドを取得する
    ISlide sld = pres.Slides[0];
```
## ステップ 3: プレゼンテーション内にビデオを埋め込む
プレゼンテーション内にビデオを埋め込むには、次のコードを使用します。
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## ステップ 4: ビデオ フレームを追加する
次に、ビデオ フレームをスライドに追加します。
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## ステップ 5: ビデオのプロパティを設定する
ビデオをビデオ フレームに設定し、再生モードと音量を構成します。
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## ステップ 6: プレゼンテーションを保存する
最後に、PPTX ファイルをディスクに保存します。
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
プレゼンテーションに埋め込むビデオごとにこれらの手順を繰り返します。
## 結論
おめでとう！ Aspose.Slides for .NET を使用して、埋め込みビデオ フレームをプレゼンテーションに追加することに成功しました。この動的な機能により、プレゼンテーションを新たな高みに引き上げ、スライドにシームレスに統合されたマルチメディア要素で聴衆を魅了します。
## よくある質問
### プレゼンテーションのスライドにビデオを埋め込むことはできますか?
はい、インデックスを変更することで任意のスライドを選択できます。`pres.Slides[index]`.
### どのビデオ形式がサポートされていますか?
Aspose.Slides は、MP4、AVI、WMV などのさまざまなビデオ形式をサポートしています。
### ビデオ フレームのサイズと位置をカスタマイズできますか?
絶対に！パラメータを調整します`AddVideoFrame(x, y, width, height, video)`必要に応じて。
### 埋め込むことができるビデオの数に制限はありますか?
埋め込みビデオの数は通常、プレゼンテーション ソフトウェアの容量によって制限されます。
### さらに支援を求めたり、自分の経験を共有したりするにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのために。