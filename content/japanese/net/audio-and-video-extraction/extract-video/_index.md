---
title: Aspose.Slides for .NET を使用してスライドからビデオを抽出する方法
linktitle: スライドからビデオを抽出
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを抽出する方法を学びます。このステップバイステップのガイドは、プロセスを簡素化します。
type: docs
weight: 14
url: /ja/net/audio-and-video-extraction/extract-video/
---

Aspose.Slides for .NET は、.NET 環境で PowerPoint プレゼンテーションを操作できるようにする強力なライブラリです。提供される便利な機能の 1 つは、スライドからビデオを抽出する機能です。このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを抽出する方法を説明します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

-  Aspose.Slides for .NET: Aspose.Slides for .NET がインストールされている必要があります。から入手できます。[Webサイト](https://purchase.aspose.com/buy).

- PowerPoint プレゼンテーション: 抽出するビデオを含む PowerPoint プレゼンテーション (例: Video.pptx) を準備します。

## 名前空間のインポート

Aspose.Slides for .NET を使用するには、必要な名前空間をインポートする必要があります。その方法は次のとおりです。

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

ここで、スライドからビデオを抽出するプロセスを複数のステップに分けてみましょう。

## ステップ 1: ドキュメント ディレクトリを設定する

```csharp
string dataDir = "Your Document Directory";
```

交換する`"Your Document Directory"`PowerPoint プレゼンテーションが配置されているディレクトリへのパスを置き換えます。

## ステップ 2: プレゼンテーションをロードする

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

このコードは、PowerPoint プレゼンテーション ファイルを表す Presentation オブジェクトを初期化します。

## ステップ 3: スライドと図形を反復処理する

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

ここでは、プレゼンテーションの各スライドをループし、最初のスライドの図形を繰り返し処理します (必要に応じて変更します)。

## ステップ 4: 形状がビデオ フレームであるかどうかを確認する

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

このステップでは、スライド上の形状がビデオ フレームであるかどうかを確認します。

## ステップ 5: ビデオ データを抽出する

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

このコードは、コンテンツ タイプやバイナリ データなど、ビデオに関する情報を抽出します。

## ステップ 6: ビデオを保存する

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

最後に、このステップでは、指定されたディレクトリ内の新しいファイルにビデオを保存します。

これらの手順を完了すると、Aspose.Slides for .NET を使用して PowerPoint スライドからビデオを正常に抽出できます。

## 結論

Aspose.Slides for .NET は、PowerPoint プレゼンテーションの操作プロセスを簡素化し、スライドからビデオを抽出するなどのタスクを簡単に実行できるようにします。このステップバイステップ ガイドに従い、Aspose.Slides ライブラリを利用すると、強力な PowerPoint 機能で .NET アプリケーションを強化できます。

## よくある質問 (FAQ)

### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、コンテンツの作成、編集、抽出など、.NET アプリケーションが PowerPoint プレゼンテーションと連携できるようにするライブラリです。

### Aspose.Slides for .NET のドキュメントはどこで見つけられますか?
ドキュメントを見つけることができます[ここ](https://reference.aspose.com/slides/net/).

### Aspose.Slides for .NET は無料試用できますか?
はい、以下から無料試用版を入手できます。[ここ](https://releases.aspose.com/).

### Aspose.Slides for .NET の一時ライセンスを取得するにはどうすればよいですか?
一時ライセンスは次からリクエストできます。[このリンク](https://purchase.aspose.com/temporary-license/).

### Aspose.Slides for .NET のサポートはどこで入手できますか?
サポートは次のサイトで見つけることができます。[Aspose.Slides フォーラム](https://forum.aspose.com/).