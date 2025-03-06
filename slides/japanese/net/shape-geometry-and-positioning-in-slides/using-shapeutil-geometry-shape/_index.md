---
title: ShapeUtil を使用したジオメトリ シェイプの習得 - Aspose.Slides .NET
linktitle: プレゼンテーションスライドのジオメトリシェイプに ShapeUtil を使用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: 動的なジオメトリ シェイプ用の ShapeUtil を備えた Aspose.Slides for .NET のパワーを体験してください。魅力的なプレゼンテーションを簡単に作成できます。今すぐダウンロードしてください。Aspose.Slides を使用して PowerPoint プレゼンテーションを強化する方法を学習します。ジオメトリ シェイプの操作には ShapeUtil をご利用ください。.NET ソース コードを使用したステップ バイ ステップ ガイド。プレゼンテーションを効果的に最適化します。
type: docs
weight: 17
url: /ja/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
## 導入
視覚的に魅力的でダイナミックなプレゼンテーション スライドを作成することは必須のスキルであり、Aspose.Slides for .NET はこれを実現するための強力なツールキットを提供します。このチュートリアルでは、プレゼンテーション スライドでジオメトリ シェイプを処理するための ShapeUtil の使用について説明します。熟練した開発者でも、Aspose.Slides を使い始めたばかりの開発者でも、このガイドでは ShapeUtil を使用してプレゼンテーションを強化するプロセスを順を追って説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- C# および .NET プログラミングの基本的な理解。
-  Aspose.Slides for .NETライブラリをインストールします。インストールされていない場合はダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).
- .NET アプリケーションを実行するためにセットアップされた開発環境。
## 名前空間のインポート
C# コードでは、Aspose.Slides 機能にアクセスするために必要な名前空間をインポートしていることを確認します。スクリプトの先頭に次のコードを追加します。
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
ここで、提供された例を複数のステップに分解して、プレゼンテーション スライドのジオメトリ シェイプに ShapeUtil を使用するためのステップ バイ ステップ ガイドを作成しましょう。
## ステップ1: ドキュメントディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
「Your Document Directory」を、プレゼンテーションを保存する実際のパスに置き換えてください。
## ステップ2: 出力ファイル名を定義する
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
ファイル拡張子を含む、希望の出力ファイル名を指定します。
## ステップ3: プレゼンテーションを作成する
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides ライブラリを使用して新しいプレゼンテーション オブジェクトを初期化します。
## ステップ4: ジオメトリシェイプを追加する
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
プレゼンテーションの最初のスライドに長方形の図形を追加します。
## ステップ5: 元のジオメトリパスを取得する
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
図形のジオメトリ パスを取得し、塗りつぶしモードを設定します。
## ステップ6: テキストを含むグラフィックパスを作成する
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
図形に追加するテキストを含むグラフィック パスを生成します。
## ステップ7: グラフィックパスをジオメトリパスに変換する
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
ShapeUtil を使用して、グラフィック パスをジオメトリ パスに変換し、塗りつぶしモードを設定します。
## ステップ8: 結合されたジオメトリパスをシェイプに設定する
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
新しいジオメトリ パスを元のパスと結合し、シェイプに設定します。
## ステップ9: プレゼンテーションを保存する
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
変更したプレゼンテーションを新しいジオメトリ シェイプで保存します。
## 結論
おめでとうございます! Aspose.Slides for .NET を使用して、プレゼンテーション スライド内のジオメトリ シェイプを処理するための ShapeUtil の使用方法を学習しました。この強力な機能により、ダイナミックで魅力的なプレゼンテーションを簡単に作成できます。
## よくある質問
### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
Aspose.Slides は主に .NET 言語をサポートしています。ただし、Aspose は他のプラットフォームや言語向けにも同様のライブラリを提供しています。
### Aspose.Slides for .NET の詳細なドキュメントはどこで入手できますか?
ドキュメントは入手可能です[ここ](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET の無料試用版はありますか?
はい、無料トライアルを見つけることができます[ここ](https://releases.aspose.com/).
### Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
コミュニティサポートフォーラムにアクセス[ここ](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for .NET の一時ライセンスを購入できますか?
はい、一時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/).