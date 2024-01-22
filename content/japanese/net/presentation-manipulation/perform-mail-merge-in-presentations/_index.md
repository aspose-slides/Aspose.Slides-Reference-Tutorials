---
title: プレゼンテーションで差し込み印刷を実行する
linktitle: プレゼンテーションで差し込み印刷を実行する
second_title: Aspose.Slides .NET PowerPoint 処理 API
description: このステップバイステップ ガイドでは、Aspose.Slides for .NET を使用したプレゼンテーションでの差し込み印刷について学習します。ダイナミックでパーソナライズされたプレゼンテーションを簡単に作成できます。
type: docs
weight: 21
url: /ja/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## 導入
.NET 開発の世界では、動的でパーソナライズされたプレゼンテーションを作成することが一般的な要件です。このプロセスを簡素化する強力なツールの 1 つは、Aspose.Slides for .NET です。このチュートリアルでは、Aspose.Slides for .NET を使用してプレゼンテーションで差し込み印刷を実行するという興味深い領域を掘り下げていきます。
## 前提条件
この作業を開始する前に、次の前提条件が満たされていることを確認してください。
- Aspose.Slides for .NET ライブラリ: Aspose.Slides for .NET ライブラリがインストールされていることを確認します。からダウンロードできます[ここ](https://releases.aspose.com/slides/net/).
- ドキュメント テンプレート: 差し込み印刷のベースとして機能するプレゼンテーション テンプレート (例: PresentationTemplate.pptx) を準備します。
- データ ソース: 差し込み印刷用のデータ ソースが必要です。この例では XML データ (TestData.xml) を使用しますが、Aspose.Slides は RDBMS などのさまざまなデータ ソースをサポートしています。
ここで、Aspose.Slides for .NET を使用してプレゼンテーションで差し込み印刷を実行する手順を詳しく見てみましょう。
## 名前空間のインポート
まず、Aspose.Slides が提供する機能を利用するために必要な名前空間をインポートしていることを確認します。
```csharp
using System;
using System.Collections.Generic;
using System.Data;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Export;
using DataTable = System.Data.DataTable;
```
## ステップ 1: ドキュメント ディレクトリを設定する
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
//結果パスが存在するかどうかを確認する
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## ステップ 2: XML データを使用して DataSet を作成する
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## ステップ 3: レコードをループして個別のプレゼンテーションを作成する
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    //結果（個別）プレゼンテーション名を作成します
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    //プレゼンテーションテンプレートをロードする
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        //テキスト ボックスにメイン テーブルのデータを入力します。
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        //データベースから画像を取得する
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //プレゼンテーションの図枠に画像を挿入する
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        //データを入力するためのテキスト フレームを取得して準備します。
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        //スタッフデータを入力する
        FillStaffList(textFrame, userRow, staffListTable);
        //計画の事実データを入力します
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## ステップ 4: テキスト フレームにリストとしてデータを入力する
```csharp
static void FillStaffList(ITextFrame textFrame, DataRow userRow, DataTable staffListTable)
{
    foreach (DataRow listRow in staffListTable.Rows)
    {
        if (listRow["UserId"].ToString() == userRow["Id"].ToString())
        {
            Paragraph para = new Paragraph();
            para.ParagraphFormat.Bullet.Type = BulletType.Symbol;
            para.ParagraphFormat.Bullet.Char = Convert.ToChar(8226);
            para.Text = listRow["Name"].ToString();
            para.ParagraphFormat.Bullet.Color.ColorType = ColorType.RGB;
            para.ParagraphFormat.Bullet.Color.Color = Color.Black;
            para.ParagraphFormat.Bullet.IsBulletHardColor = NullableBool.True;
            para.ParagraphFormat.Bullet.Height = 100;
            textFrame.Paragraphs.Add(para);
        }
    }
}
```
## ステップ 5: セカンダリ PlanFact テーブルからデータ チャートを入力する
```csharp
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";
    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();
    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;
    //線系列のデータ ポイントを追加する
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries
(cellsFactory.GetCell(worksheetIndex, 1, 1, double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2, double.Parse(selRows[0]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1, double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2, double.Parse(selRows[1]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[2]["FactData"].ToString())));
    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1, double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2, double.Parse(selRows[3]["FactData"].ToString())));
    chart.ChartData.SetRange(range);
}
```
これらの手順は、Aspose.Slides for .NET を使用してプレゼンテーションで差し込み印刷を実行するための包括的なガイドを示しています。ここで、よくある質問に答えてみましょう。
## よくある質問
### 1. Aspose.Slides for .NET はさまざまなデータ ソースと互換性がありますか?
はい、Aspose.Slides for .NET は、XML、RDBMS などを含むさまざまなデータ ソースをサポートしています。
### 2. 生成されたプレゼンテーションの箇条書きの外観をカスタマイズできますか?
確かに！に示すように、箇条書きの外観を完全に制御できます。`FillStaffList`方法。
### 3. Aspose.Slides for .NET を使用してどのような種類のグラフを作成できますか?
Aspose.Slides for .NET は、この例で示した折れ線グラフ、棒グラフ、円グラフなどを含む幅広いグラフをサポートしています。
### 4. Aspose.Slides for .NET に関するサポートやサポートを受けるにはどうすればよいですか?
サポートと支援が必要な場合は、次のサイトにアクセスしてください。[Aspose.Slides フォーラム](https://forum.aspose.com/c/slides/11).
### 5. 購入する前に Aspose.Slides for .NET を試すことはできますか?
確かに！ Aspose.Slides for .NET の無料トライアルは、次のサイトから利用できます。[ここ](https://releases.aspose.com/).
## 結論
このチュートリアルでは、プレゼンテーションで差し込み印刷を実行する際の Aspose.Slides for .NET の魅力的な機能を調べました。ステップバイステップのガイドに従うことで、ダイナミックでパーソナライズされたプレゼンテーションを簡単に作成できます。 Aspose.Slides を使用して .NET 開発エクスペリエンスを向上させ、シームレスなプレゼンテーションを生成します。