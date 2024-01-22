---
title: ShapeUtil でジオメトリ シェイプをマスターする - Aspose.Slides .NET
linktitle: プレゼンテーション スライドのジオメトリ形状に ShapeUtil を使用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: 動的なジオメトリ シェイプの ShapeUtil を使用して、Aspose.Slides for .NET の機能を試してください。魅力的なプレゼンテーションを簡単に作成できます。今すぐダウンロードしてください。Aspose.Slides を使用して PowerPoint プレゼンテーションを強化する方法を学びましょう。ジオメトリ形状の操作については、ShapeUtil を調べてください。 .NET ソース コードを含むステップバイステップ ガイド。プレゼンテーションを効果的に最適化します。
type: docs
weight: 17
url: /ja/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---
## 導入
視覚的に魅力的で動的なプレゼンテーション スライドを作成することは必須のスキルであり、Aspose.Slides for .NET はこれを実現するための強力なツールキットを提供します。このチュートリアルでは、ShapeUtil を使用してプレゼンテーション スライド内のジオメトリ形状を処理する方法を検討します。経験豊富な開発者でも、Aspose.Slides を使い始めたばかりでも、このガイドでは、ShapeUtil を利用してプレゼンテーションを強化するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- C# および .NET プログラミングの基本的な理解。
-  Aspose.Slides for .NET ライブラリがインストールされました。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/slides/net/).
- .NET アプリケーションを実行するためにセットアップされた開発環境。
## 名前空間のインポート
C# コードでは、Aspose.Slides 機能にアクセスするために必要な名前空間をインポートしていることを確認してください。スクリプトの先頭に次の行を追加します。
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
ここで、提供された例を複数のステップに分割して、プレゼンテーション スライドのジオメトリ形状に ShapeUtil を使用するためのステップバイステップ ガイドを作成しましょう。
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
「ドキュメント ディレクトリ」をプレゼンテーションを保存する実際のパスに置き換えてください。
## ステップ 2: 出力ファイル名を定義する
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
ファイル拡張子を含む目的の出力ファイル名を指定します。
## ステップ 3: プレゼンテーションを作成する
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides ライブラリを使用して、新しいプレゼンテーション オブジェクトを初期化します。
## ステップ 4: ジオメトリ形状を追加する
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
プレゼンテーションの最初のスライドに長方形の図形を追加します。
## ステップ 5: 元のジオメトリ パスを取得する
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
シェイプのジオメトリ パスを取得し、塗りつぶしモードを設定します。
## ステップ 6: テキストを含むグラフィックス パスを作成する
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
図形に追加するテキストを含むグラフィックス パスを生成します。
## ステップ 7: グラフィックス パスをジオメトリ パスに変換する
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
ShapeUtil を使用して、グラフィックス パスをジオメトリ パスに変換し、塗りつぶしモードを設定します。
## ステップ 8: 結合されたジオメトリ パスをシェイプに設定する
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
新しいジオメトリ パスを元のパスと結合し、形状に設定します。
## ステップ 9: プレゼンテーションを保存する
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
変更したプレゼンテーションを新しいジオメトリ形状とともに保存します。
## 結論
おめでとう！ Aspose.Slides for .NET を使用して、ShapeUtil を使用してプレゼンテーション スライド内のジオメトリ形状を処理する方法を確認しました。この強力な機能を使用すると、ダイナミックで魅力的なプレゼンテーションを簡単に作成できます。
## よくある質問
### Aspose.Slides for .NET を他のプログラミング言語で使用できますか?
Aspose.Slides は主に .NET 言語をサポートします。ただし、Aspose は他のプラットフォームや言語にも同様のライブラリを提供します。
### Aspose.Slides for .NET の詳細なドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET に利用できる無料トライアルはありますか?
はい、無料トライアルを見つけることができます[ここ](https://releases.aspose.com/).
### Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
コミュニティサポートフォーラムにアクセスしてください[ここ](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for .NET の一時ライセンスを購入できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).