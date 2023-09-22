---
title: Führen Sie den Serienbrief in Präsentationen durch
linktitle: Führen Sie den Serienbrief in Präsentationen durch
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie in dieser umfassenden Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Slides für .NET einen Seriendruck in Präsentationen durchführen. Erstellen Sie ganz einfach personalisierte und dynamische Präsentationen.
type: docs
weight: 21
url: /de/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

Im Bereich der Softwareentwicklung ist die Erstellung dynamischer und personalisierter Präsentationen eine häufige Anforderung. Unternehmen müssen häufig Präsentationen erstellen, die auf bestimmte Daten zugeschnitten sind, und hier kommt die Serienbrieffunktion ins Spiel. In diesem Tutorial führen wir Sie durch den Prozess der Durchführung von Serienbriefen in Präsentationen mit Aspose.Slides für .NET.

## Einführung

Beim Seriendruck handelt es sich um eine leistungsstarke Technik, mit der Sie Präsentationsvorlagen mit Daten aus verschiedenen Quellen wie Datenbanken oder XML-Dateien füllen können. In diesem Tutorial konzentrieren wir uns auf die Verwendung von Aspose.Slides für .NET, um Schritt für Schritt den Serienbrief in Präsentationen durchzuführen.

## Einrichten Ihrer Umgebung

Bevor wir uns mit dem E-Mail-Zusammenführungsprozess befassen, müssen Sie Ihre Entwicklungsumgebung einrichten. Stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Visual Studio oder eine andere C#-Entwicklungsumgebung.
-  Aspose.Slides für .NET-Bibliothek installiert. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).

## Die Datenquelle verstehen

Für den Serienbrief benötigen Sie eine Datenquelle. In diesem Tutorial verwenden wir eine XML-Datei als Datenquelle. Hier ist ein Beispiel dafür, wie Ihre Datenquelle aussehen könnte:

```xml
<!-- TestData.xml -->
<?xml version="1.0" encoding="UTF-8"?>
<MailMerge>
    <TestTable>
        <Id>1</Id>
        <Code>105</Code>
        <Name>Samuel Ellington</Name>
        <Department>Legal Department</Department> <Img></Img>
    </TestTable>
    <StaffList>
        <Id>18</Id>
        <UserId>1</UserId>
        <Name>Amelia Walker</Name>
    </StaffList>
    <Plan_Fact>
        <Id>1</Id>
        <UserId>1</UserId>
        <OnDate>2020/01</OnDate>
        <PlanData>2,0</PlanData>
        <FactData>2,8</FactData>
    </Plan_Fact>
</MailMerge>
```

## Erstellen der Präsentationsvorlage

Um den Seriendruck durchzuführen, benötigen Sie eine Präsentationsvorlage (PPTX-Datei), die das Layout Ihrer endgültigen Präsentationen definiert. Sie können diese Vorlage mit Microsoft PowerPoint oder einem anderen Tool Ihrer Wahl erstellen.

## E-Mail-Zusammenführungsprozess

Lassen Sie uns nun mit Aspose.Slides für .NET in den eigentlichen E-Mail-Zusammenführungsprozess eintauchen. Wir unterteilen es in Schritte:

1. Laden Sie die Präsentationsvorlage.
2. Füllen Sie Textfelder mit Daten aus der Datenquelle.
3. Fügen Sie Bilder in die Präsentation ein.
4. Textrahmen vorbereiten und füllen.
5. Speichern Sie die einzelnen Präsentationen.

Hier ist ein Ausschnitt aus C#-Code, der diese Schritte ausführt:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Pfad zu den Daten.
    // XML-Daten sind eines der Beispiele für mögliche MailMerge-Datenquellen (neben RDBMS und anderen Arten von Datenquellen).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Überprüfen Sie, ob ein Ergebnispfad vorhanden ist
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // DataSet mit XML-Daten erstellen
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Für alle Datensätze in der Haupttabelle erstellen wir eine separate Präsentation
        foreach (DataRow userRow in usersTable.Rows)
        {
            // Ergebnis erstellen (individueller) Präsentationsname
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Präsentationsvorlage laden
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Füllen Sie Textfelder mit Daten aus der Haupttabelle der Datenbank
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Bild aus der Datenbank abrufen
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // Bild in den Bilderrahmen der Präsentation einfügen
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Holen Sie sich einen Textrahmen und bereiten Sie ihn zum Füllen mit Daten vor
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
    }

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

// Füllt das Datendiagramm aus der sekundären planFact-Tabelle
static void FillPlanFact(Presentation pres, DataRow row, DataTable planFactTable)
{
    IChart chart = pres.Slides[0].Shapes[3] as Chart;
    IChartTitle chartTitle = chart.ChartTitle;
    chartTitle.TextFrameForOverriding.Text = row["Name"] + " : Plan / Fact";

    DataRow[] selRows = planFactTable.Select("UserId = " + row["Id"]);
    string range = chart.ChartData.GetRange();

    IChartDataWorkbook cellsFactory = chart.ChartData.ChartDataWorkbook;
    int worksheetIndex = 0;

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 1,
            double.Parse(selRows[0]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 1, 2,
            double.Parse(selRows[0]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 1,
            double.Parse(selRows[1]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 2, 2,
            double.Parse(selRows[1]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[2]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[2]["FactData"].ToString())));

    chart.ChartData.Series[0].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 1,
            double.Parse(selRows[3]["PlanData"].ToString())));
    chart.ChartData.Series[1].DataPoints.AddDataPointForLineSeries(
        cellsFactory.GetCell(worksheetIndex, 3, 2,
            double.Parse(selRows[3]["FactData"].ToString())));

    chart.ChartData.SetRange(range);
}		
```

## Speichern des Ergebnisses

Sobald Sie den Seriendruckvorgang für alle Datensätze in Ihrer Datenquelle abgeschlossen haben, stehen Ihnen individuelle Präsentationen zur Verfügung. Sie können sie an Ihrem gewünschten Ort speichern.

## Abschluss

Das Durchführen von Serienbriefen in Präsentationen mit Aspose.Slides für .NET eröffnet eine Welt voller Möglichkeiten für die Erstellung individueller und datengesteuerter Präsentationen. Dieses Tutorial hat Sie durch die wesentlichen Schritte geführt, um dies nahtlos zu erreichen.

## FAQs

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
A1: Während Aspose.Slides für .NET eine leistungsstarke Wahl ist, bieten auch andere Bibliotheken und Tools ähnliche Funktionen. Letztendlich kommt es auf Ihre spezifischen Anforderungen und Vorlieben an.

**Q2: Can I use different data sources apart from XML files?**
A2: Ja, Aspose.Slides für .NET unterstützt verschiedene Datenquellen, einschließlich Datenbanken und benutzerdefinierten Datenstrukturen.

**Q3: How can I format the merged presentations further?**
A3: Mit dem umfangreichen Funktionsumfang von Aspose.Slides können Sie zusätzliche Formatierungen, Stile und Animationen auf die zusammengeführten Präsentationen anwenden.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 A4: Ja, Sie können eine kostenlose Testversion von Aspose.Slides für .NET erhalten[Hier](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 A5: Für technischen Support und Diskussionen können Sie die besuchen[Aspose.Slides-Forum](https://forum.aspose.com/).

Nachdem Sie nun gelernt haben, wie Sie mit Aspose.Slides für .NET einen Serienbrief in Präsentationen durchführen, können Sie mit der Erstellung dynamischer und datenreicher Präsentationen für Ihre Projekte beginnen. Viel Spaß beim Codieren!
