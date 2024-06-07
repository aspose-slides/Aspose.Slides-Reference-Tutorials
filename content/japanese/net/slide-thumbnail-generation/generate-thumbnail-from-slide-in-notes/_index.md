---
title: ノートのスライドからサムネイルを生成する
linktitle: ノートのスライドからサムネイルを生成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、プレゼンテーションのノート セクションのスライドからサムネイルを生成する方法を学びます。ビジュアル コンテンツを強化しましょう。
type: docs
weight: 12
url: /ja/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

現代のプレゼンテーションの世界では、ビジュアル コンテンツが重要です。効果的なコミュニケーションには、魅力的なスライドの作成が不可欠です。プレゼンテーションを強化する方法の 1 つは、特に特定の詳細を強調したり概要を共有したりする場合、スライドからサムネイルを生成することです。Aspose.Slides for .NET は、これをシームレスに実現できる強力なツールです。このステップ バイ ステップ ガイドでは、Aspose.Slides for .NET を使用して、プレゼンテーションのノート セクションのスライドからサムネイルを生成するプロセスを順を追って説明します。

## 前提条件

詳細に入る前に、次の前提条件を満たしている必要があります。

### 1. .NET 用 Aspose.Slides

 Aspose.Slides for .NETがインストールされ、設定されていることを確認してください。ダウンロードはこちらからできます。[ここ](https://releases.aspose.com/slides/net/).

### 2. .NET環境

システムに .NET 開発環境を準備しておく必要があります。

### 3. プレゼンテーションファイル

プレゼンテーションファイル（例：`ThumbnailFromSlideInNotes.pptx`サムネイルを生成する画像（ ）を選択します。

それでは、プロセスをステップに分解してみましょう。

## ステップ1: 名前空間をインポートする

まず、Aspose.Slides を操作するために必要な名前空間をインポートする必要があります。C# スクリプトの先頭に次のコードを追加します。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## ステップ2: プレゼンテーションを読み込む

次に、メモ付きのスライドを含むプレゼンテーションファイルを読み込む必要があります。次のコードを使用して、`Presentation`クラス：

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    //ここにコードを入力してください
}
```

## ステップ3: スライドにアクセスする

プレゼンテーション内のどのスライドのサムネイルを生成するかを選択できます。この例では、最初のスライドにアクセスします。

```csharp
ISlide sld = pres.Slides[0];
```

## ステップ4: 希望する寸法を定義する

生成するサムネイルの寸法 (幅と高さ) を指定します。例:

```csharp
int desiredX = 1200; //幅
int desiredY = 800;  //身長
```

## ステップ5: スケーリング係数を計算する

サムネイルが希望の寸法に収まるようにするには、次のようにスケーリング係数を計算します。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## ステップ6: サムネイルを作成する

次に、計算されたスケーリング係数を使用してフルスケールの画像サムネイルを作成します。

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## ステップ7: サムネイルを保存する

最後に、生成されたサムネイルを JPEG 画像として保存します。

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

これで完了です。Aspose.Slides for .NET を使用して、プレゼンテーションのノート セクションのスライドからサムネイルを正常に生成できました。

## 結論

プレゼンテーションにサムネイルを組み込むと、プレゼンテーションの見た目の魅力と効果が大幅に向上します。Aspose.Slides for .NET を使用すると、このプロセスが簡単になり、スライドからカスタマイズされたサムネイルを簡単に作成できます。

## FAQ（よくある質問）

### 生成されたサムネイルはどのような形式で保存できますか?
要件に応じて、JPEG、PNG などさまざまな形式でサムネイルを保存できます。

### 一度に複数のスライドのサムネイルを生成できますか?
はい、プレゼンテーション内のスライドをループし、それぞれのサムネイルを生成することができます。

### Aspose.Slides for .NET はさまざまな .NET フレームワークと互換性がありますか?
はい、Aspose.Slides for .NET は、.NET Core や .NET Framework を含むさまざまな .NET フレームワークと互換性があります。

### 生成されたサムネイルの外観をカスタマイズできますか?
もちろんです! Aspose.Slides for .NET には、サイズや品質など、サムネイルの外観をカスタマイズするためのオプションが用意されています。

### Aspose.Slides for .NET に関するサポートや追加の支援はどこで受けられますか?
 Asposeコミュニティのヘルプや参加については、[Aspose サポート フォーラム](https://forum.aspose.com/).