---
title: Utför koppling av brev i presentationer
linktitle: Utför koppling av brev i presentationer
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du utför sammanslagning i presentationer med Aspose.Slides för .NET i den här omfattande steg-för-steg-guiden. Skapa personliga och dynamiska presentationer med lätthet.
type: docs
weight: 21
url: /sv/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

Inom mjukvaruutveckling är det ett vanligt krav att skapa dynamiska och personliga presentationer. Företag behöver ofta skapa presentationer som är skräddarsydda för specifik data, och det är här funktionen för e-postsammankoppling kommer in i bilden. I den här handledningen kommer vi att guida dig genom processen att utföra e-postsammanfogning i presentationer med Aspose.Slides för .NET.

## Introduktion

Mail merge är en kraftfull teknik som låter dig fylla presentationsmallar med data från olika källor, som databaser eller XML-filer. I den här handledningen kommer vi att fokusera på att använda Aspose.Slides för .NET för att utföra e-postsammanfogning i presentationer steg för steg.

## Ställa in din miljö

Innan vi dyker in i e-postsammanfogningsprocessen måste du konfigurera din utvecklingsmiljö. Se till att du har följande förutsättningar:

- Visual Studio eller någon annan C#-utvecklingsmiljö.
-  Aspose.Slides för .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/slides/net/).

## Förstå datakällan

För e-postsammanfogning behöver du en datakälla. I den här handledningen kommer vi att använda en XML-fil som vår datakälla. Här är ett exempel på hur din datakälla kan se ut:

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

## Skapa presentationsmallen

För att utföra sammanslagning behöver du en presentationsmall (PPTX-fil) som definierar layouten för dina slutliga presentationer. Du kan skapa den här mallen med Microsoft PowerPoint eller något annat valfritt verktyg.

## E-postsammanfogningsprocess

Låt oss nu dyka in i själva e-postsammanfogningsprocessen med Aspose.Slides för .NET. Vi delar upp det i steg:

1. Ladda presentationsmallen.
2. Fyll textrutor med data från datakällan.
3. Infoga bilder i presentationen.
4. Förbered och fyll textramar.
5. Spara de enskilda presentationerna.

Här är ett utdrag av C#-kod som utför dessa steg:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Vägen till data.
    // XML-data är ett av exemplen på möjliga MailMerge-datakällor (bland RDBMS och andra typer av datakällor).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Kontrollera om resultatsökvägen finns
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // Skapa datauppsättning med XML-data
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // För alla poster i huvudtabellen kommer vi att skapa en separat presentation
        foreach (DataRow userRow in usersTable.Rows)
        {
            // skapa resultat (individuellt) presentationsnamn
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Ladda presentationsmall
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Fyll textrutor med data från databasens huvudtabell
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Hämta bild från databasen
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // infoga bilden i bildramen för presentationen
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Få en abd förbered textram för att fylla den med data
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // fylla i personaluppgifter
                FillStaffList(textFrame, userRow, staffListTable);

                // fyll i planfakta
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

// Fyller datadiagram från den sekundära planFact-tabellen
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

## Sparar resultatet

När du har slutfört sammankopplingsprocessen för alla poster i din datakälla har du individuella presentationer redo. Du kan spara dem på önskad plats.

## Slutsats

Att utföra sammanslagning i presentationer med Aspose.Slides för .NET öppnar upp en värld av möjligheter för att skapa skräddarsydda och datadrivna presentationer. Denna handledning har guidat dig genom de väsentliga stegen för att uppnå detta sömlöst.

## Vanliga frågor

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
S1: Även om Aspose.Slides för .NET är ett kraftfullt val, erbjuder andra bibliotek och verktyg liknande funktionalitet. Det beror i slutändan på dina specifika krav och preferenser.

**Q2: Can I use different data sources apart from XML files?**
S2: Ja, Aspose.Slides för .NET stöder olika datakällor, inklusive databaser och anpassade datastrukturer.

**Q3: How can I format the merged presentations further?**
S3: Du kan använda ytterligare formatering, stilar och animationer på de sammanslagna presentationerna med Aspose.Slides rika funktionsuppsättning.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 S4: Ja, du kan få en gratis provversion av Aspose.Slides för .NET[här](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 S5: För teknisk support och diskussioner kan du besöka[Aspose.Slides forum](https://forum.aspose.com/).

Nu när du har lärt dig hur du utför sammanslagning i presentationer med Aspose.Slides för .NET, kan du börja skapa dynamiska och datarika presentationer för dina projekt. Glad kodning!
