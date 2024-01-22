---
title: Aspose.Slides でベベル効果をマスターする - ステップバイステップチュートリアル
linktitle: Aspose.Slides を使用してプレゼンテーション スライド内の図形にベベル効果を適用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーション スライドを強化します。このステップバイステップのガイドで、魅力的なベベル効果を適用する方法を学びましょう。
type: docs
weight: 24
url: /ja/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---
## 導入
ダイナミックなプレゼンテーションの世界では、スライドに視覚的な魅力を追加すると、メッセージの影響力が大幅に高まります。 Aspose.Slides for .NET は、プレゼンテーション スライドをプログラムで操作および美化するための強力なツールキットを提供します。そのような興味深い機能の 1 つは、図形にベベル効果を適用して、ビジュアルに奥行きと立体感を加える機能です。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
- Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: .NET 開発環境をセットアップし、C# の基本を理解します。
- ドキュメント ディレクトリ: 生成されたプレゼンテーション ファイルが保存されるドキュメント用のディレクトリを作成します。
## 名前空間のインポート
C# コードに、Aspose.Slides 機能にアクセスするために必要な名前空間を含めます。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
ドキュメント ディレクトリが存在することを確認し、存在しない場合は作成します。
## ステップ 2: プレゼンテーション インスタンスを作成する
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
プレゼンテーション インスタンスを初期化し、操作するスライドを追加します。
## ステップ 3: スライドに図形を追加する
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
## ステップ 4: ThreeDFormat プロパティを設定する
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
ベベルのタイプ、高さ、幅、カメラのタイプ、ライトのタイプ、方向などの 3 次元プロパティを指定します。
## ステップ 5: プレゼンテーションを保存する
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
ベベル効果を適用したプレゼンテーションを PPTX ファイルに保存します。
## 結論
おめでとう！ Aspose.Slides for .NET を使用して、プレゼンテーション内の図形にベベル効果を適用することに成功しました。さまざまなパラメーターを試して、スライドの視覚的な強化の可能性を最大限に引き出します。
## よくある質問
### 1. ベベル効果を他のシェイプに適用できますか?
はい、シェイプのタイプとプロパティを適宜調整することで、さまざまなシェイプにベベル効果を適用できます。
### 2. ベベルの色を変更するにはどうすればよいですか?
を変更します。`SolidFillColor.Color`内のプロパティ`BevelTop`ベベルの色を変更するプロパティ。
### 3. Aspose.Slides は最新の .NET Framework と互換性がありますか?
はい。Aspose.Slides は、最新の .NET フレームワークとの互換性を確保するために定期的に更新されます。
### 4. 複数のベベル効果を 1 つのシェイプに適用できますか?
一般的ではありませんが、複数のシェイプを積み重ねたり、ベベルのプロパティを操作して同様の効果を実現することを試すことができます。
### 5. Aspose.Slides で利用できる他の 3D 効果はありますか?
絶対に！ Aspose.Slides は、プレゼンテーション要素に深みとリアルさを加えるさまざまな 3D 効果を提供します。