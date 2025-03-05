---
title: Aspose.Slides で魅力的なスケッチ図形を作成する
linktitle: Aspose.Slides を使用してプレゼンテーション スライドにスケッチ図形を作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、プレゼンテーション スライドにクリエイティブなスケッチ図形を追加する方法を学びます。視覚的な魅力を簡単に高めることができます。
type: docs
weight: 13
url: /ja/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## 導入
Aspose.Slides for .NET を使用してプレゼンテーション スライドにスケッチ図形を作成する手順を説明したガイドへようこそ。プレゼンテーションに創造性を加えたい場合は、スケッチ図形を使用すると、手描きのようなユニークな外観を実現できます。このチュートリアルでは、プロセスを簡単な手順に分解して順を追って説明し、スムーズな操作を実現します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。ダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).
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
## ステップ1: プロジェクトの設定
まず、新しい .NET プロジェクトを作成するか、既存のプロジェクトを開きます。プロジェクト参照に Aspose.Slides を含めるようにしてください。
## ステップ 2: Aspose.Slides を初期化する
次のコード スニペットを追加して Aspose.Slides を初期化します。これにより、プレゼンテーションが設定され、プレゼンテーション ファイルとサムネイル イメージの出力パスが指定されます。
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    //次の手順に進みます...
}
```
## ステップ3: スケッチした図形を追加する
次に、スライドにスケッチした図形を追加してみましょう。この例では、フリーハンド スケッチ効果のある長方形を追加します。
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
//図形をフリーハンドスタイルのスケッチに変換します
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## ステップ4: サムネイルを生成する
スケッチした形状を視覚化するためにスライドのサムネイルを生成します。サムネイルを PNG ファイルとして保存します。
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## ステップ5: プレゼンテーションを保存する
スケッチした図形を含むプレゼンテーション ファイルを保存します。
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
これで完了です。Aspose.Slides for .NET を使用して、スケッチされた図形を含むプレゼンテーションを正常に作成できました。
## 結論
プレゼンテーション スライドにスケッチされた図形を追加すると、視覚的な魅力が高まり、視聴者の関心を引き付けることができます。Aspose.Slides for .NET を使用すると、プロセスが簡単になり、創造性を簡単に発揮できるようになります。
## よくある質問
### 1. スケッチ効果をカスタマイズできますか?
はい、Aspose.Slides for .NET ではスケッチ効果のさまざまなカスタマイズ オプションが提供されています。[ドキュメンテーション](https://reference.aspose.com/slides/net/)詳細情報については。
### 2. 無料トライアルはありますか?
もちろんです！Aspose.Slides for .NETの無料トライアルをお試しください。[ここ](https://releases.aspose.com/).
### 3. サポートはどこで受けられますか?
ご不明な点やご質問は、[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
### 4. Aspose.Slides for .NET を購入するにはどうすればよいですか?
 Aspose.Slides for .NETを購入するには、[購入ページ](https://purchase.aspose.com/buy).
### 5. 一時ライセンスを提供していますか?
はい、一時ライセンスは利用可能です[ここ](https://purchase.aspose.com/temporary-license/).