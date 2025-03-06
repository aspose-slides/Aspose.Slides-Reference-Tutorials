---
title: ビジュアルをマスターする - .NET で Aspose.Slides を使用してセグメントを追加する
linktitle: Aspose.Slides を使用してプレゼンテーションのジオメトリ シェイプにセグメントを追加する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides を使用して .NET アプリケーションを強化する方法を学びます。このチュートリアルでは、魅力的なプレゼンテーションのためにジオメトリ シェイプにセグメントを追加する方法について説明します。
weight: 13
url: /ja/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
.NET 開発の世界では、視覚的に魅力的なプレゼンテーションを作成することが一般的な要件です。Aspose.Slides for .NET は、強力なプレゼンテーション作成機能を .NET アプリケーションにシームレスに統合する強力なライブラリです。このチュートリアルでは、プレゼンテーション デザインの特定の側面、つまりジオメトリ シェイプへのセグメントの追加に焦点を当てます。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- C# プログラミング言語に関する基本的な知識。
- マシンに Visual Studio がインストールされています。
- Aspose.Slides for .NET ライブラリがダウンロードされ、プロジェクトで参照されます。
## 名前空間のインポート
C# コードでは、Aspose.Slides 機能にアクセスするために必要な名前空間を必ずインポートしてください。コードに次の行を追加します。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
ここで、例を複数のステップに分解してみましょう。
## ステップ1: プロジェクトを設定する
まず、Visual Studio で新しい C# プロジェクトを作成します。プロジェクトで Aspose.Slides ライブラリが参照されていることを確認します。
## ステップ2: プレゼンテーションを作成する
Aspose.Slides ライブラリを使用して新しいプレゼンテーション オブジェクトを初期化します。これは、ジオメトリ シェイプのキャンバスとして機能します。
```csharp
using (Presentation pres = new Presentation())
{
    //プレゼンテーションを作成するためのコードをここに入力します
}
```
## ステップ3: ジオメトリシェイプを追加する
プレゼンテーション内に幾何学図形を作成します。たとえば、最初のスライドに長方形を追加してみましょう。
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## ステップ4: ジオメトリパスを取得する
作成されたシェイプのジオメトリ パスを取得して、そのセグメントを操作します。
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## ステップ5: セグメントを追加する
ジオメトリ パスにセグメント (線) を追加します。この例では、パスに 2 本の線が追加されます。
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## ステップ6: 編集したジオメトリパスを割り当てる
変更を適用するには、変更したジオメトリ パスをシェイプに再度割り当てます。
```csharp
shape.SetGeometryPath(geometryPath);
```
## ステップ7: プレゼンテーションを保存する
変更したプレゼンテーションを目的の場所に保存します。
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
これらの手順により、Aspose.Slides for .NET を使用してプレゼンテーションのジオメトリ シェイプにセグメントを正常に追加できました。
## 結論
Aspose.Slides for .NET を使用すると、開発者は高度なプレゼンテーション作成機能を使用してアプリケーションを強化できます。ジオメトリ シェイプにセグメントを追加すると、プレゼンテーションの視覚要素をカスタマイズできます。
### よくある質問
### Aspose.Slides を使用してさまざまな種類の図形を追加できますか?
はい、Aspose.Slides は、長方形、円、カスタムジオメトリ図形など、さまざまな図形タイプをサポートしています。
### プロジェクトで Aspose.Slides を使用するにはライセンスが必要ですか?
はい、有効なライセンスが必要です。テスト目的で一時ライセンスを取得するか、本番環境用にフルライセンスを購入することができます。
### Aspose.Slides 関連のクエリのサポートを受けるにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのため。
### Aspose.Slides に関する他のチュートリアルはありますか?
探索する[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的なガイドと例については、こちらをご覧ください。
### 購入前に Aspose.Slides を無料で試すことはできますか?
はい、無料トライアルはここからダウンロードできます。[ここ](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
