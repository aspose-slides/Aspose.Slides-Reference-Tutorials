---
"description": "Aspose.Slides for .NET を使用して、PowerPoint スライド内の図形を非表示にする方法を学びます。このステップバイステップガイドに従って、プログラムでプレゼンテーションをカスタマイズします。"
"linktitle": "Aspose.Slides を使用してプレゼンテーション スライド内の図形を非表示にする"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "Aspose.Slides .NET チュートリアルで PowerPoint の図形を非表示にする"
"url": "/ja/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET チュートリアルで PowerPoint の図形を非表示にする

## 導入
プレゼンテーションのダイナミックな世界では、カスタマイズが鍵となります。Aspose.Slides for .NET は、PowerPoint プレゼンテーションをプログラムで操作するための強力なソリューションを提供します。よくある要件の一つとして、スライド内の特定の図形を非表示にしたいという要望があります。このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションスライド内の図形を非表示にする手順を説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
- Aspose.Slides for .NET: Aspose.Slidesライブラリがインストールされていることを確認してください。ダウンロードできます。 [ここ](https://releases。aspose.com/slides/net/).
- 開発環境: .NET 用の希望する開発環境を設定します。
- C# の基礎知識: 提供されるコード例は C# 言語で書かれているので、C# について理解しておいてください。
## 名前空間のインポート
Aspose.Slides を使い始めるには、C# プロジェクトに必要な名前空間をインポートします。これにより、必要なクラスとメソッドにアクセスできるようになります。
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
ここで、明確かつ簡潔に理解できるように、サンプル コードを複数のステップに分解してみましょう。
## ステップ1: プロジェクトの設定
新しい C# プロジェクトを作成し、Aspose.Slides ライブラリを必ず含めます。
## ステップ2: プレゼンテーションを作成する
インスタンス化する `Presentation` クラスはPowerPointファイルを表します。スライドを追加し、その参照を取得します。
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
おめでとうございます！Aspose.Slides for .NET を使ってプレゼンテーション内の図形を非表示にできました。これにより、プログラムで動的かつカスタマイズされたスライドを作成する可能性が広がります。
---
## よくある質問
### Aspose.Slides は .NET Core と互換性がありますか?
はい、Aspose.Slides は .NET Core をサポートしており、開発環境に柔軟性を提供します。
### 代替テキスト以外の条件に基づいて図形を非表示にすることはできますか?
もちろんです！図形の種類、色、位置などのさまざまな属性に基づいて、非表示ロジックをカスタマイズできます。
### Aspose.Slides の追加ドキュメントはどこで入手できますか?
ドキュメントを見る [ここ](https://reference.aspose.com/slides/net/) 詳しい情報と例については、こちらをご覧ください。
### Aspose.Slides には一時ライセンスがありますか?
はい、臨時免許証を取得できます [ここ](https://purchase.aspose.com/temporary-license/) テスト目的のため。
### Aspose.Slides のコミュニティ サポートを受けるにはどうすればよいですか?
Aspose.Slidesコミュニティに参加しましょう [フォーラム](https://forum.aspose.com/c/slides/11) 議論と支援のため。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}