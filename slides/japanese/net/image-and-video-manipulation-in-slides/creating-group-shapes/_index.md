---
title: Aspose.Slides - .NET でグループ図形を作成する
linktitle: Aspose.Slides を使用してプレゼンテーション スライドにグループ図形を作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint でグループ図形を作成する方法を学びます。視覚的に魅力的なプレゼンテーションを作成するためのステップバイステップ ガイドに従ってください。
weight: 11
url: /ja/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - .NET でグループ図形を作成する

## 導入
プレゼンテーション スライドの視覚的な魅力を高め、コンテンツをより効率的に整理したい場合は、グループ シェイプを組み込むことが強力なソリューションとなります。Aspose.Slides for .NET は、PowerPoint プレゼンテーションでグループ シェイプをシームレスに作成および操作する方法を提供します。このチュートリアルでは、Aspose.Slides を使用してグループ シェイプを作成するプロセスを、わかりやすい手順に分解して説明します。
## 前提条件
チュートリアルに進む前に、次のものを用意してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: Visual Studio などの .NET 互換 IDE を使用して作業環境をセットアップします。
- C# の基礎知識: C# プログラミング言語の基礎を理解します。
## 名前空間のインポート
C# プロジェクトでは、まず必要な名前空間をインポートします。
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ1: プレゼンテーションクラスのインスタンスを作成する

インスタンスを作成する`Presentation`クラスを作成し、ドキュメントが保存されるディレクトリを指定します。

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    //このブロックを使用して次の手順に進みます
}
```

## ステップ2: 最初のスライドにアクセスする

プレゼンテーションから最初のスライドを取得します。

```csharp
ISlide sld = pres.Slides[0];
```

## ステップ3: シェイプコレクションにアクセスする

スライド上の図形のコレクションにアクセスします。

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## ステップ4: グループシェイプの追加

スライドにグループ図形を追加します。

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## ステップ5: グループ図形内に図形を追加する

グループ シェイプに個別のシェイプを追加します。

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## ステップ6: グループシェイプフレームの追加

グループ シェイプ全体のフレームを定義します。

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## ステップ7: プレゼンテーションを保存する

変更したプレゼンテーションを指定したディレクトリに保存します。

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

C# アプリケーションでこれらの手順を繰り返して、Aspose.Slides を使用してプレゼンテーション スライドにグループ シェイプを正常に作成します。

## 結論
このチュートリアルでは、Aspose.Slides for .NET を使用してグループ図形を作成するプロセスについて説明しました。これらの手順に従うことで、PowerPoint プレゼンテーションの視覚的な魅力と構成を強化できます。
## よくある質問
### Aspose.Slides は最新バージョンの .NET と互換性がありますか?
はい、Aspose.Slidesは定期的に更新され、最新の.NETバージョンをサポートします。[ドキュメンテーション](https://reference.aspose.com/slides/net/)互換性の詳細については、こちらをご覧ください。
### 購入前に Aspose.Slides を試すことはできますか?
もちろんです！無料試用版をダウンロードできます[ここ](https://releases.aspose.com/).
### Aspose.Slides 関連のクエリのサポートはどこで見つかりますか?
Aspose.Slidesをご覧ください[フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのため。
### Aspose.Slides の一時ライセンスを取得するにはどうすればよいですか?
臨時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides のフルライセンスはどこで購入できますか?
ライセンスは以下から購入できます。[購入ページ](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
