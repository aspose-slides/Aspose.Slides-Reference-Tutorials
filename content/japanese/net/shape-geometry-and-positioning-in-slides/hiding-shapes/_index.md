---
title: Aspose.Slides を使用して PowerPoint で図形を非表示にする .NET チュートリアル
linktitle: Aspose.Slides を使用してプレゼンテーション スライド内の図形を非表示にする
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して PowerPoint スライド内の図形を非表示にする方法を学習します。このステップバイステップ ガイドを使用して、プレゼンテーションをプログラムでカスタマイズします。
type: docs
weight: 21
url: /ja/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## 導入
ダイナミックなプレゼンテーションの世界では、カスタマイズが鍵となります。 Aspose.Slides for .NET は、PowerPoint プレゼンテーションをプログラムで操作するための強力なソリューションを提供します。一般的な要件の 1 つは、スライド内の特定の図形を非表示にする機能です。このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーション スライド内の図形を非表示にするプロセスについて説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slides ライブラリがインストールされていることを確認してください。ダウンロードできます[ここ](https://releases.aspose.com/slides/net/).
- 開発環境: .NET 用の優先開発環境をセットアップします。
- C# の基本知識: 提供されているコード例はこの言語で提供されているため、C# に慣れてください。
## 名前空間のインポート
Aspose.Slides の使用を開始するには、必要な名前空間を C# プロジェクトにインポートします。これにより、必要なクラスとメソッドに確実にアクセスできるようになります。
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
ここで、明確かつ簡潔に理解できるように、サンプル コードを複数のステップに分割してみましょう。
## ステップ 1: プロジェクトをセットアップする
新しい C# プロジェクトを作成し、必ず Aspose.Slides ライブラリを含めてください。
## ステップ 2: プレゼンテーションを作成する
インスタンス化します`Presentation` PowerPoint ファイルを表すクラス。スライドを追加し、それへの参照を取得します。
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## ステップ 3: スライドに図形を追加する
特定の寸法の長方形や月などのオートシェイプをスライドに追加します。
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## ステップ 4: 代替テキストに基づいて図形を非表示にする
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
## ステップ 5: プレゼンテーションを保存する
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
絶対に！形状タイプ、色、位置などのさまざまな属性に基づいて非表示ロジックをカスタマイズできます。
### Aspose.Slides の追加ドキュメントはどこで見つけられますか?
ドキュメントを調べる[ここ](https://reference.aspose.com/slides/net/)詳細な情報と例については、
### Aspose.Slides の一時ライセンスは利用できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/)テスト目的のため。
### Aspose.Slides のコミュニティ サポートを得るにはどうすればよいですか?
 Aspose.Slides コミュニティに参加してください。[フォーラム](https://forum.aspose.com/c/slides/11)議論と支援のために。