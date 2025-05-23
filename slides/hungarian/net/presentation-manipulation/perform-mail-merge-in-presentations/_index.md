---
"description": "Tanulja meg a körlevelezést prezentációkban az Aspose.Slides for .NET használatával ebben a lépésről lépésre szóló útmutatóban. Készítsen dinamikus, személyre szabott prezentációkat könnyedén."
"linktitle": "Körlevél végrehajtása prezentációkban"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Körlevél végrehajtása prezentációkban"
"url": "/hu/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Körlevél végrehajtása prezentációkban

## Bevezetés
.NET fejlesztés világában a dinamikus és személyre szabott prezentációk létrehozása gyakori követelmény. Az Aspose.Slides for .NET egy hatékony eszköz, amely leegyszerűsíti ezt a folyamatot. Ebben az oktatóanyagban elmerülünk a körlevélkészítés lenyűgöző világában a prezentációkban az Aspose.Slides for .NET használatával.
## Előfeltételek
Mielőtt nekivágnánk ennek az útnak, győződjünk meg róla, hogy a következő előfeltételek teljesülnek:
- Aspose.Slides for .NET könyvtár: Győződjön meg róla, hogy telepítve van az Aspose.Slides for .NET könyvtár. Letöltheti innen: [itt](https://releases.aspose.com/slides/net/).
- Dokumentumsablon: Készítsen elő egy prezentációs sablont (pl. PresentationTemplate.pptx), amely a körlevelezés alapjául szolgál majd.
- Adatforrás: Szükséged van egy adatforrásra a körlevelezéshez. A példánkban XML adatokat (TestData.xml) fogunk használni, de az Aspose.Slides különféle adatforrásokat támogat, például az RDBMS-t.
Most pedig nézzük meg a körlevelezés lépéseit a prezentációkban az Aspose.Slides for .NET használatával.
## Névterek importálása
Először is, importáld a szükséges névtereket az Aspose.Slides által biztosított funkciók kihasználásához:
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
## 1. lépés: Dokumentumkönyvtár beállítása
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Ellenőrizze, hogy létezik-e az eredményútvonal
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## 2. lépés: Adatkészlet létrehozása XML-adatok felhasználásával
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## 3. lépés: Rekordok ismétlése és egyedi prezentációk létrehozása
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // eredmény létrehozása (egyéni) prezentáció neve
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Bemutatósablon betöltése
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Szövegmezők kitöltése a fő táblázat adataival
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Kép beolvasása az adatbázisból
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Kép beillesztése a prezentáció képkeretébe
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Szövegkeret beszerzése és előkészítése az adatokkal való kitöltéshez
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Személyzeti adatok kitöltése
        FillStaffList(textFrame, userRow, staffListTable);
        // Töltse ki a terv tényadatait
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## 4. lépés: Szövegkeret kitöltése adatokkal listaként
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
## 5. lépés: Töltse ki az adattáblázatot a másodlagos PlanFact táblából
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
    // Adatpontok hozzáadása vonalsorozatokhoz
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
Ezek a lépések átfogó útmutatót nyújtanak a körlevelek végrehajtásához prezentációkban az Aspose.Slides for .NET használatával. Most pedig válaszoljunk néhány gyakran ismételt kérdésre.
## Gyakran Ismételt Kérdések
### 1. Az Aspose.Slides for .NET kompatibilis a különböző adatforrásokkal?
Igen, az Aspose.Slides for .NET különféle adatforrásokat támogat, beleértve az XML-t, az RDBMS-t és egyebeket.
### 2. Testreszabhatom a felsorolásjelek megjelenését a létrehozott prezentációban?
Természetesen! Teljes mértékben szabályozhatod a felsorolásjelek megjelenését, ahogy az a példában is látható. `FillStaffList` módszer.
### 3. Milyen típusú diagramokat hozhatok létre az Aspose.Slides for .NET használatával?
Az Aspose.Slides for .NET számos diagramot támogat, beleértve a példánkban látható vonaldiagramokat, oszlopdiagramokat, kördiagramokat és egyebeket.
### 4. Hogyan kaphatok támogatást vagy kérhetek segítséget az Aspose.Slides for .NET-tel kapcsolatban?
Támogatásért és segítségért látogassa meg a következőt: [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### 5. Kipróbálhatom az Aspose.Slides for .NET-et vásárlás előtt?
Természetesen! Ingyenes próbaverziót kaphatsz az Aspose.Slides for .NET alkalmazásból a következő címen: [itt](https://releases.aspose.com/).
## Következtetés
Ebben az oktatóanyagban az Aspose.Slides for .NET izgalmas képességeit vizsgáltuk meg körlevelek készítésében prezentációkban. A lépésről lépésre haladó útmutató követésével könnyedén készíthet dinamikus és személyre szabott prezentációkat. Emeld magasabb szintre .NET fejlesztési tapasztalataidat az Aspose.Slides segítségével a zökkenőmentes prezentációk készítéséhez.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}