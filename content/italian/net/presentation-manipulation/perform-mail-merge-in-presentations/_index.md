---
title: Esegui la stampa unione nelle presentazioni
linktitle: Esegui la stampa unione nelle presentazioni
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri come eseguire la stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET in questa guida passo passo completa. Crea presentazioni personalizzate e dinamiche con facilità.
type: docs
weight: 21
url: /it/net/presentation-manipulation/perform-mail-merge-in-presentations/
---

Nel campo dello sviluppo software, la creazione di presentazioni dinamiche e personalizzate è un requisito comune. Le aziende spesso hanno bisogno di generare presentazioni su misura per dati specifici, ed è qui che entra in gioco la funzionalità di stampa unione. In questo tutorial, ti guideremo attraverso il processo di esecuzione della stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET.

## introduzione

La stampa unione è una tecnica potente che consente di popolare modelli di presentazione con dati provenienti da varie fonti, come database o file XML. In questo tutorial, ci concentreremo sull'utilizzo di Aspose.Slides per .NET per eseguire la stampa unione nelle presentazioni passo dopo passo.

## Configurazione dell'ambiente

Prima di immergerci nel processo di stampa unione, devi configurare il tuo ambiente di sviluppo. Assicurati di avere i seguenti prerequisiti:

- Visual Studio o qualsiasi altro ambiente di sviluppo C#.
-  Aspose.Slides per la libreria .NET installata. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/net/).

## Comprendere l'origine dati

Per la stampa unione avrai bisogno di un'origine dati. In questo tutorial utilizzeremo un file XML come origine dati. Ecco un esempio di come potrebbe apparire la tua origine dati:

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

## Creazione del modello di presentazione

Per eseguire la stampa unione, avrai bisogno di un modello di presentazione (file PPTX) che definisca il layout delle presentazioni finali. Puoi creare questo modello utilizzando Microsoft PowerPoint o qualsiasi altro strumento di tua scelta.

## Processo di fusione della posta

Ora, tuffiamoci nell'effettivo processo di fusione della posta utilizzando Aspose.Slides per .NET. Lo suddivideremo in passaggi:

1. Carica il modello di presentazione.
2. Compila le caselle di testo con i dati dell'origine dati.
3. Inserisci immagini nella presentazione.
4. Preparare e riempire cornici di testo.
5. Salva le singole presentazioni.

Ecco uno snippet di codice C# che esegue questi passaggi:

```csharp
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
    string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");

    // Percorso dei dati.
    // I dati XML sono uno degli esempi delle possibili origini dati MailMerge (tra RDBMS e altri tipi di origini dati).
    string dataPath = Path.Combine(dataDir, "TestData.xml");

    // Controlla se il percorso dei risultati esiste
    if (!Directory.Exists(resultPath))
        Directory.CreateDirectory(resultPath);

    // Creazione di un set di dati utilizzando dati XML
    using (DataSet dataSet = new DataSet())
    {
        dataSet.ReadXml(dataPath);

        DataTableCollection dataTables = dataSet.Tables;
        DataTable usersTable = dataTables["TestTable"];
        DataTable staffListTable = dataTables["StaffList"];
        DataTable planFactTable = dataTables["Plan_Fact"];

        // Per tutti i record nella tabella principale creeremo una presentazione separata
        foreach (DataRow userRow in usersTable.Rows)
        {
            // creare il nome della presentazione del risultato (individuale).
            string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");

            //Carica il modello di presentazione
            using (Presentation pres = new Presentation(presTemplatePath))
            {
                // Compila le caselle di testo con i dati dalla tabella principale del database
                ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text =
                    "Chief of the department - " + userRow["Name"];
                ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();

                // Ottieni l'immagine dal database
                byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());

                // inserire l'immagine nella cornice della presentazione
                IPPImage image = pres.Images.AddImage(bytes);
                IPictureFrame pf = pres.Slides[0].Shapes[1] as PictureFrame;
                pf.PictureFormat.Picture.Image.ReplaceImage(image);

                // Ottieni e prepara la cornice di testo per riempirla con i dati
                IAutoShape list = pres.Slides[0].Shapes[2] as IAutoShape;
                ITextFrame textFrame = list.TextFrame;

                textFrame.Paragraphs.Clear();
                Paragraph para = new Paragraph();
                para.Text = "Department Staff:";
                textFrame.Paragraphs.Add(para);

                // compilare i dati del personale
                FillStaffList(textFrame, userRow, staffListTable);

                // compilare i dati relativi ai fatti del piano
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

// Compila il grafico dei dati dalla tabella planFact secondaria
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

## Salvataggio del risultato

Una volta completato il processo di stampa unione per tutti i record nell'origine dati, avrai a disposizione le singole presentazioni. Puoi salvarli nella posizione desiderata.

## Conclusione

L'esecuzione della stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET apre un mondo di possibilità per la creazione di presentazioni personalizzate e basate sui dati. Questo tutorial ti ha guidato attraverso i passaggi essenziali per raggiungere questo obiettivo senza problemi.

## Domande frequenti

**Q1: Is Aspose.Slides for .NET the only library for mail merge in presentations?**
A1: Sebbene Aspose.Slides per .NET sia una scelta potente, anche altre librerie e strumenti offrono funzionalità simili. Alla fine dipende dalle tue esigenze e preferenze specifiche.

**Q2: Can I use different data sources apart from XML files?**
A2: Sì, Aspose.Slides per .NET supporta varie origini dati, inclusi database e strutture dati personalizzate.

**Q3: How can I format the merged presentations further?**
A3: puoi applicare formattazione, stili e animazioni aggiuntivi alle presentazioni unite utilizzando il ricco set di funzionalità di Aspose.Slides.

**Q4: Is there a trial version of Aspose.Slides for .NET available?**
 A4: Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET[Qui](https://releases.aspose.com/).

**Q5: Where can I get support for Aspose.Slides for .NET?**
 R5: Per supporto tecnico e discussioni, è possibile visitare il sito[Forum Aspose.Slides](https://forum.aspose.com/).

Ora che hai imparato come eseguire la stampa unione nelle presentazioni con Aspose.Slides per .NET, puoi iniziare a creare presentazioni dinamiche e ricche di dati per i tuoi progetti. Buona programmazione!
