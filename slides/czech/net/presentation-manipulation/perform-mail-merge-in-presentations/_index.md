---
title: Proveďte hromadnou korespondenci v prezentacích
linktitle: Proveďte hromadnou korespondenci v prezentacích
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se hromadnou korespondenci v prezentacích pomocí Aspose.Slides pro .NET v tomto podrobném průvodci. Vytvářejte dynamické, personalizované prezentace bez námahy.
type: docs
weight: 21
url: /cs/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## Úvod
Ve světě vývoje .NET je vytváření dynamických a personalizovaných prezentací běžným požadavkem. Jedním mocným nástrojem, který tento proces zjednodušuje, je Aspose.Slides for .NET. V tomto tutoriálu se ponoříme do fascinující sféry provádění hromadné korespondence v prezentacích pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se vydáme na tuto cestu, ujistěte se, že máte splněny následující předpoklady:
- Knihovna Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).
- Šablona dokumentu: Připravte si šablonu prezentace (např. PresentationTemplate.pptx), která bude sloužit jako základ pro hromadnou korespondenci.
- Zdroj dat: Pro hromadnou korespondenci potřebujete zdroj dat. V našem příkladu použijeme data XML (TestData.xml), ale Aspose.Slides podporuje různé zdroje dat, jako je RDBMS.
Nyní se pojďme ponořit do kroků provádění hromadné korespondence v prezentacích pomocí Aspose.Slides pro .NET.
## Importovat jmenné prostory
Nejprve se ujistěte, že importujete potřebné jmenné prostory, abyste mohli využít funkcí poskytovaných Aspose.Slides:
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
## Krok 1: Nastavte adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Zkontrolujte, zda existuje cesta k výsledku
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Krok 2: Vytvořte datovou sadu pomocí dat XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Krok 3: Procházení záznamů a vytváření individuálních prezentací
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // vytvořit výsledek (individuální) název prezentace
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Načíst šablonu prezentace
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Vyplňte textová pole daty z hlavní tabulky
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Získejte obrázek z databáze
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Vložte obrázek do rámečku obrázku prezentace
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Získejte a připravte textový rámeček pro jeho vyplnění daty
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Vyplňte údaje o zaměstnancích
        FillStaffList(textFrame, userRow, staffListTable);
        // Vyplňte údaje o faktech plánu
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Krok 4: Vyplňte textový rámeček daty jako seznam
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
## Krok 5: Vyplňte datový graf ze sekundární tabulky PlanFact
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
    // Přidejte datové body pro řadu čar
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
Tyto kroky demonstrují komplexního průvodce prováděním hromadné korespondence v prezentacích pomocí Aspose.Slides for .NET. Nyní se podívejme na některé často kladené otázky.
## Často kladené otázky
### 1. Je Aspose.Slides for .NET kompatibilní s různými zdroji dat?
Ano, Aspose.Slides for .NET podporuje různé zdroje dat, včetně XML, RDBMS a dalších.
### 2. Mohu upravit vzhled odrážek ve vygenerované prezentaci?
 Rozhodně! Máte plnou kontrolu nad vzhledem odrážek, jak je ukázáno v`FillStaffList` metoda.
### 3. Jaké typy grafů mohu vytvořit pomocí Aspose.Slides pro .NET?
Aspose.Slides for .NET podporuje širokou škálu grafů, včetně spojnicových grafů, jak je ukázáno v našem příkladu, sloupcových grafů, koláčových grafů a dalších.
### 4. Jak získám podporu nebo pomoc s Aspose.Slides for .NET?
 Pro podporu a pomoc můžete navštívit stránku[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Mohu Aspose.Slides for .NET vyzkoušet před nákupem?
 Rozhodně! Můžete využít bezplatnou zkušební verzi Aspose.Slides pro .NET od[tady](https://releases.aspose.com/).
## Závěr
V tomto tutoriálu jsme prozkoumali vzrušující schopnosti Aspose.Slides pro .NET při provádění hromadné korespondence v prezentacích. Podle tohoto podrobného průvodce můžete bez námahy vytvářet dynamické a personalizované prezentace. Zvyšte své zkušenosti s vývojem .NET pomocí Aspose.Slides pro bezproblémové generování prezentací.