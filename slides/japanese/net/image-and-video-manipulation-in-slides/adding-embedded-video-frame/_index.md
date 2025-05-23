---
"description": "Aspose.Slides for .NET を使えば、埋め込みビデオでプレゼンテーションをさらに魅力的に演出できます。ステップバイステップのガイドに従って、シームレスに統合しましょう。"
"linktitle": "Aspose.Slides - .NET プレゼンテーションに埋め込みビデオを追加する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "Aspose.Slides - .NET プレゼンテーションに埋め込みビデオを追加する"
"url": "/ja/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET プレゼンテーションに埋め込みビデオを追加する

## 導入
プレゼンテーションという動的な世界では、マルチメディア要素を組み込むことで、エンゲージメントを大幅に高めることができます。Aspose.Slides for .NET は、プレゼンテーションスライドに埋め込みビデオフレームを組み込むための強力なソリューションを提供します。このチュートリアルでは、各ステップを詳しく説明し、シームレスなエクスペリエンスを実現します。
## 前提条件
チュートリアルに進む前に、次のものを用意してください。
- Aspose.Slides for .NET ライブラリ: ライブラリを以下のサイトからダウンロードしてインストールします。 [リリースページ](https://releases。aspose.com/slides/net/).
- メディア コンテンツ: プレゼンテーションに埋め込みたいビデオ ファイル (例: 「Wildlife.mp4」) を用意します。
## 名前空間のインポート
まず、.NET プロジェクトに必要な名前空間をインポートします。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## ステップ1: ディレクトリを設定する
プロジェクトにドキュメントとメディア ファイルに必要なディレクトリがあることを確認します。
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// ディレクトリがまだ存在しない場合は作成します。
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## ステップ2: プレゼンテーションクラスのインスタンス化
PPTX ファイルを表す Presentation クラスのインスタンスを作成します。
```csharp
using (Presentation pres = new Presentation())
{
    // 最初のスライドを取得する
    ISlide sld = pres.Slides[0];
```
## ステップ3：プレゼンテーション内にビデオを埋め込む
プレゼンテーション内にビデオを埋め込むには、次のコードを使用します。
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## ステップ4：ビデオフレームを追加する
次に、スライドにビデオ フレームを追加します。
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## ステップ5：ビデオのプロパティを設定する
ビデオをビデオ フレームに設定し、再生モードと音量を構成します。
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## ステップ6: プレゼンテーションを保存する
最後に、PPTX ファイルをディスクに保存します。
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
プレゼンテーションに埋め込むビデオごとに、これらの手順を繰り返します。
## 結論
おめでとうございます！Aspose.Slides for .NET を使用して、プレゼンテーションに埋め込みビデオフレームを追加することができました。このダイナミックな機能により、プレゼンテーションの質がさらに向上し、スライドにシームレスに統合されたマルチメディア要素で視聴者を魅了することができます。
## よくある質問
### プレゼンテーションのどのスライドにもビデオを埋め込むことはできますか?
はい、インデックスを変更することで任意のスライドを選択できます。 `pres。Slides[index]`.
### どのビデオ形式がサポートされていますか?
Aspose.Slides は、MP4、AVI、WMV など、さまざまなビデオ形式をサポートしています。
### ビデオフレームのサイズと位置をカスタマイズできますか?
絶対に！パラメータを調整してください `AddVideoFrame(x, y, width, height, video)` 必要に応じて。
### 埋め込むことができる動画の数に制限はありますか?
埋め込まれるビデオの数は、通常、プレゼンテーション ソフトウェアの容量によって制限されます。
### さらにサポートを求めたり、経験を共有したりするにはどうすればよいでしょうか?
訪問 [Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11) コミュニティのサポートとディスカッションのため。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}