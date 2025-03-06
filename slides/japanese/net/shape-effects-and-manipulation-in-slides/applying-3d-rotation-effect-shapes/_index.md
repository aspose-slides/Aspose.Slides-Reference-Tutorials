---
title: Aspose.Slides for .NET を使用したプレゼンテーションでの 3D 回転の習得
linktitle: プレゼンテーションスライドの図形に 3D 回転効果を適用する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET でプレゼンテーションを強化しましょう。このチュートリアルでは、図形に 3D 回転効果を適用する方法を学びます。ダイナミックで視覚的に魅力的なプレゼンテーションを作成します。
weight: 23
url: /ja/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET を使用したプレゼンテーションでの 3D 回転の習得

## 導入
魅力的でダイナミックなプレゼンテーション スライドを作成することは、効果的なコミュニケーションの重要な側面です。Aspose.Slides for .NET は、図形に 3D 回転効果を適用する機能など、プレゼンテーションを強化するための強力なツール セットを提供します。このチュートリアルでは、Aspose.Slides for .NET を使用して、プレゼンテーション スライドの図形に 3D 回転効果を適用するプロセスについて説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: コードを記述して実行するために、Visual Studio などの .NET 開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトで、Aspose.Slides の機能を活用するために必要な名前空間をインポートします。コードの先頭に次の名前空間を含めます。
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ1: プロジェクトを設定する
希望する .NET 開発環境で新しいプロジェクトを作成します。プロジェクトに Aspose.Slides 参照を追加したことを確認します。
## ステップ2: プレゼンテーションを初期化する
スライドの操作を開始するには、Presentation クラスをインスタンス化します。
```csharp
Presentation pres = new Presentation();
```
## ステップ3: オートシェイプを追加する
スライドにオートシェイプを追加し、その種類、位置、寸法を指定します。
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## ステップ4: 3D回転効果を設定する
オートシェイプの 3D 回転効果を設定します。
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## ステップ5: プレゼンテーションを保存する
3D 回転効果を適用した変更されたプレゼンテーションを保存します。
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## ステップ6: 他の図形についても繰り返します
追加の図形がある場合は、図形ごとに手順 3 ～ 5 を繰り返します。
## 結論
プレゼンテーション スライドの図形に 3D 回転効果を追加すると、見た目の魅力が大幅に高まります。Aspose.Slides for .NET を使用すると、このプロセスが簡単になり、魅力的なプレゼンテーションを作成できます。
## よくある質問
### Aspose.Slides for .NET のテキスト ボックスに 3D 回転を適用できますか?
はい、Aspose.Slides を使用して、テキスト ボックスを含むさまざまな図形に 3D 回転効果を適用できます。
### Aspose.Slides for .NET の試用版はありますか?
はい、試用版にアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Slides for .NET のサポートを受けるにはどうすればよいですか?
訪問[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのため。
### Aspose.Slides for .NET の一時ライセンスを購入できますか?
はい、一時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET の詳細なドキュメントはどこで入手できますか?
ドキュメントは入手可能です[ここ](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
