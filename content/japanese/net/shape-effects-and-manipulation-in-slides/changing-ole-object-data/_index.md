---
title: Aspose.Slides を使用したプレゼンテーション内の OLE オブジェクト データの変更
linktitle: Aspose.Slides を使用したプレゼンテーション内の OLE オブジェクト データの変更
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: OLE オブジェクト データを簡単に変更できる Aspose.Slides for .NET の機能を試してください。動的なコンテンツを使用してプレゼンテーションを強化します。
type: docs
weight: 25
url: /ja/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---
## 導入
ダイナミックでインタラクティブな PowerPoint プレゼンテーションを作成することは、今日のデジタル世界では一般的な要件です。これを実現する強力なツールの 1 つは、開発者が PowerPoint プレゼンテーションをプログラムで操作および強化できる堅牢なライブラリである Aspose.Slides for .NET です。このチュートリアルでは、Aspose.Slides を使用してプレゼンテーション スライド内の OLE (Object Linking and Embedding) オブジェクト データを変更するプロセスを詳しく説明します。
## 前提条件
Aspose.Slides for .NET の使用を開始する前に、次の前提条件が満たされていることを確認してください。
1. 開発環境: .NET がインストールされた開発環境をセットアップします。
2.  Aspose.Slides ライブラリ: Aspose.Slides for .NET ライブラリをダウンロードしてインストールします。図書館を見つけることができます[ここ](https://releases.aspose.com/slides/net/).
3. 基本的な理解: C# プログラミングと PowerPoint プレゼンテーションの基本概念を理解します。
## 名前空間のインポート
C# プロジェクトで、Aspose.Slides 機能を使用するために必要な名前空間をインポートします。
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## ステップ 1: プロジェクトをセットアップする
まず、新しい C# プロジェクトを作成し、Aspose.Slides ライブラリをインポートします。プロジェクトが正しく構成されており、必要な依存関係が適切に設定されていることを確認してください。
## ステップ 2: プレゼンテーションとスライドにアクセスする
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## ステップ 3: OLE オブジェクトを見つける
スライド内のすべての図形を移動して、OLE オブジェクト フレームを見つけます。
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## ステップ 4: ワークブック データの読み取りと変更
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        //ワークブック内のオブジェクト データの読み取り
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            //ワークブックデータの変更
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            //Oleフレームオブジェクトデータの変更
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## ステップ 5: プレゼンテーションを保存する
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## 結論
これらの手順に従うと、Aspose.Slides for .NET を使用してプレゼンテーション スライド内の OLE オブジェクト データをシームレスに変更できます。これにより、特定のニーズに合わせてカスタマイズされたダイナミックなプレゼンテーションを作成する可能性が広がります。
## よくある質問
### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者がプログラムで PowerPoint プレゼンテーションを操作できるようにする強力なライブラリであり、簡単な操作と拡張を可能にします。
### Aspose.Slides のドキュメントはどこで見つけられますか?
 Aspose.Slides for .NET のドキュメントは次のとおりです。[ここ](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET をダウンロードするにはどうすればよいですか?
リリースページからライブラリをダウンロードできます[ここ](https://releases.aspose.com/slides/net/).
### Aspose.Slides に利用できる無料トライアルはありますか?
はい、無料トライアルにアクセスできます[ここ](https://releases.aspose.com/).
### Aspose.Slides for .NET のサポートはどこで入手できますか?
サポートとディスカッションについては、次のサイトにアクセスしてください。[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).