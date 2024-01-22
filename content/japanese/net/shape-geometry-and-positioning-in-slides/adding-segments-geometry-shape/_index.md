---
title: ビジュアルのマスタリング - .NET で Aspose.Slides を使用してセグメントを追加する
linktitle: Aspose.Slides を使用したプレゼンテーションのジオメトリ図形へのセグメントの追加
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides を使用して .NET アプリケーションを強化する方法を学びます。このチュートリアルでは、魅力的なプレゼンテーションを作成するためにジオメトリ図形にセグメントを追加する方法を説明します。
type: docs
weight: 13
url: /ja/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---
## 導入
.NET 開発の世界では、視覚的に魅力的なプレゼンテーションを作成することが一般的な要件です。 Aspose.Slides for .NET は、堅牢なプレゼンテーション作成機能を .NET アプリケーションにシームレスに統合することを容易にする強力なライブラリです。このチュートリアルでは、プレゼンテーション デザインの特定の側面、つまりジオメトリ形状へのセグメントの追加に焦点を当てます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語の基本的な知識。
- Visual Studio がマシンにインストールされていること。
- Aspose.Slides for .NET ライブラリがダウンロードされ、プロジェクトで参照されます。
## 名前空間のインポート
C# コードでは、Aspose.Slides 機能にアクセスするために必要な名前空間をインポートしてください。コードに次の行を追加します。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
ここで、例を複数のステップに分けてみましょう。
## ステップ 1: プロジェクトをセットアップする
まず、Visual Studio で新しい C# プロジェクトを作成します。プロジェクト内で Aspose.Slides ライブラリが参照されていることを確認してください。
## ステップ 2: プレゼンテーションを作成する
Aspose.Slides ライブラリを使用して、新しいプレゼンテーション オブジェクトを初期化します。これは、ジオメトリ形状のキャンバスとして機能します。
```csharp
using (Presentation pres = new Presentation())
{
    //プレゼンテーションを作成するためのコードはここにあります
}
```
## ステップ 3: ジオメトリ形状を追加する
プレゼンテーション内にジオメトリ形状を作成します。たとえば、最初のスライドに四角形を追加してみましょう。
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## ステップ 4: ジオメトリ パスを取得する
作成されたシェイプのジオメトリ パスを取得して、そのセグメントを操作します。
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## ステップ 5: セグメントを追加する
ジオメトリ パスにセグメント (線) を追加します。この例では、パスに 2 行が追加されます。
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## ステップ 6: 編集したジオメトリ パスを割り当てる
変更したジオメトリ パスをシェイプに割り当てて戻し、変更を適用します。
```csharp
shape.SetGeometryPath(geometryPath);
```
## ステップ 7: プレゼンテーションを保存する
変更したプレゼンテーションを目的の場所に保存します。
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
これらの手順により、Aspose.Slides for .NET を使用してプレゼンテーション内のジオメトリ図形にセグメントを追加することができました。
## 結論
Aspose.Slides for .NET を使用すると、開発者は高度なプレゼンテーション作成機能でアプリケーションを強化できます。セグメントをジオメトリ図形に追加すると、プレゼンテーションの視覚要素をカスタマイズする手段が提供されます。
### よくある質問
### Aspose.Slides を使用してさまざまな種類の図形を追加できますか?
はい。Aspose.Slides は、長方形、円、カスタム ジオメトリ形状など、さまざまな形状タイプをサポートしています。
### プロジェクトで Aspose.Slides を使用するにはライセンスが必要ですか?
はい、有効なライセンスが必要です。テスト目的で一時ライセンスを取得することも、運用目的で完全ライセンスを購入することもできます。
### Aspose.Slides 関連のクエリのサポートを受けるにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのために。
### Aspose.Slides で利用できる他のチュートリアルはありますか?
を探索してください[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的なガイドと例を参照してください。
### 購入する前に、Aspose.Slides を無料で試すことはできますか?
はい、以下から無料試用版をダウンロードできます。[ここ](https://releases.aspose.com/).