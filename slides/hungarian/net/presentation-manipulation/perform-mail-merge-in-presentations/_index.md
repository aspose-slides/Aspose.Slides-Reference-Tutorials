---
title: Hajtsa végre a körlevél-egyesítést a prezentációkban
linktitle: Hajtsa végre a körlevél-egyesítést a prezentációkban
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ebben a lépésenkénti útmutatóban megismerheti a prezentációkban a körlevélkészítést az Aspose.Slides for .NET segítségével. Hozzon létre dinamikus, személyre szabott prezentációkat könnyedén.
weight: 21
url: /hu/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
A .NET fejlesztés világában általános követelmény a dinamikus és személyre szabott prezentációk készítése. Az egyik hatékony eszköz, amely leegyszerűsíti ezt a folyamatot, az Aspose.Slides for .NET. Ebben az oktatóanyagban az Aspose.Slides for .NET használatával végzett prezentációkban a körlevél-egyesítés lenyűgöző birodalmába ásunk bele.
## Előfeltételek
Mielőtt nekivágnánk ennek az útnak, győződjön meg arról, hogy a következő előfeltételeket teljesíti:
- Aspose.Slides for .NET Library: Győződjön meg arról, hogy telepítve van az Aspose.Slides for .NET könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/net/).
- Dokumentum sablon: Készítsen egy bemutatósablont (pl. PresentationTemplate.pptx), amely a körlevél-összevonás alapjaként fog szolgálni.
- Adatforrás: Szüksége van egy adatforrásra a körlevélkészítéshez. Példánkban XML-adatokat fogunk használni (TestData.xml), de az Aspose.Slides különféle adatforrásokat támogat, például az RDBMS-t.
Most pedig nézzük meg a levelek egyesítésének lépéseit bemutatókban az Aspose.Slides for .NET használatával.
## Névterek importálása
Először is győződjön meg arról, hogy importálja a szükséges névtereket az Aspose.Slides által biztosított funkciók kihasználásához:
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
## 1. lépés: Állítsa be a dokumentumkönyvtárat
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Ellenőrizze, hogy létezik-e az eredmény elérési útja
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 2. lépés: Hozzon létre egy adatkészletet XML adatok használatával
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 3. lépés: Folytassa a rekordokat és hozzon létre egyéni prezentációkat
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // eredmény (egyedi) prezentációnév létrehozása
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Bemutatósablon betöltése
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Töltse ki a szövegdobozokat a fő táblázat adataival
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Kép beszerzése az adatbázisból
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Illessze be a képet a prezentáció képkeretébe
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Szerezze meg és készítse elő a szövegkeretet az adatokkal való feltöltéshez
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Töltse ki a személyzet adatait
        FillStaffList(textFrame, userRow, staffListTable);
        // Töltse ki a terv tényadatait
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## 4. lépés: Töltse ki a szövegkeretet adatokkal listaként
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
## 5. lépés: Töltse ki az adatdiagramot a másodlagos PlanFact táblázatból
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
    // Adjon hozzá adatpontokat a vonalsorozatokhoz
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
Ezek a lépések egy átfogó útmutatót mutatnak be az Aspose.Slides for .NET használatával prezentációkban történő körlevél-egyesítéshez. Most pedig válaszoljunk néhány gyakran ismételt kérdésre.
## Gyakran Ismételt Kérdések
### 1. Az Aspose.Slides for .NET kompatibilis a különböző adatforrásokkal?
Igen, az Aspose.Slides for .NET különféle adatforrásokat támogat, beleértve az XML-t, az RDBMS-t és egyebeket.
### 2. Testreszabhatom a felsorolásjelek megjelenését a generált prezentációban?
 Biztosan! Teljes ellenőrzése alatt áll a felsorolásjelek megjelenése felett, amint azt a`FillStaffList` módszer.
### 3. Milyen típusú diagramokat hozhatok létre az Aspose.Slides for .NET használatával?
Az Aspose.Slides for .NET diagramok széles skáláját támogatja, beleértve a példánkban bemutatott vonaldiagramokat, oszlopdiagramokat, kördiagramokat és egyebeket.
### 4. Hogyan kaphatok támogatást vagy kérhetek segítséget az Aspose.Slides for .NET-hez?
 Támogatásért és segítségért látogassa meg a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### 5. Kipróbálhatom az Aspose.Slides for .NET-et vásárlás előtt?
 Biztosan! Használhatja az Aspose.Slides for .NET ingyenes próbaverzióját[itt](https://releases.aspose.com/).
## Következtetés
Ebben az oktatóanyagban az Aspose.Slides for .NET izgalmas képességeit fedeztük fel a prezentációkban a körlevél-egyesítés végrehajtásában. A lépésenkénti útmutató követésével könnyedén hozhat létre dinamikus és személyre szabott prezentációkat. Növelje .NET fejlesztési tapasztalatait az Aspose.Slides segítségével a zökkenőmentes prezentációk létrehozásához.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
