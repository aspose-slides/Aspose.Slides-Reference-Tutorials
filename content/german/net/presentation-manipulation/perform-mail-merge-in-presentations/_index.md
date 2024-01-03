---
title: Führen Sie den Serienbrief in Präsentationen durch
linktitle: Führen Sie den Serienbrief in Präsentationen durch
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie in dieser Schritt-für-Schritt-Anleitung mehr über den Seriendruck in Präsentationen mit Aspose.Slides für .NET. Erstellen Sie mühelos dynamische, personalisierte Präsentationen.
type: docs
weight: 21
url: /de/net/presentation-manipulation/perform-mail-merge-in-presentations/
---
## Einführung
In der Welt der .NET-Entwicklung ist die Erstellung dynamischer und personalisierter Präsentationen eine häufige Anforderung. Ein leistungsstarkes Tool, das diesen Prozess vereinfacht, ist Aspose.Slides für .NET. In diesem Tutorial tauchen wir in den faszinierenden Bereich der Durchführung von Serienbriefen in Präsentationen mit Aspose.Slides für .NET ein.
## Voraussetzungen
Bevor wir uns auf diese Reise begeben, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
- Aspose.Slides for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Slides for .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net/).
- Dokumentvorlage: Bereiten Sie eine Präsentationsvorlage (z. B. PresentationTemplate.pptx) vor, die als Basis für den Seriendruck dient.
- Datenquelle: Sie benötigen eine Datenquelle für den Seriendruck. In unserem Beispiel verwenden wir XML-Daten (TestData.xml), aber Aspose.Slides unterstützt verschiedene Datenquellen wie RDBMS.
Lassen Sie uns nun in die Schritte zum Durchführen von Serienbriefen in Präsentationen mit Aspose.Slides für .NET eintauchen.
## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um die von Aspose.Slides bereitgestellten Funktionen nutzen zu können:
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
## Schritt 1: Richten Sie Ihr Dokumentenverzeichnis ein
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Überprüfen Sie, ob ein Ergebnispfad vorhanden ist
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Schritt 2: Erstellen Sie ein DataSet mit XML-Daten
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Schritt 3: Durchgehen Sie die Datensätze und erstellen Sie individuelle Präsentationen
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // Ergebnis erstellen (individueller) Präsentationsname
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Präsentationsvorlage laden
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Füllen Sie Textfelder mit Daten aus der Haupttabelle
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Holen Sie sich ein Bild aus der Datenbank
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        //Bild in den Bilderrahmen der Präsentation einfügen
        IPPImage image = pres.Images.AddImage(bytes);
        IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
        pf.PictureFormat.Picture.Image.ReplaceImage(image);
        // Holen Sie sich den Textrahmen und bereiten Sie ihn zum Füllen mit Daten vor
        IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
        ITextFrame textFrame = list.TextFrame;
        textFrame.Paragraphs.Clear();
        Paragraph para = new Paragraph();
        para.Text = "Department Staff:";
        textFrame.Paragraphs.Add(para);
        // Personaldaten ausfüllen
        FillStaffList(textFrame, userRow, staffListTable);
        // Füllen Sie die Faktendaten des Plans aus
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Schritt 4: Füllen Sie den Textrahmen mit Daten als Liste
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
## Schritt 5: Füllen Sie das Datendiagramm aus der sekundären PlanFact-Tabelle
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
    // Fügen Sie Datenpunkte für Linienreihen hinzu
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
Diese Schritte stellen eine umfassende Anleitung zum Durchführen von Serienbriefen in Präsentationen mit Aspose.Slides für .NET dar. Lassen Sie uns nun einige häufig gestellte Fragen beantworten.
## Häufig gestellte Fragen
### 1. Ist Aspose.Slides für .NET mit verschiedenen Datenquellen kompatibel?
Ja, Aspose.Slides für .NET unterstützt verschiedene Datenquellen, einschließlich XML, RDBMS und mehr.
### 2. Kann ich das Erscheinungsbild von Aufzählungspunkten in der generierten Präsentation anpassen?
 Sicherlich! Sie haben die volle Kontrolle über das Erscheinungsbild von Aufzählungspunkten, wie im gezeigt`FillStaffList` Methode.
### 3. Welche Arten von Diagrammen kann ich mit Aspose.Slides für .NET erstellen?
Aspose.Slides für .NET unterstützt eine Vielzahl von Diagrammen, darunter Liniendiagramme wie in unserem Beispiel gezeigt, Balkendiagramme, Kreisdiagramme und mehr.
### 4. Wie erhalte ich Unterstützung oder Hilfe bei Aspose.Slides für .NET?
 Für Unterstützung und Unterstützung können Sie die besuchen[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11).
### 5. Kann ich Aspose.Slides für .NET vor dem Kauf testen?
 Sicherlich! Sie können eine kostenlose Testversion von Aspose.Slides für .NET unter nutzen[Hier](https://releases.aspose.com/).
## Abschluss
In diesem Tutorial haben wir die spannenden Funktionen von Aspose.Slides für .NET bei der Durchführung von Serienbriefen in Präsentationen untersucht. Wenn Sie der Schritt-für-Schritt-Anleitung folgen, können Sie mühelos dynamische und personalisierte Präsentationen erstellen. Verbessern Sie Ihre .NET-Entwicklungserfahrung mit Aspose.Slides für eine nahtlose Präsentationserstellung.