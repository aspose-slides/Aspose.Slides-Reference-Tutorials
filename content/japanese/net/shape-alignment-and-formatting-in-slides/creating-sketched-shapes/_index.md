---
title: Aspose.Slides で見事なスケッチ形状を作成
linktitle: Aspose.Slides を使用してプレゼンテーション スライドにスケッチされた形状を作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、クリエイティブなスケッチ形状をプレゼンテーション スライドに追加する方法を学びます。視覚的な魅力を簡単に強化します。
type: docs
weight: 13
url: /ja/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## 導入
Aspose.Slides for .NET を使用してプレゼンテーション スライドにスケッチ形状を作成するためのステップバイステップ ガイドへようこそ。プレゼンテーションに創造性を加えたい場合は、スケッチされた形状を使用すると、独自の手書きの美しさが得られます。このチュートリアルでは、スムーズなエクスペリエンスを確保するために、プロセスを簡単なステップに分けて説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slides for .NET ライブラリがインストールされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/slides/net/).
- 開発環境: 好みの IDE を使用して .NET 開発環境をセットアップします。
## 名前空間のインポート
まず、.NET プロジェクトに必要な名前空間をインポートします。この手順により、Aspose.Slides の操作に必要なクラスと機能にアクセスできるようになります。
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## ステップ 1: プロジェクトをセットアップする
新しい .NET プロジェクトを作成するか、既存のプロジェクトを開くことから始めます。プロジェクト参照に必ず Aspose.Slides を含めてください。
## ステップ 2: Aspose.Slides を初期化する
次のコード スニペットを追加して、Aspose.Slides を初期化します。これにより、プレゼンテーションが設定され、プレゼンテーション ファイルとサムネイル画像の出力パスが指定されます。
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    //次の手順に進みます...
}
```
## ステップ 3: スケッチ形状を追加する
次に、スケッチした形状をスライドに追加しましょう。この例では、フリーハンド スケッチ効果を備えた長方形を追加します。
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
//形状をフリーハンド スタイルのスケッチに変換します
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## ステップ 4: サムネイルを生成する
スライドのサムネイルを生成して、スケッチした形状を視覚化します。サムネイルを PNG ファイルとして保存します。
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## ステップ 5: プレゼンテーションを保存する
スケッチした形状を含むプレゼンテーション ファイルを保存します。
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
それでおしまい！ Aspose.Slides for .NET を使用して、スケッチされた形状を含むプレゼンテーションを正常に作成できました。
## 結論
スケッチした図形をプレゼンテーション スライドに追加すると、視覚的な魅力が高まり、聴衆の関心を引くことができます。 Aspose.Slides for .NET を使用すると、プロセスが簡単になり、創造性を簡単に発揮できるようになります。
## よくある質問
### 1. スケッチ効果をカスタマイズできますか?
はい、Aspose.Slides for .NET は、スケッチされた効果に対してさまざまなカスタマイズ オプションを提供します。を参照してください。[ドキュメンテーション](https://reference.aspose.com/slides/net/)詳細については。
### 2. 無料トライアルはありますか?
確かに！ Aspose.Slides for .NET の無料トライアルを試すことができます[ここ](https://releases.aspose.com/).
### 3. どこでサポートを受けられますか?
サポートや質問がある場合は、次のサイトにアクセスしてください。[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
### 4. Aspose.Slides for .NET を購入するにはどうすればよいですか?
 Aspose.Slides for .NET を購入するには、次のサイトにアクセスしてください。[購入ページ](https://purchase.aspose.com/buy).
### 5. 一時ライセンスは提供されますか?
はい、一時ライセンスは利用可能です[ここ](https://purchase.aspose.com/temporary-license/).