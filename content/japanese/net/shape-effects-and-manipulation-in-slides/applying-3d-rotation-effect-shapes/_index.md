---
title: Aspose.Slides for .NET を使用してプレゼンテーションでの 3D 回転をマスターする
linktitle: プレゼンテーション スライドの図形に 3D 回転効果を適用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用してプレゼンテーションを強化しましょう。このチュートリアルでは、3D 回転効果をシェイプに適用する方法を学びます。ダイナミックで視覚的に素晴らしいプレゼンテーションを作成します。
type: docs
weight: 23
url: /ja/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---
## 導入
魅力的でダイナミックなプレゼンテーション スライドを作成することは、効果的なコミュニケーションの重要な側面です。 Aspose.Slides for .NET は、図形に 3D 回転効果を適用する機能など、プレゼンテーションを強化するための強力なツール セットを提供します。このチュートリアルでは、Aspose.Slides for .NET を使用して、プレゼンテーション スライド内の図形に 3D 回転効果を適用するプロセスを説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slides for .NET ライブラリがインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: コードを作成して実行するために、Visual Studio などの .NET 開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトで、Aspose.Slides の機能を利用するために必要な名前空間をインポートします。コードの先頭に次の名前空間を含めます。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ 1: プロジェクトをセットアップする
好みの .NET 開発環境で新しいプロジェクトを作成します。 Aspose.Slides 参照がプロジェクトに追加されていることを確認してください。
## ステップ 2: プレゼンテーションを初期化する
プレゼンテーション クラスをインスタンス化して、スライドの操作を開始します。
```csharp
Presentation pres = new Presentation();
```
## ステップ 3: オートシェイプを追加する
オートシェイプをスライドに追加し、タイプ、位置、寸法を指定します。
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## ステップ 4: 3D 回転効果を設定する
オートシェイプの 3D 回転効果を構成します。
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## ステップ 5: プレゼンテーションを保存する
3D 回転効果を適用して、変更したプレゼンテーションを保存します。
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## ステップ 6: 他の形状についても繰り返します
追加の図形がある場合は、各図形に対して手順 3 ～ 5 を繰り返します。
## 結論
プレゼンテーション スライド内の図形に 3D 回転効果を追加すると、視覚的な魅力が大幅に向上します。 Aspose.Slides for .NET を使用すると、このプロセスが簡単になり、魅力的なプレゼンテーションを作成できるようになります。
## よくある質問
### Aspose.Slides for .NET のテキスト ボックスに 3D 回転を適用できますか?
はい、Aspose.Slides を使用して、テキスト ボックスを含むさまざまな図形に 3D 回転効果を適用できます。
### Aspose.Slides for .NET の試用版は入手できますか?
はい、試用版にアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのために。
### Aspose.Slides for .NET の一時ライセンスを購入できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET の詳細なドキュメントはどこで見つけられますか?
ドキュメントは利用可能です[ここ](https://reference.aspose.com/slides/net/).