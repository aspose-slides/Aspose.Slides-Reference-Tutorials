---
title: Aspose.Slides .NET で楕円を簡単に作成する
linktitle: Aspose.Slides を使用してプレゼンテーション スライドにシンプルな楕円形を作成する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: Aspose.Slides for .NET を使用して、プレゼンテーション スライドに魅力的な楕円形を作成する方法を学びます。簡単な手順でダイナミックなデザインを作成できます。
type: docs
weight: 11
url: /ja/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## 導入
プレゼンテーション デザインのダイナミックな世界では、楕円などの図形を組み込むことで、創造性とプロフェッショナリズムの雰囲気を演出できます。Aspose.Slides for .NET は、プレゼンテーション ファイルをプログラムで操作するための強力なソリューションを提供します。このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーション スライドに単純な楕円を作成する手順を説明します。
## 前提条件
チュートリアルに進む前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Slides for .NET: Aspose.Slidesライブラリが.NET用にインストールされていることを確認してください。[リリースページ](https://releases.aspose.com/slides/net/).
- 開発環境: マシンに .NET 開発環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトでは、まず必要な名前空間をインポートします。
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
これらの名前空間は、プレゼンテーションのスライドや図形を操作するために必要な基本的なクラスとメソッドを提供します。
## ステップ1: プレゼンテーションを設定する
まず、新しいプレゼンテーションを作成し、最初のスライドにアクセスします。これを実現するには、次のコードを追加します。
```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "Your Document Directory";
//ディレクトリがまだ存在しない場合は作成します。
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
//プレゼンテーションクラスをインスタンス化する
using (Presentation pres = new Presentation())
{
    //最初のスライドを取得する
    ISlide sld = pres.Slides[0];
```
このコードは、新しいプレゼンテーションを初期化し、さらに操作するために最初のスライドを選択します。
## ステップ2: 楕円形を追加する
さて、スライドに楕円を追加してみましょう。`AddAutoShape`方法：
```csharp
//楕円形のオートシェイプを追加
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
このコード行は、座標 (50, 150) に幅 150 単位、高さ 50 単位の楕円形を作成します。
## ステップ3: プレゼンテーションを保存する
最後に、次のコードを使用して、変更したプレゼンテーションを指定したファイル名でディスクに保存します。
```csharp
// PPTXファイルをディスクに書き込む
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
この手順により、変更が保持され、新しく追加された楕円形を含む結果のプレゼンテーションを表示できるようになります。
## 結論
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## よくある質問
### 楕円形をさらにカスタマイズできますか?
はい、特定のデザイン要件に合わせて、色、サイズ、位置など、楕円形のさまざまなプロパティを変更できます。
### Aspose.Slides は最新の .NET フレームワークと互換性がありますか?
はい、Aspose.Slides は最新の .NET フレームワークとの互換性を確保するために定期的に更新されます。
### Aspose.Slides のその他のチュートリアルや例はどこで見つかりますか?
訪問[ドキュメンテーション](https://reference.aspose.com/slides/net/)包括的なガイドと例については、こちらをご覧ください。
### Aspose.Slides の一時ライセンスを取得するにはどうすればよいですか?
フォロー[一時ライセンスリンク](https://purchase.aspose.com/temporary-license/)テスト目的で一時ライセンスを申請します。
### サポートが必要ですか、または具体的な質問がありますか?
訪問[Aspose.Slides サポート フォーラム](https://forum.aspose.com/c/slides/11)コミュニティや専門家からの支援を受けることができます。