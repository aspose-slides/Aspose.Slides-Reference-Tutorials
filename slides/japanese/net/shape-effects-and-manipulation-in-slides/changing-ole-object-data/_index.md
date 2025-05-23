---
"description": "Aspose.Slides for .NET のパワーを活用して、OLE オブジェクトのデータを簡単に変更しましょう。動的なコンテンツでプレゼンテーションを充実させましょう。"
"linktitle": "Aspose.Slides を使用してプレゼンテーション内の OLE オブジェクト データを変更する"
"second_title": "Aspose.Slides .NET PowerPoint 処理 API"
"title": "Aspose.Slides を使用してプレゼンテーション内の OLE オブジェクト データを変更する"
"url": "/ja/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides を使用してプレゼンテーション内の OLE オブジェクト データを変更する

## 導入
ダイナミックでインタラクティブなPowerPointプレゼンテーションの作成は、今日のデジタル世界では当たり前の要件となっています。これを実現するための強力なツールの一つが、Aspose.Slides for .NETです。これは、開発者がPowerPointプレゼンテーションをプログラム的に操作・強化できる強力なライブラリです。このチュートリアルでは、Aspose.Slidesを使用してプレゼンテーションスライド内のOLE（オブジェクトのリンクと埋め込み）オブジェクトデータを変更するプロセスを詳しく解説します。
## 前提条件
Aspose.Slides for .NET の使用を開始する前に、次の前提条件が満たされていることを確認してください。
1. 開発環境: .NET がインストールされた開発環境をセットアップします。
2. Aspose.Slidesライブラリ: Aspose.Slides for .NETライブラリをダウンロードしてインストールしてください。ライブラリは次の場所にあります。 [ここ](https://releases。aspose.com/slides/net/).
3. 基本的な理解: C# プログラミングと PowerPoint プレゼンテーションの基本的な概念を理解します。
## 名前空間のインポート
C# プロジェクトで、Aspose.Slides 機能を使用するために必要な名前空間をインポートします。
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## ステップ1: プロジェクトの設定
まず、新しいC#プロジェクトを作成し、Aspose.Slidesライブラリをインポートします。プロジェクトが正しく構成され、必要な依存関係が設定されていることを確認してください。
## ステップ2: プレゼンテーションとスライドにアクセスする
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## ステップ3: OLEオブジェクトの検索
スライド内のすべての図形を走査して、OLE オブジェクト フレームを見つけます。
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
## ステップ4: ワークブックデータの読み取りと変更
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // ワークブック内のオブジェクトデータの読み取り
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // ワークブックデータの変更
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Oleフレームオブジェクトデータの変更
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## ステップ5: プレゼンテーションを保存する
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## 結論
これらの手順に従うことで、Aspose.Slides for .NET を使用してプレゼンテーションスライド内のOLEオブジェクトデータをシームレスに変更できます。これにより、特定のニーズに合わせてカスタマイズされたダイナミックなプレゼンテーションを作成するための可能性が広がります。
## よくある質問
### Aspose.Slides for .NET とは何ですか?
Aspose.Slides for .NET は、開発者が PowerPoint プレゼンテーションをプログラムで操作して簡単に操作および拡張できるようにする強力なライブラリです。
### Aspose.Slides のドキュメントはどこにありますか?
Aspose.Slides for .NETのドキュメントは以下にあります。 [ここ](https://reference。aspose.com/slides/net/).
### Aspose.Slides for .NET をダウンロードするにはどうすればいいですか?
ライブラリはリリースページからダウンロードできます [ここ](https://releases。aspose.com/slides/net/).
### Aspose.Slides の無料トライアルはありますか?
はい、無料トライアルにアクセスできます [ここ](https://releases。aspose.com/).
### Aspose.Slides for .NET のサポートはどこで受けられますか?
サポートやディスカッションについては、 [Aspose.Slides フォーラム](https://forum。aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}