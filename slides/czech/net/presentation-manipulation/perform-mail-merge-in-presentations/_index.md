---
"description": "Naučte se hromadnou korespondenci v prezentacích pomocí Aspose.Slides pro .NET v tomto podrobném návodu. Vytvářejte dynamické a personalizované prezentace bez námahy."
"linktitle": "Provádění hromadné korespondence v prezentacích"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Provádění hromadné korespondence v prezentacích"
"url": "/cs/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Provádění hromadné korespondence v prezentacích

## Zavedení
Ve světě vývoje pro .NET je vytváření dynamických a personalizovaných prezentací běžným požadavkem. Jedním z účinných nástrojů, které tento proces zjednodušují, je Aspose.Slides for .NET. V tomto tutoriálu se ponoříme do fascinující oblasti hromadné korespondence v prezentacích pomocí Aspose.Slides for .NET.
## Předpoklady
Než se na tuto cestu vydáme, ujistěte se, že máte splněny následující předpoklady:
- Knihovna Aspose.Slides pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/net/).
- Šablona dokumentu: Připravte šablonu prezentace (např. PresentationTemplate.pptx), která bude sloužit jako základ pro hromadnou korespondenci.
- Zdroj dat: Pro hromadnou korespondenci potřebujete zdroj dat. V našem příkladu použijeme data XML (TestData.xml), ale Aspose.Slides podporuje různé zdroje dat, jako například RDBMS.
Nyní se ponoříme do kroků provádění hromadné korespondence v prezentacích pomocí Aspose.Slides pro .NET.
## Importovat jmenné prostory
Nejprve se ujistěte, že jste importovali potřebné jmenné prostory, abyste mohli využívat funkce poskytované Aspose.Slides:
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
## Krok 1: Nastavení adresáře dokumentů
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Zkontrolujte, zda existuje výsledná cesta
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Krok 2: Vytvoření datové sady pomocí dat XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Krok 3: Procházení záznamů a vytváření jednotlivých prezentací
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // vytvořit název prezentace výsledku (individuální)
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Načíst šablonu prezentace
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Vyplňte textová pole daty z hlavní tabulky
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Získejte obrázek z databáze
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Vložit obrázek do rámečku prezentace
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Získání a příprava textového rámečku k naplnění daty
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Vyplňte údaje o zaměstnancích
        FillStaffList(textFrame, userRow, staffListTable);
        // Vyplňte fakta plánu
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Krok 4: Vyplnění textového rámečku daty jako seznam
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
## Krok 5: Vyplňte datovou tabulku ze sekundární tabulky PlanFact
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
    // Přidání datových bodů pro čárové řady
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
Tyto kroky představují komplexního průvodce hromadnou korespondencí v prezentacích pomocí Aspose.Slides pro .NET. Nyní se podívejme na některé často kladené otázky.
## Často kladené otázky
### 1. Je Aspose.Slides pro .NET kompatibilní s různými zdroji dat?
Ano, Aspose.Slides pro .NET podporuje různé zdroje dat, včetně XML, RDBMS a dalších.
### 2. Mohu si přizpůsobit vzhled odrážek ve vygenerované prezentaci?
Jistě! Máte plnou kontrolu nad vzhledem odrážek, jak je ukázáno v `FillStaffList` metoda.
### 3. Jaké typy grafů mohu vytvářet pomocí Aspose.Slides pro .NET?
Aspose.Slides pro .NET podporuje širokou škálu grafů, včetně spojnicových grafů, jak je znázorněno v našem příkladu, sloupcových grafů, koláčových grafů a dalších.
### 4. Jak získám podporu nebo vyhledám pomoc s Aspose.Slides pro .NET?
Pro podporu a pomoc můžete navštívit [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Mohu si před zakoupením vyzkoušet Aspose.Slides pro .NET?
Jistě! Můžete využít bezplatnou zkušební verzi Aspose.Slides pro .NET od [zde](https://releases.aspose.com/).
## Závěr
tomto tutoriálu jsme prozkoumali vzrušující možnosti Aspose.Slides pro .NET při hromadné korespondenci v prezentacích. Dodržováním podrobných pokynů můžete bez námahy vytvářet dynamické a personalizované prezentace. Posuňte své zkušenosti s vývojem v .NET na vyšší úroveň s Aspose.Slides pro bezproblémové generování prezentací.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}