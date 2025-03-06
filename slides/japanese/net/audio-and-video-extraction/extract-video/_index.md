---
title: Aspose.Slides for .NET を使用してスライドからビデオを抽出する方法
linktitle: スライドからビデオを抽出する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを抽出する方法を学びます。このステップ バイ ステップ ガイドでは、プロセスが簡素化されます。
weight: 14
url: /ja/net/audio-and-video-extraction/extract-video/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Aspose.Slides for .NET は、.NET 環境で PowerPoint プレゼンテーションを操作できる強力なライブラリです。このライブラリが提供する便利な機能の 1 つは、スライドからビデオを抽出する機能です。このステップ バイ ステップ ガイドでは、Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを抽出する方法を説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides for .NETがインストールされている必要があります。[Webサイト](https://purchase.aspose.com/buy).

- PowerPoint プレゼンテーション: 抽出するビデオを含む PowerPoint プレゼンテーション (例: Video.pptx) を準備します。

## 名前空間のインポート

Aspose.Slides for .NET を使用するには、必要な名前空間をインポートする必要があります。手順は次のとおりです。

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

ここで、スライドからビデオを抽出するプロセスを複数のステップに分解してみましょう。

## ステップ1: ドキュメントディレクトリを設定する

```csharp
string dataDir = "Your Document Directory";
```

交換する`"Your Document Directory"` PowerPoint プレゼンテーションが保存されているディレクトリへのパスを入力します。

## ステップ2: プレゼンテーションを読み込む

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

このコードは、PowerPoint プレゼンテーション ファイルを表す Presentation オブジェクトを初期化します。

## ステップ3: スライドと図形を反復処理する

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

ここでは、プレゼンテーションの各スライドをループし、最初のスライドの図形を反復処理します (必要に応じて変更します)。

## ステップ4: シェイプがビデオフレームであるかどうかを確認する

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

この手順では、スライド上の図形がビデオ フレームであるかどうかを確認します。

## ステップ5: ビデオデータを抽出する

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

このコードは、コンテンツ タイプやバイナリ データなど、ビデオに関する情報を抽出します。

## ステップ6: ビデオを保存する

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

最後に、この手順では、指定されたディレクトリ内の新しいファイルにビデオを保存します。

これらの手順を完了すると、Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを正常に抽出できるようになります。

## 結論

Aspose.Slides for .NET は、PowerPoint プレゼンテーションの操作プロセスを簡素化し、スライドからビデオを抽出するなどのタスクを簡単に実行できるようにします。このステップ バイ ステップ ガイドに従い、Aspose.Slides ライブラリを利用することで、強力な PowerPoint 機能を使用して .NET アプリケーションを強化できます。

## よくある質問（FAQ）

### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、コンテンツの作成、編集、抽出など、.NET アプリケーションで PowerPoint プレゼンテーションを操作できるようにするライブラリです。

### Aspose.Slides for .NET のドキュメントはどこにありますか?
ドキュメントは以下からご覧いただけます[ここ](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET は無料試用版として利用できますか?
はい、無料試用版を入手できます。[ここ](https://releases.aspose.com/).

### Aspose.Slides for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスを申請するには[このリンク](https://purchase.aspose.com/temporary-license/).

### Aspose.Slides for .NET のサポートはどこで受けられますか?
サポートについては、[Aspose.Slides フォーラム](https://forum.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
