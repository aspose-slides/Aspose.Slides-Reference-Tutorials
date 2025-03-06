---
title: Personalizzazione avanzata dei grafici in Aspose.Slides
linktitle: Personalizzazione avanzata dei grafici in Aspose.Slides
second_title: API di elaborazione di PowerPoint .NET Aspose.Slides
description: Scopri la personalizzazione avanzata dei grafici in Aspose.Slides per .NET. Crea grafici visivamente accattivanti con una guida passo passo.
weight: 10
url: /it/net/advanced-chart-customization/advanced-chart-customization/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


La creazione di grafici visivamente accattivanti e informativi è una parte essenziale della presentazione dei dati in molte applicazioni. Aspose.Slides per .NET fornisce strumenti robusti per la personalizzazione dei grafici, consentendoti di ottimizzare ogni aspetto dei tuoi grafici. In questo tutorial esploreremo le tecniche avanzate di personalizzazione dei grafici utilizzando Aspose.Slides per .NET.

## Prerequisiti

Prima di immergerti nella personalizzazione avanzata dei grafici con Aspose.Slides per .NET, assicurati di disporre dei seguenti prerequisiti:

1. Libreria Aspose.Slides per .NET: è necessario che la libreria Aspose.Slides sia installata e configurata correttamente nel progetto .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/net/).

2. Un ambiente di sviluppo .NET: dovresti avere un ambiente di sviluppo .NET configurato, incluso Visual Studio o qualsiasi altro IDE di tua scelta.

3. Conoscenza di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile, poiché scriveremo codice C# per lavorare con Aspose.Slides.

Ora suddividiamo la personalizzazione avanzata del grafico in più passaggi per guidarti attraverso il processo.

## Passaggio 1: crea una presentazione

Innanzitutto, crea una nuova presentazione utilizzando Aspose.Slides.

```csharp
// Il percorso della directory dei documenti.
string dataDir = "Your Document Directory";

// Crea directory se non è già presente.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Presentazione istanziativa
Presentation pres = new Presentation();
```

In questo passaggio, avviamo una nuova presentazione che manterrà il nostro grafico.

## Passaggio 2: accedi alla prima diapositiva

Successivamente, accedi alla prima diapositiva della presentazione in cui desideri aggiungere il grafico.

```csharp
// Accesso alla prima diapositiva
ISlide slide = pres.Slides[0];
```

Questo snippet di codice ti consente di lavorare con la prima diapositiva della presentazione.

## Passaggio 3: aggiunta di un grafico di esempio

Ora aggiungiamo un grafico di esempio alla diapositiva. In questo esempio creeremo un grafico a linee con indicatori.

```csharp
// Aggiunta del grafico di esempio
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Qui specifichiamo il tipo di grafico (LineWithMarkers) e la sua posizione e dimensioni sulla diapositiva.

## Passaggio 4: impostazione del titolo del grafico

Impostiamo un titolo per il grafico per fornire il contesto.

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

Ora personalizziamo le principali linee della griglia per l'asse dei valori.

```csharp
// Impostazione del formato delle linee principali della griglia per l'asse dei valori
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Questo passaggio configura l'aspetto delle principali linee della griglia sull'asse dei valori.

## Passaggio 6: personalizzare le linee della griglia minori

Allo stesso modo, possiamo personalizzare le linee minori della griglia per l'asse dei valori.

```csharp
// Impostazione del formato delle linee della griglia secondarie per l'asse dei valori
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Questo codice regola l'aspetto delle linee della griglia minori sull'asse dei valori.

## Passaggio 7: definire il formato del numero dell'asse dei valori

Personalizza il formato numerico per l'asse dei valori.

```csharp
// Impostazione del formato del numero dell'asse dei valori
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Questo passaggio consente di formattare i numeri visualizzati sull'asse dei valori.

## Passaggio 8: impostare i valori massimo e minimo del grafico

Definire i valori massimo e minimo per il grafico.

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

È inoltre possibile personalizzare le proprietà del testo dell'asse dei valori.

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

## Passaggio 10: aggiungi il titolo dell'asse valore

Se il tuo grafico richiede un titolo per l'asse dei valori, puoi aggiungerlo con questo passaggio.

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

