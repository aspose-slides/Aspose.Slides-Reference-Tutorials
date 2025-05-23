---
"description": "Lär dig dokumentkoppling i presentationer med Aspose.Slides för .NET i den här steg-för-steg-guiden. Skapa dynamiska, personliga presentationer utan ansträngning."
"linktitle": "Utför dokumentkoppling i presentationer"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Utför dokumentkoppling i presentationer"
"url": "/sv/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Utför dokumentkoppling i presentationer

## Introduktion
.NET-utvecklingens värld är det vanligt att skapa dynamiska och personliga presentationer. Ett kraftfullt verktyg som förenklar denna process är Aspose.Slides för .NET. I den här handledningen ska vi fördjupa oss i den fascinerande världen av att utföra dokumentkoppling i presentationer med Aspose.Slides för .NET.
## Förkunskapskrav
Innan vi ger oss ut på denna resa, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET-biblioteket: Se till att du har Aspose.Slides för .NET-biblioteket installerat. Du kan ladda ner det från [här](https://releases.aspose.com/slides/net/).
- Dokumentmall: Förbered en presentationsmall (t.ex. PresentationTemplate.pptx) som ska fungera som bas för dokumentkoppling.
- Datakälla: Du behöver en datakälla för dokumentkoppling. I vårt exempel använder vi XML-data (TestData.xml), men Aspose.Slides stöder olika datakällor som RDBMS.
Nu ska vi gå in på stegen för att utföra dokumentkoppling i presentationer med Aspose.Slides för .NET.
## Importera namnrymder
Först, se till att du importerar de namnrymder som behövs för att utnyttja funktionerna i Aspose.Slides:
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
## Steg 1: Konfigurera din dokumentkatalog
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Kontrollera om sökvägen för resultat finns
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Steg 2: Skapa en datamängd med XML-data
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Steg 3: Gå igenom poster och skapa individuella presentationer
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // skapa resultat (individuell) presentationsnamn
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Ladda presentationsmall
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Fyll textrutor med data från huvudtabellen
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Hämta bild från databasen
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Infoga bild i presentationens bildram
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Hämta och förbered textramen för att fylla den med data
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Fyll i personaldata
        FillStaffList(textFrame, userRow, staffListTable);
        // Fyll i planfaktadata
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Steg 4: Fyll textramen med data som en lista
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
## Steg 5: Fyll i datadiagrammet från den sekundära PlanFact-tabellen
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
    // Lägg till datapunkter för linjeserier
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
Dessa steg visar en omfattande guide för hur man utför dokumentkoppling i presentationer med Aspose.Slides för .NET. Nu ska vi ta upp några vanliga frågor.
## Vanliga frågor
### 1. Är Aspose.Slides för .NET kompatibelt med olika datakällor?
Ja, Aspose.Slides för .NET stöder olika datakällor, inklusive XML, RDBMS och mer.
### 2. Kan jag anpassa utseendet på punktlistor i den genererade presentationen?
Absolut! Du har full kontroll över utseendet på punktlistor, vilket visas i `FillStaffList` metod.
### 3. Vilka typer av diagram kan jag skapa med Aspose.Slides för .NET?
Aspose.Slides för .NET stöder ett brett utbud av diagram, inklusive linjediagram som visas i vårt exempel, stapeldiagram, cirkeldiagram och mer.
### 4. Hur får jag support eller söker hjälp med Aspose.Slides för .NET?
För stöd och hjälp kan du besöka [Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### 5. Kan jag prova Aspose.Slides för .NET innan jag köper?
Absolut! Du kan prova Aspose.Slides för .NET gratis från [här](https://releases.aspose.com/).
## Slutsats
den här handledningen utforskade vi de spännande möjligheterna med Aspose.Slides för .NET för att utföra dokumentkoppling i presentationer. Genom att följa steg-för-steg-guiden kan du enkelt skapa dynamiska och personliga presentationer. Förbättra din .NET-utvecklingsupplevelse med Aspose.Slides för sömlös presentationsgenerering.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}