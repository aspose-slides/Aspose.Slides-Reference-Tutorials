---
"description": "Scopri la personalizzazione avanzata dei grafici in Aspose.Slides per .NET. Crea grafici visivamente accattivanti con istruzioni dettagliate."
"linktitle": "Personalizzazione avanzata dei grafici in Aspose.Slides"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Personalizzazione avanzata dei grafici in Aspose.Slides"
"url": "/it/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Personalizzazione avanzata dei grafici in Aspose.Slides


Creare grafici visivamente accattivanti e informativi è essenziale per la presentazione dei dati in molte applicazioni. Aspose.Slides per .NET offre strumenti robusti per la personalizzazione dei grafici, consentendo di perfezionarne ogni aspetto. In questo tutorial, esploreremo tecniche avanzate di personalizzazione dei grafici utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di immergerti nella personalizzazione avanzata dei grafici con Aspose.Slides per .NET, assicurati di disporre dei seguenti prerequisiti:

1. Libreria Aspose.Slides per .NET: è necessario che la libreria Aspose.Slides sia installata e correttamente configurata nel progetto .NET. È possibile scaricarla da [Qui](https://releases.aspose.com/slides/net/).

2. Un ambiente di sviluppo .NET: dovresti avere configurato un ambiente di sviluppo .NET, che includa Visual Studio o qualsiasi altro IDE di tua scelta.

3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile, poiché scriveremo codice C# da utilizzare con Aspose.Slides.

Ora, scomponiamo la personalizzazione avanzata dei grafici in più passaggi per guidarti nel processo.

## Passaggio 1: creare una presentazione

Per prima cosa, crea una nuova presentazione utilizzando Aspose.Slides.

```csharp
// Percorso verso la directory dei documenti.
string dataDir = "Your Document Directory";

// Creare la directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Presentazione di istanziazione
Presentation pres = new Presentation();
```

In questa fase, avviamo una nuova presentazione che conterrà il nostro grafico.

## Passaggio 2: accedi alla prima diapositiva

Successivamente, accedi alla prima diapositiva della presentazione in cui desideri aggiungere il grafico.

```csharp
// Accesso alla prima diapositiva
ISlide slide = pres.Slides[0];
```

Questo frammento di codice consente di lavorare con la prima diapositiva della presentazione.

## Passaggio 3: aggiunta di un grafico di esempio

Ora aggiungiamo un grafico di esempio alla diapositiva. In questo esempio, creeremo un grafico a linee con indicatori.

```csharp
// Aggiunta del grafico di esempio
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Qui specifichiamo il tipo di grafico (LineWithMarkers), la sua posizione e le sue dimensioni sulla diapositiva.

## Passaggio 4: impostazione del titolo del grafico

Impostiamo un titolo per il grafico per fornire contesto.

```csharp
// Impostazione del titolo del grafico
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

Questo codice imposta un titolo per il grafico, specificandone il testo, l'aspetto e lo stile del carattere.

## Passaggio 5: personalizzare le linee principali della griglia

Adesso personalizziamo le linee principali della griglia per l'asse dei valori.

```csharp
// Impostazione del formato delle linee della griglia principale per l'asse dei valori
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Questo passaggio configura l'aspetto delle principali linee della griglia sull'asse dei valori.

## Passaggio 6: personalizzare le linee della griglia secondaria

Allo stesso modo, possiamo personalizzare le linee della griglia secondaria per l'asse dei valori.

```csharp
// Impostazione del formato delle linee della griglia secondaria per l'asse dei valori
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Questo codice regola l'aspetto delle linee della griglia secondaria sull'asse dei valori.

## Passaggio 7: definire il formato numerico dell'asse dei valori

Personalizza il formato numerico per l'asse dei valori.

```csharp
// Impostazione del formato del numero dell'asse dei valori
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Questo passaggio consente di formattare i numeri visualizzati sull'asse dei valori.

## Passaggio 8: impostare i valori massimo e minimo del grafico

Definisci i valori massimo e minimo per il grafico.

```csharp
// Impostazione dei valori massimi e minimi del grafico
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Qui puoi specificare l'intervallo di valori che l'asse del grafico deve visualizzare.

## Passaggio 9: personalizzare le proprietà del testo dell'asse dei valori

È anche possibile personalizzare le proprietà del testo dell'asse dei valori.

```csharp
// Impostazione delle proprietà del testo dell'asse dei valori
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Questo codice consente di modificare lo stile del carattere e l'aspetto delle etichette dell'asse dei valori.

## Passaggio 10: aggiungere il titolo dell'asse del valore

Se il grafico richiede un titolo per l'asse dei valori, è possibile aggiungerlo con questo passaggio.

```csharp
// Impostazione del titolo dell'asse dei valori
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

In questo passaggio puoi impostare un titolo per l'asse dei valori.

## Passaggio 11: personalizzare le linee principali della griglia per l'asse delle categorie

Concentriamoci ora sulle linee principali della griglia per l'asse delle categorie.

```csharp
// Impostazione del formato delle linee della griglia principale per l'asse delle categorie
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Questo codice configura l'aspetto delle principali linee della griglia sull'asse delle categorie.

## Passaggio 12: personalizzare le linee della griglia secondaria per l'asse delle categorie

Similmente all'asse dei valori, è possibile personalizzare le linee della griglia secondaria per l'asse delle categorie.

```csharp
// Impostazione del formato delle linee della griglia secondaria per l'asse della categoria
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Qui puoi regolare l'aspetto delle linee della griglia secondaria sull'asse delle categorie.

## Passaggio 13: personalizzare le proprietà del testo dell'asse delle categorie

Personalizza le proprietà del testo per le etichette dell'asse delle categorie.

```csharp
// Impostazione delle proprietà del testo dell'asse delle categorie
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Questo codice consente di modificare lo stile del carattere e l'aspetto delle etichette degli assi delle categorie.

## Passaggio 14: aggiungere il titolo dell'asse delle categorie

Se necessario, puoi anche aggiungere un titolo all'asse delle categorie.

```csharp
// Titolo della categoria di impostazione
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

In questo passaggio puoi impostare un titolo per l'asse delle categorie.

## Passaggio 15: personalizzazioni aggiuntive

Puoi esplorare ulteriori personalizzazioni, come legende, sfondo del grafico, base e colori dell'area del grafico. Queste personalizzazioni ti permettono di migliorare l'aspetto visivo del tuo grafico.

```csharp
// Personalizzazioni aggiuntive (facoltative)

// Impostazione delle proprietà del testo delle legende
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Imposta la visualizzazione delle legende del grafico senza sovrapposizione del grafico
chart.Legend.Overlay = true;

// Tracciamento della prima serie sull'asse dei valori secondari (se necessario)
// Grafico.ChartData.Series[0].PlotOnSecondAxis = true;

// Impostazione del colore della parete posteriore del grafico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Impostazione del colore del pavimento del grafico
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Impostazione del colore dell'area del grafico
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Salva la presentazione
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Queste personalizzazioni aggiuntive sono facoltative e possono essere applicate in base ai requisiti specifici di progettazione del grafico.

## Conclusione

In questa guida passo passo, abbiamo esplorato la personalizzazione avanzata dei grafici utilizzando Aspose.Slides per .NET. Hai imparato a creare una presentazione, aggiungere un grafico e perfezionarne l'aspetto, inclusi griglia, etichette degli assi e altri elementi visivi. Grazie alle potenti opzioni di personalizzazione offerte da Aspose.Slides, puoi creare grafici che trasmettono efficacemente i tuoi dati e coinvolgono il pubblico.

Se hai domande o riscontri difficoltà durante l'utilizzo di Aspose.Slides per .NET, non esitare a consultare la documentazione [Qui](https://reference.aspose.com/slides/net/) o chiedi assistenza in Aspose.Slides [foro](https://forum.aspose.com/).

## Domande frequenti

### Quali versioni di .NET sono supportate da Aspose.Slides per .NET?
Aspose.Slides per .NET supporta diverse versioni di .NET, tra cui .NET Framework e .NET Core. Per l'elenco completo delle versioni supportate, consultare la documentazione.

### Posso creare grafici da fonti dati come file Excel utilizzando Aspose.Slides per .NET?
Sì, Aspose.Slides per .NET consente di creare grafici da fonti dati esterne come fogli di calcolo Excel. Puoi consultare la documentazione per esempi dettagliati.

### Come posso aggiungere etichette dati personalizzate alla mia serie di grafici?
Per aggiungere etichette dati personalizzate alla serie di grafici, puoi accedere a `DataLabels` proprietà della serie e personalizzare le etichette secondo necessità. Consultare la documentazione per esempi di codice.

### È possibile esportare il grafico in diversi formati di file, come PDF o formati immagine?
Sì, Aspose.Slides per .NET offre opzioni per esportare la presentazione con grafici in vari formati, inclusi PDF e immagini. È possibile utilizzare la libreria per salvare il lavoro nel formato di output desiderato.

### Dove posso trovare altri tutorial ed esempi per Aspose.Slides per .NET?
Puoi trovare una vasta gamma di tutorial, esempi di codice e documentazione su Aspose.Slides [sito web](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}