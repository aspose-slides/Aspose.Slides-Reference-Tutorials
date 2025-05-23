---
"description": "Scopri come creare grafici straordinari con Aspose.Slides per .NET. Migliora la tua visualizzazione dati con la nostra guida passo passo."
"linktitle": "Entità e formattazione del grafico"
"second_title": "API di elaborazione PowerPoint Aspose.Slides .NET"
"title": "Creazione di grafici accattivanti con Aspose.Slides per .NET"
"url": "/it/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Creazione di grafici accattivanti con Aspose.Slides per .NET


Nell'attuale mondo basato sui dati, una visualizzazione efficace dei dati è fondamentale per trasmettere informazioni al pubblico. Aspose.Slides per .NET è una potente libreria che consente di creare presentazioni e slide di grande impatto, inclusi grafici accattivanti. In questo tutorial, vi guideremo attraverso il processo di creazione di grafici di grande impatto utilizzando Aspose.Slides per .NET. Suddivideremo ogni esempio in più passaggi per aiutarvi a comprendere e implementare le entità e la formattazione dei grafici. Iniziamo!

## Prerequisiti

Prima di immergerci nella creazione di grafici accattivanti con Aspose.Slides per .NET, è necessario assicurarsi di disporre dei seguenti prerequisiti:

1. Aspose.Slides per .NET: assicurati di aver installato la libreria Aspose.Slides per .NET. Puoi scaricarla da [sito web](https://releases.aspose.com/slides/net/).

2. Ambiente di sviluppo: dovresti disporre di un ambiente di sviluppo funzionante con Visual Studio o qualsiasi altro IDE che supporti lo sviluppo .NET.

3. Conoscenza di base del linguaggio C#: per questo tutorial è essenziale avere familiarità con la programmazione C#.

Ora che abbiamo sistemato i prerequisiti, procediamo a creare splendidi grafici con Aspose.Slides per .NET.

## Importa spazi dei nomi

Per prima cosa, devi importare gli spazi dei nomi necessari per lavorare con Aspose.Slides per .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Passaggio 1: creare una presentazione

Iniziamo creando una nuova presentazione su cui lavorare. Questa presentazione servirà da base per il nostro grafico.

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

## Passaggio 2: accedi alla prima diapositiva

Andiamo alla prima diapositiva della presentazione, dove posizioneremo il nostro grafico.

```csharp
// Accesso alla prima diapositiva
ISlide slide = pres.Slides[0];
```

## Passaggio 3: aggiungere un grafico di esempio

Ora aggiungeremo un grafico di esempio alla nostra diapositiva. In questo esempio, creeremo un grafico a linee con indicatori.

```csharp
// Aggiunta del grafico di esempio
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Passaggio 4: imposta il titolo del grafico

Daremo un titolo al nostro grafico, rendendolo più informativo e visivamente accattivante.

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

## Passaggio 5: personalizzare le linee della griglia dell'asse verticale

In questo passaggio personalizzeremo le linee della griglia dell'asse verticale per rendere il nostro grafico visivamente più accattivante.

```csharp
// Impostazione del formato delle linee della griglia principale per l'asse dei valori
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Impostazione del formato delle linee della griglia secondaria per l'asse dei valori
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Impostazione del formato del numero dell'asse dei valori
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Passaggio 6: definire l'intervallo dell'asse verticale

In questo passaggio imposteremo i valori massimo, minimo e unitario per l'asse verticale.

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

## Passaggio 7: personalizzare il testo dell'asse verticale

Ora personalizzeremo l'aspetto del testo sull'asse verticale.

```csharp
// Impostazione delle proprietà del testo dell'asse dei valori
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

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

## Passaggio 8: personalizzare le linee della griglia dell'asse orizzontale

Adesso personalizziamo le linee della griglia per l'asse orizzontale.

```csharp
// Impostazione del formato delle linee della griglia principale per l'asse delle categorie
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Impostazione del formato delle linee della griglia secondaria per l'asse della categoria
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Impostazione delle proprietà del testo dell'asse delle categorie
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Passaggio 9: personalizzare le etichette dell'asse orizzontale

In questo passaggio regoleremo la posizione e la rotazione delle etichette dell'asse orizzontale.

```csharp
// Impostazione della posizione dell'etichetta dell'asse della categoria
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Impostazione dell'angolo di rotazione dell'etichetta dell'asse della categoria
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Passaggio 10: personalizza le legende

Miglioriamo le legende nel nostro grafico per migliorarne la leggibilità.

```csharp
// Impostazione delle proprietà del testo delle legende
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Imposta la visualizzazione delle legende del grafico senza sovrapposizione del grafico
chart.Legend.Overlay = true;
```

## Passaggio 11: personalizzare lo sfondo del grafico

Personalizzeremo i colori di sfondo del grafico, della parete di fondo e del pavimento.

```csharp
// Impostazione del colore della parete posteriore del grafico
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Impostazione del colore dell'area del grafico
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Passaggio 12: Salva la presentazione

Infine, salviamo la nostra presentazione con il grafico formattato.

```csharp
// Salva presentazione
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Conclusione

Creare grafici accattivanti e informativi nelle tue presentazioni è ora più facile che mai con Aspose.Slides per .NET. In questo tutorial, abbiamo illustrato i passaggi essenziali per personalizzare vari aspetti di un grafico, rendendolo visivamente accattivante e informativo. Con queste tecniche, puoi creare grafici straordinari che trasmettono efficacemente i tuoi dati al tuo pubblico.

Inizia a sperimentare con Aspose.Slides per .NET e porta la visualizzazione dei tuoi dati a un livello superiore!

## Domande frequenti

### 1. Che cos'è Aspose.Slides per .NET?

Aspose.Slides per .NET è una potente libreria che consente agli sviluppatori .NET di creare, manipolare e convertire presentazioni di Microsoft PowerPoint. Offre un'ampia gamma di funzionalità per lavorare con diapositive, forme, grafici e altro ancora.

### 2. Dove posso scaricare Aspose.Slides per .NET?

Puoi scaricare Aspose.Slides per .NET dal sito web [Qui](https://releases.aspose.com/slides/net/).

### 3. È disponibile una versione di prova gratuita di Aspose.Slides per .NET?

Sì, puoi ottenere una prova gratuita di Aspose.Slides per .NET da [Qui](https://releases.aspose.com/).

### 4. Come posso ottenere una licenza temporanea per Aspose.Slides per .NET?

Se hai bisogno di una licenza temporanea, puoi ottenerne una da [questo collegamento](https://purchase.aspose.com/temporary-license/).

### 5. Esiste una community o un forum di supporto per Aspose.Slides per .NET?

Sì, puoi trovare la community e il forum di supporto di Aspose.Slides [Qui](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}