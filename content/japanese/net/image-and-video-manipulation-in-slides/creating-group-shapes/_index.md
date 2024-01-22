---
title: Aspose.Slides - .NET でのグループ シェイプの作成
linktitle: Aspose.Slides を使用してプレゼンテーション スライドにグループ図形を作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint でグループ図形を作成する方法を学びます。視覚的に魅力的なプレゼンテーションを作成するには、ステップバイステップのガイドに従ってください。
type: docs
weight: 11
url: /ja/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## 導入
プレゼンテーション スライドの視覚的な魅力を高め、コンテンツをより効率的に整理したい場合は、グループ図形を組み込むことが強力なソリューションです。 Aspose.Slides for .NET は、PowerPoint プレゼンテーションでグループ図形を作成および操作するシームレスな方法を提供します。このチュートリアルでは、Aspose.Slides を使用してグループ シェイプを作成するプロセスを、わかりやすい手順に分けて説明します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/slides/net/).
- 開発環境: Visual Studio などの .NET 互換 IDE を使用して作業環境をセットアップします。
- C# の基本知識: C# プログラミング言語の基本を理解します。
## 名前空間のインポート
C# プロジェクトで、必要な名前空間をインポートすることから始めます。
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## ステップ 1: プレゼンテーション クラスをインスタンス化する

のインスタンスを作成します。`Presentation`クラスを指定し、ドキュメントが保存されているディレクトリを指定します。

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    //この using ブロック内で次の手順を続行します。
}
```

## ステップ 2: 最初のスライドにアクセスする

プレゼンテーションから最初のスライドを取得します。

```csharp
ISlide sld = pres.Slides[0];
```

## ステップ 3: 形状コレクションへのアクセス

スライド上の図形のコレクションにアクセスします。

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## ステップ 4: グループ図形を追加する

グループ図形をスライドに追加します。

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## ステップ 5: グループ図形内に図形を追加する

グループ シェイプに個々のシェイプを追加します。

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## ステップ 6: グループ シェイプ フレームを追加する

グループ形状全体のフレームを定義します。

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## ステップ 7: プレゼンテーションを保存する

変更したプレゼンテーションを指定したディレクトリに保存します。

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

C# アプリケーションでこれらの手順を繰り返し、Aspose.Slides を使用してプレゼンテーション スライドにグループ図形を正常に作成します。

## 結論
このチュートリアルでは、Aspose.Slides for .NET を使用してグループ シェイプを作成するプロセスについて説明しました。これらの手順に従うことで、PowerPoint プレゼンテーションの視覚的な魅力と構成を強化できます。
## よくある質問
### Aspose.Slides は .NET の最新バージョンと互換性がありますか?
はい、Aspose.Slides は最新の .NET バージョンをサポートするために定期的に更新されます。チェックしてください[ドキュメンテーション](https://reference.aspose.com/slides/net/)互換性の詳細については。
### 購入する前に Aspose.Slides を試してみることはできますか?
絶対に！無料の試用版をダウンロードできます[ここ](https://releases.aspose.com/).
### Aspose.Slides 関連のクエリのサポートはどこで見つけられますか?
 Aspose.Slides にアクセスしてください[フォーラム](https://forum.aspose.com/c/slides/11)コミュニティのサポートとディスカッションのために。
### Aspose.Slides の一時ライセンスを取得するにはどうすればよいですか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides の完全なライセンスはどこで購入できますか?
からライセンスを購入できます。[購入ページ](https://purchase.aspose.com/buy).
