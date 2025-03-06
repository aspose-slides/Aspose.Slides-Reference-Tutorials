---
title: Aspose.Slides .NET チュートリアルを使用して PowerPoint で図形を非表示にする
linktitle: Aspose.Slides を使用してプレゼンテーション スライド内の図形を非表示にする
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint スライド内の図形を非表示にする方法を学びます。このステップ バイ ステップ ガイドを使用して、プログラムでプレゼンテーションをカスタマイズします。
weight: 21
url: /ja/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## 導入
プレゼンテーションの動的な世界では、カスタマイズが重要です。Aspose.Slides for .NET は、PowerPoint プレゼンテーションをプログラムで操作するための強力なソリューションを提供します。一般的な要件の 1 つは、スライド内の特定の図形を非表示にする機能です。このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーション スライド内の図形を非表示にするプロセスについて説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。ダウンロードできます。[ここ](https://releases.aspose.com/slides/net/).
- 開発環境: .NET 用の好みの開発環境を設定します。
- C# の基礎知識: 提供されるコード例は C# 言語で書かれているので、C# について理解しておいてください。
## 名前空間のインポート
Aspose.Slides の使用を開始するには、C# プロジェクトに必要な名前空間をインポートします。これにより、必要なクラスとメソッドにアクセスできるようになります。
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
ここで、明確かつ簡潔に理解できるように、サンプル コードを複数のステップに分解してみましょう。
## ステップ1: プロジェクトを設定する
新しい C# プロジェクトを作成し、Aspose.Slides ライブラリを必ず含めてください。
## ステップ2: プレゼンテーションを作成する
インスタンス化する`Presentation`クラスは、PowerPoint ファイルを表します。スライドを追加して、その参照を取得します。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## ステップ3: スライドに図形を追加する
特定の寸法を持つ長方形や月などのオートシェイプをスライドに追加します。
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## ステップ4: 代替テキストに基づいて図形を非表示にする
代替テキストを指定し、このテキストに一致する図形を非表示にします。
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## ステップ5: プレゼンテーションを保存する
変更したプレゼンテーションを PPTX 形式でディスクに保存します。
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## 結論
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## よくある質問
### Aspose.Slides は .NET Core と互換性がありますか?
はい、Aspose.Slides は .NET Core をサポートしており、開発環境に柔軟性を提供します。
### 代替テキスト以外の条件に基づいて図形を非表示にすることはできますか?
もちろんです! 図形の種類、色、位置などのさまざまな属性に基づいて非表示ロジックをカスタマイズできます。
### Aspose.Slides の追加ドキュメントはどこで入手できますか?
ドキュメントを見る[ここ](https://reference.aspose.com/slides/net/)詳しい情報と例については、こちらをご覧ください。
### Aspose.Slides には一時ライセンスがありますか?
はい、一時免許証を取得できます[ここ](https://purchase.aspose.com/temporary-license/)テスト目的のため。
### Aspose.Slides のコミュニティ サポートを受けるにはどうすればよいですか?
 Aspose.Slidesコミュニティに参加しましょう[フォーラム](https://forum.aspose.com/c/slides/11)議論と支援のため。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
