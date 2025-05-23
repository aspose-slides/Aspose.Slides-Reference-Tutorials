---
"description": "Leer samenvoegen in presentaties met Aspose.Slides voor .NET in deze stapsgewijze handleiding. Maak moeiteloos dynamische, gepersonaliseerde presentaties."
"linktitle": "Samenvoegen in presentaties uitvoeren"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Samenvoegen in presentaties uitvoeren"
"url": "/nl/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Samenvoegen in presentaties uitvoeren

## Invoering
In de wereld van .NET-ontwikkeling is het creëren van dynamische en gepersonaliseerde presentaties een veelvoorkomende vereiste. Een krachtige tool die dit proces vereenvoudigt, is Aspose.Slides voor .NET. In deze tutorial duiken we in de fascinerende wereld van het samenvoegen van documenten in presentaties met Aspose.Slides voor .NET.
## Vereisten
Voordat we aan deze reis beginnen, zorg ervoor dat u aan de volgende voorwaarden voldoet:
- Aspose.Slides voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.Slides voor .NET-bibliotheek hebt geïnstalleerd. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/net/).
- Documentsjabloon: maak een presentatiesjabloon (bijvoorbeeld PresentationTemplate.pptx) die als basis voor de samenvoegbewerking dient.
- Gegevensbron: Je hebt een gegevensbron nodig voor samenvoeging. In ons voorbeeld gebruiken we XML-gegevens (TestData.xml), maar Aspose.Slides ondersteunt verschillende gegevensbronnen, zoals RDBMS.
Laten we nu eens kijken naar de stappen voor het uitvoeren van samenvoegingen in presentaties met behulp van Aspose.Slides voor .NET.
## Naamruimten importeren
Zorg er allereerst voor dat u de benodigde naamruimten importeert om optimaal gebruik te kunnen maken van de functionaliteiten die Aspose.Slides biedt:
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
## Stap 1: Stel uw documentenmap in
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Controleren of het resultaatpad bestaat
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Stap 2: Een dataset maken met XML-gegevens
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Stap 3: Loop door records en maak individuele presentaties
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // resultaat (individuele) presentatienaam maken
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Presentatiesjabloon laden
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Vul tekstvakken met gegevens uit de hoofdtabel
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Afbeelding uit de database halen
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Afbeelding invoegen in het fotokader van de presentatie
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Het tekstkader ophalen en voorbereiden om het met gegevens te vullen
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Personeelsgegevens invullen
        FillStaffList(textFrame, userRow, staffListTable);
        // Vul planfeitgegevens in
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Stap 4: Vul het tekstkader met gegevens als een lijst
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
## Stap 5: Vul het gegevensdiagram in vanuit de secundaire PlanFact-tabel
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
    // Voeg datapunten toe voor lijnreeksen
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
Deze stappen vormen een uitgebreide handleiding voor het samenvoegen van documenten in presentaties met Aspose.Slides voor .NET. Laten we nu enkele veelgestelde vragen beantwoorden.
## Veelgestelde vragen
### 1. Is Aspose.Slides voor .NET compatibel met verschillende gegevensbronnen?
Ja, Aspose.Slides voor .NET ondersteunt verschillende gegevensbronnen, waaronder XML, RDBMS en meer.
### 2. Kan ik het uiterlijk van opsommingstekens in de gegenereerde presentatie aanpassen?
Zeker! Je hebt volledige controle over de weergave van opsommingstekens, zoals aangetoond in de `FillStaffList` methode.
### 3. Welke soorten grafieken kan ik maken met Aspose.Slides voor .NET?
Aspose.Slides voor .NET ondersteunt een breed scala aan grafieken, waaronder lijndiagrammen zoals getoond in ons voorbeeld, staafdiagrammen, cirkeldiagrammen en meer.
### 4. Hoe kan ik ondersteuning of hulp krijgen met Aspose.Slides voor .NET?
Voor ondersteuning en hulp kunt u terecht op de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 5. Kan ik Aspose.Slides voor .NET uitproberen voordat ik het koop?
Zeker! U kunt een gratis proefversie van Aspose.Slides voor .NET gebruiken vanaf [hier](https://releases.aspose.com/).
## Conclusie
In deze tutorial hebben we de interessante mogelijkheden van Aspose.Slides voor .NET voor het samenvoegen van documenten in presentaties onderzocht. Door de stapsgewijze handleiding te volgen, kunt u moeiteloos dynamische en gepersonaliseerde presentaties maken. Verbeter uw .NET-ontwikkelervaring met Aspose.Slides voor het naadloos genereren van presentaties.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}