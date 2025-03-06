---
title: Aspose.Slides でベベル効果をマスターする - ステップバイステップのチュートリアル
linktitle: Aspose.Slides を使用してプレゼンテーション スライドの図形にベベル効果を適用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーション スライドを強化しましょう。このステップ バイ ステップ ガイドで、魅力的なベベル効果を適用する方法を学びます。
weight: 24
url: /ja/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## 導入
プレゼンテーションのダイナミックな世界では、スライドに視覚的な魅力を加えることで、メッセージの効果を大幅に高めることができます。Aspose.Slides for .NET は、プレゼンテーション スライドをプログラムで操作し、美しくするための強力なツールキットを提供します。そのような魅力的な機能の 1 つは、図形にベベル効果を適用して、ビジュアルに深みと次元を追加する機能です。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: .NET 開発環境を設定し、C# の基本を理解します。
- ドキュメント ディレクトリ: 生成されたプレゼンテーション ファイルを保存するドキュメント用のディレクトリを作成します。
## 名前空間のインポート
C# コードに、Aspose.Slides 機能にアクセスするために必要な名前空間を含めます。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ1: ドキュメントディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ドキュメント ディレクトリが存在することを確認し、まだ存在しない場合は作成します。
## ステップ2: プレゼンテーションインスタンスを作成する
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
プレゼンテーション インスタンスを初期化し、作業するスライドを追加します。
## ステップ3: スライドに図形を追加する
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
自動シェイプ (この例では楕円) を作成し、その塗りつぶしと線のプロパティをカスタマイズします。
## ステップ4: ThreeDFormatプロパティを設定する
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
ベベル タイプ、高さ、幅、カメラ タイプ、ライト タイプ、方向などの 3 次元プロパティを指定します。
## ステップ5: プレゼンテーションを保存する
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
ベベル効果を適用したプレゼンテーションを PPTX ファイルに保存します。
## 結論
おめでとうございます! Aspose.Slides for .NET を使用して、プレゼンテーションの図形にベベル効果を適用できました。さまざまなパラメーターを試して、スライドの視覚的強化の可能性を最大限に引き出してください。
## よくある質問
### 1. ベベル効果を他の図形に適用できますか?
はい、シェイプの種類とプロパティを適宜調整することで、さまざまなシェイプにベベル効果を適用できます。
### 2. ベベルの色を変更するにはどうすればよいですか?
変更する`SolidFillColor.Color`内の財産`BevelTop`ベベルの色を変更するプロパティ。
### 3. Aspose.Slides は最新の .NET フレームワークと互換性がありますか?
はい、Aspose.Slides は最新の .NET フレームワークとの互換性を確保するために定期的に更新されます。
### 4. 1 つのシェイプに複数のベベル効果を適用できますか?
一般的ではありませんが、複数の図形を積み重ねたり、ベベルのプロパティを操作したりして、同様の効果を実現することもできます。
### 5. Aspose.Slides では他の 3D 効果も利用できますか?
もちろんです! Aspose.Slides は、プレゼンテーション要素に深みとリアリティを加えるさまざまな 3D 効果を提供します。
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
