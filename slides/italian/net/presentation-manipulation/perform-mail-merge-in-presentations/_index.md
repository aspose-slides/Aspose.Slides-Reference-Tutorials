---
"description": "Impara a usare la stampa unione nelle presentazioni usando Aspose.Slides per .NET in questa guida passo passo. Crea presentazioni dinamiche e personalizzate senza sforzo."
"linktitle": "Eseguire la stampa unione nelle presentazioni"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Eseguire la stampa unione nelle presentazioni"
"url": "/it/net/presentation-manipulation/perform-mail-merge-in-presentations/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Eseguire la stampa unione nelle presentazioni

## Introduzione
Nel mondo dello sviluppo .NET, creare presentazioni dinamiche e personalizzate è un'esigenza comune. Uno strumento potente che semplifica questo processo è Aspose.Slides per .NET. In questo tutorial, approfondiremo l'affascinante mondo dell'esecuzione della stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET.
## Prerequisiti
Prima di intraprendere questo viaggio, assicurati di avere i seguenti prerequisiti:
- Libreria Aspose.Slides per .NET: assicurarsi di aver installato la libreria Aspose.Slides per .NET. È possibile scaricarla da [Qui](https://releases.aspose.com/slides/net/).
- Modello di documento: preparare un modello di presentazione (ad esempio PresentationTemplate.pptx) che servirà da base per la stampa unione.
- Origine dati: è necessaria un'origine dati per la stampa unione. Nel nostro esempio, utilizzeremo dati XML (TestData.xml), ma Aspose.Slides supporta diverse origini dati, come RDBMS.
Ora analizziamo i passaggi per eseguire la stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET.
## Importa spazi dei nomi
Innanzitutto, assicurati di importare gli spazi dei nomi necessari per sfruttare le funzionalità fornite da Aspose.Slides:
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
## Passaggio 1: imposta la directory dei documenti
```csharp
string dataDir = "Your Document Directory";
string presTemplatePath = Path.Combine(dataDir, "PresentationTemplate.pptx");
string resultPath = Path.Combine(RunExamples.OutPath, "MailMergeResult");
// Controlla se esiste il percorso del risultato
if (!Directory.Exists(resultPath))
    Directory.CreateDirectory(resultPath);
```
## Passaggio 2: creare un set di dati utilizzando dati XML
```csharp
using (DataSet dataSet = new DataSet())
{
    dataSet.ReadXml(dataPath);
    DataTableCollection dataTables = dataSet.Tables;
    DataTable usersTable = dataTables["TestTable"];
    DataTable staffListTable = dataTables["StaffList"];
    DataTable planFactTable = dataTables["Plan_Fact"];
```
## Passaggio 3: scorrere i record e creare presentazioni individuali
```csharp
foreach (DataRow userRow in usersTable.Rows)
{
    // crea risultato (individuale) nome presentazione
    string presPath = Path.Combine(resultPath, "PresFor_" + userRow["Name"] + ".pptx");
    // Carica modello di presentazione
    using (Presentation pres = new Presentation(presTemplatePath))
    {
        // Riempi le caselle di testo con i dati della tabella principale
        ((AutoShape)pres.Slides[0].Shapes[0]).TextFrame.Text = "Chief of the department - " + userRow["Name"];
        ((AutoShape)pres.Slides[0].Shapes[4]).TextFrame.Text = userRow["Department"].ToString();
        // Ottieni l'immagine dal database
        byte[] bytes = Convert.FromBase64String(userRow["Img"].ToString());
        // Inserisci l'immagine nella cornice della presentazione
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
        // Compila i dati del personale
        FillStaffList(textFrame, userRow, staffListTable);
        // Compila i dati del piano
        FillPlanFact(pres, userRow, planFactTable);
        pres.Save(presPath, SaveFormat.Pptx);
    }
}
```
## Passaggio 4: Riempi la cornice di testo con i dati come un elenco
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
## Passaggio 5: compilare il grafico dei dati dalla tabella PlanFact secondaria
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
    // Aggiungere punti dati per serie di linee
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
Questi passaggi rappresentano una guida completa all'esecuzione della stampa unione nelle presentazioni utilizzando Aspose.Slides per .NET. Ora, rispondiamo ad alcune domande frequenti.
## Domande frequenti
### 1. Aspose.Slides per .NET è compatibile con diverse origini dati?
Sì, Aspose.Slides per .NET supporta varie origini dati, tra cui XML, RDBMS e altro ancora.
### 2. Posso personalizzare l'aspetto degli elenchi puntati nella presentazione generata?
Certamente! Hai il pieno controllo sull'aspetto degli elenchi puntati, come dimostrato nel `FillStaffList` metodo.
### 3. Quali tipi di grafici posso creare utilizzando Aspose.Slides per .NET?
Aspose.Slides per .NET supporta un'ampia gamma di grafici, tra cui grafici a linee come mostrato nel nostro esempio, grafici a barre, grafici a torta e altro ancora.
### 4. Come posso ottenere supporto o cercare assistenza con Aspose.Slides per .NET?
Per supporto e assistenza, puoi visitare il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Posso provare Aspose.Slides per .NET prima di acquistarlo?
Certamente! Puoi usufruire di una prova gratuita di Aspose.Slides per .NET da [Qui](https://releases.aspose.com/).
## Conclusione
In questo tutorial abbiamo esplorato le entusiasmanti funzionalità di Aspose.Slides per .NET nell'esecuzione della stampa unione nelle presentazioni. Seguendo la guida passo passo, puoi creare presentazioni dinamiche e personalizzate senza sforzo. Migliora la tua esperienza di sviluppo .NET con Aspose.Slides per una generazione di presentazioni impeccabile.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}