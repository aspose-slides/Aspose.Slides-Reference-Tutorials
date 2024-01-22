---
title: ノートのスライドからサムネイルを生成
linktitle: ノートのスライドからサムネイルを生成
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、プレゼンテーションのメモ セクションのスライドからサムネイルを生成する方法を学びます。ビジュアルコンテンツを強化しましょう！
type: docs
weight: 12
url: /ja/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

現代のプレゼンテーションの世界では、視覚的なコンテンツが重要です。効果的なコミュニケーションには、魅力的なスライドを作成することが不可欠です。プレゼンテーションを強化する 1 つの方法は、特に特定の詳細を強調したい場合や概要を共有したい場合に、スライドからサムネイルを生成することです。 Aspose.Slides for .NET は、これをシームレスに実現できる強力なツールです。このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用して、プレゼンテーションのメモ セクションのスライドからサムネイルを生成するプロセスについて説明します。

## 前提条件

詳細に入る前に、次の前提条件を満たしている必要があります。

### 1. .NET 用の Aspose.Slides

 Aspose.Slides for .NET がインストールされ、設定されていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/slides/net/).

### 2..NET環境

システム上に .NET 開発環境を準備しておく必要があります。

### 3. プレゼンテーション ファイル

プレゼンテーション ファイルを用意します (例:`ThumbnailFromSlideInNotes.pptx`) からサムネイルを生成します。

ここで、プロセスをステップに分けてみましょう。

## ステップ 1: 名前空間をインポートする

まず、Aspose.Slides を操作するために必要な名前空間をインポートする必要があります。 C# スクリプトの先頭に次のコードを追加します。

```csharp
using Aspose.Slides;
using System.Drawing;
```

## ステップ 2: プレゼンテーションをロードする

次に、メモ付きのスライドを含むプレゼンテーション ファイルをロードする必要があります。次のコードを使用してインスタンスを作成します`Presentation`クラス：

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    //コードはここに入力します
}
```

## ステップ 3: スライドにアクセスする

プレゼンテーション内のサムネイルを生成するスライドを選択できます。この例では、最初のスライドにアクセスします。

```csharp
ISlide sld = pres.Slides[0];
```

## ステップ 4: 必要な寸法を定義する

生成するサムネイルの寸法 (幅と高さ) を指定します。例えば：

```csharp
int desiredX = 1200; //幅
int desiredY = 800;  //身長
```

## ステップ 5: スケーリング係数を計算する

サムネイルが目的の寸法に確実に収まるように、次のように倍率を計算します。

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## ステップ 6: サムネイルを作成する

ここで、計算された倍率を使用して、フルスケール画像のサムネイルを作成します。

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## ステップ 7: サムネイルを保存する

最後に、生成されたサムネイルを JPEG 画像として保存します。

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

それでおしまい！ Aspose.Slides for .NET を使用して、プレゼンテーションのメモ セクションのスライドからサムネイルを生成することに成功しました。

## 結論

プレゼンテーションにサムネイルを組み込むと、プレゼンテーションの視覚的な魅力と効果が大幅に向上します。 Aspose.Slides for .NET を使用すると、このプロセスが簡単になり、スライドからカスタマイズされたサムネイルを簡単に作成できるようになります。

## FAQ（よくある質問）

### 生成されたサムネイルはどのような形式で保存できますか?
要件に応じて、JPEG、PNG などのさまざまな形式でサムネイルを保存できます。

### 複数のスライドのサムネイルを一度に生成できますか?
はい、プレゼンテーション内のスライドをループして、各スライドのサムネイルを生成できます。

### Aspose.Slides for .NET はさまざまな .NET フレームワークと互換性がありますか?
はい、Aspose.Slides for .NET は、.NET Core や .NET Framework などのさまざまな .NET フレームワークと互換性があります。

### 生成されたサムネイルの外観をカスタマイズできますか?
絶対に！ Aspose.Slides for .NET には、寸法、品質など、サムネイルの外観をカスタマイズするためのオプションが用意されています。

### Aspose.Slides for .NET に関するサポートやさらなる支援はどこで受けられますか?
次の場所でヘルプを見つけたり、Aspose コミュニティに参加したりできます。[Aspose サポート フォーラム](https://forum.aspose.com/).