In questo passaggio è possibile impostare un titolo per l'asse dei valori.

## Passaggio 11: personalizzare le linee principali della griglia per l'asse delle categorie

Ora concentriamoci sulle principali linee della griglia per l'asse delle categorie.

```csharp
// Impostazione del formato delle linee principali della griglia per l'asse delle categorie
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Questo codice configura l'aspetto delle principali linee della griglia sull'asse delle categorie.

## Passaggio 12: personalizzare le linee della griglia minori per l'asse delle categorie

Analogamente all'asse dei valori, puoi personalizzare le linee della griglia minori per l'asse delle categorie.

```csharp
// Impostazione del formato delle linee della griglia secondarie per l'asse delle categorie
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Qui puoi regolare l'aspetto delle linee della griglia minori sull'asse delle categorie.

## Passaggio 13: personalizzare le proprietà del testo dell'asse della categoria

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

Questo codice ti consente di regolare lo stile del carattere e l'aspetto delle etichette dell'asse delle categorie.

## Passaggio 14: aggiungere il titolo dell'asse della categoria

Se necessario, puoi anche aggiungere un titolo all'asse delle categorie.

```csharp
// Impostazione del titolo della categoria
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

Puoi esplorare ulteriori personalizzazioni, come legende, parete posteriore del grafico, pavimento e colori dell'area del tracciato. Queste personalizzazioni ti consentono di migliorare l'attrattiva visiva del tuo grafico.

```csharp
// Ulteriori personalizzazioni (opzionali)

// Impostazione delle proprietà del testo delle legende
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Imposta la visualizzazione delle legende del grafico senza sovrapposizione del grafico
chart.Legend.Overlay = true;

// Tracciare la prima serie sull'asse dei valori secondari (se necessario)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Impostazione del colore della parete posteriore del grafico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Impostazione del colore del piano del grafico
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Impostazione del colore dell'area del tracciato
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Salva la presentazione
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Queste personalizzazioni aggiuntive sono facoltative e possono essere applicate in base ai requisiti specifici di progettazione del grafico.

## Conclusione

In questa guida passo passo, abbiamo esplorato la personalizzazione avanzata dei grafici utilizzando Aspose.Slides per .NET. Hai imparato come creare una presentazione, aggiungere un grafico e perfezionarne l'aspetto, comprese le linee della griglia, le etichette degli assi e altri elementi visivi. Con le potenti opzioni di personalizzazione fornite da Aspose.Slides, puoi creare grafici che trasmettono efficacemente i tuoi dati e coinvolgono il tuo pubblico.

 Se hai domande o incontri sfide mentre lavori con Aspose.Slides per .NET, sentiti libero di esplorare la documentazione[Qui](https://reference.aspose.com/slides/net/) o chiedere assistenza in Aspose.Slides[Forum](https://forum.aspose.com/).

## Domande frequenti

### Quali versioni di .NET sono supportate da Aspose.Slides per .NET?
Aspose.Slides per .NET supporta varie versioni di .NET, inclusi .NET Framework e .NET Core. È possibile fare riferimento alla documentazione per l'elenco completo delle versioni supportate.

### Posso creare grafici da origini dati come file Excel utilizzando Aspose.Slides per .NET?
Sì, Aspose.Slides per .NET ti consente di creare grafici da origini dati esterne come fogli di calcolo Excel. È possibile esplorare la documentazione per esempi dettagliati.

### Come posso aggiungere etichette dati personalizzate alle mie serie di grafici?
 Per aggiungere etichette dati personalizzate alle serie di grafici, puoi accedere a`DataLabels` proprietà della serie e personalizzare le etichette secondo necessità. Fare riferimento alla documentazione per campioni ed esempi di codice.

### È possibile esportare il grafico in diversi formati di file, come PDF o formati immagine?
Sì, Aspose.Slides per .NET fornisce opzioni per esportare la tua presentazione con grafici in vari formati, inclusi PDF e formati immagine. Puoi utilizzare la libreria per salvare il tuo lavoro nel formato di output desiderato.

### Dove posso trovare altri tutorial ed esempi per Aspose.Slides per .NET?
 Puoi trovare numerosi tutorial, esempi di codice e documentazione su Aspose.Slides[sito web](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
