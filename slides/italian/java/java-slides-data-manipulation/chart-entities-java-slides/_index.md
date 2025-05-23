---
"description": "Impara a creare e personalizzare grafici Java Slides con Aspose.Slides. Migliora le tue presentazioni con potenti entità grafico."
"linktitle": "Entità del grafico in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Entità del grafico in Java Slides"
"url": "/it/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Entità del grafico in Java Slides


## Introduzione alle entità dei grafici in Java Slides

grafici sono strumenti potenti per visualizzare i dati nelle presentazioni. Che si tratti di creare report aziendali, presentazioni accademiche o qualsiasi altra forma di contenuto, i grafici aiutano a trasmettere le informazioni in modo efficace. Aspose.Slides per Java offre funzionalità avanzate per l'utilizzo dei grafici, rendendolo la scelta ideale per gli sviluppatori Java.

## Prerequisiti

Prima di immergerci nel mondo delle entità grafico, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato
- Libreria Aspose.Slides per Java scaricata e aggiunta al tuo progetto
- Conoscenza di base della programmazione Java

Ora iniziamo a creare e personalizzare i grafici utilizzando Aspose.Slides per Java.

## Fase 1: Creazione di una presentazione

Il primo passo è creare una nuova presentazione in cui aggiungere il grafico. Ecco un frammento di codice per creare una presentazione:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiunta di un grafico

Una volta pronta la presentazione, è il momento di aggiungere un grafico. In questo esempio, aggiungeremo un semplice grafico a linee con indicatori. Ecco come fare:

```java
// Accesso alla prima diapositiva
ISlide slide = pres.getSlides().get_Item(0);

// Aggiunta del grafico di esempio
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Passaggio 3: personalizzazione del titolo del grafico

Un grafico ben definito dovrebbe avere un titolo. Impostiamo un titolo per il nostro grafico:

```java
// Impostazione del titolo del grafico
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Passaggio 4: formattazione delle linee della griglia

Puoi formattare le linee principali e secondarie della griglia del tuo grafico. Impostiamo un po' di formattazione per le linee della griglia dell'asse verticale:

```java
// Impostazione del formato delle linee della griglia principale per l'asse dei valori
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Impostazione del formato delle linee della griglia secondaria per l'asse dei valori
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Passaggio 5: personalizzazione dell'asse dei valori

Puoi controllare il formato dei numeri, i valori massimi e minimi dell'asse dei valori. Ecco come personalizzarlo:

```java
// Impostazione del formato del numero dell'asse dei valori
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Impostazione dei valori massimi e minimi del grafico
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Passaggio 6: aggiunta del titolo dell'asse dei valori

Per rendere il grafico più informativo, puoi aggiungere un titolo all'asse dei valori:

```java
// Impostazione del titolo dell'asse dei valori
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Passaggio 7: formattazione dell'asse delle categorie

Anche l'asse delle categorie, che in genere rappresenta le categorie di dati, può essere personalizzato:

```java
// Impostazione del formato delle linee della griglia principale per l'asse delle categorie
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Impostazione del formato delle linee della griglia secondaria per l'asse della categoria
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Passaggio 8: aggiunta di legende

Le legende aiutano a spiegare le serie di dati nel grafico. Personalizziamole:

```java
// Impostazione delle proprietà del testo delle legende
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Imposta la visualizzazione delle legende del grafico senza sovrapposizione del grafico
chart.getLegend().setOverlay(true);
```

## Passaggio 9: salvataggio della presentazione

Infine, salva la presentazione con il grafico:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per le entità del grafico in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Creazione di un'istanza di presentazione // Creazione di un'istanza di presentazione
Presentation pres = new Presentation();
try
{
	// Accesso alla prima diapositiva
	ISlide slide = pres.getSlides().get_Item(0);
	// Aggiunta del grafico di esempio
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Titolo del grafico di impostazione
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Impostazione del formato delle linee della griglia principale per l'asse dei valori
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Impostazione del formato delle linee della griglia secondaria per l'asse dei valori
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Impostazione del formato del numero dell'asse dei valori
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Impostazione dei valori massimi e minimi del grafico
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Impostazione delle proprietà del testo dell'asse dei valori
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Impostazione del titolo dell'asse dei valori
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Impostazione del formato della linea dell'asse dei valori: ora obsoleto
	// grafico.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Impostazione del formato delle linee della griglia principale per l'asse delle categorie
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Impostazione del formato delle linee della griglia secondaria per l'asse della categoria
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Impostazione delle proprietà del testo dell'asse delle categorie
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Titolo della categoria di impostazione
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Impostazione della posizione dell'etichetta dell'asse della categoria
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Impostazione dell'angolo di rotazione dell'etichetta dell'asse della categoria
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Impostazione delle proprietà del testo delle legende
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Imposta la visualizzazione delle legende del grafico senza sovrapposizione del grafico
	chart.getLegend().setOverlay(true);
	// Tracciamento della prima serie sull'asse dei valori secondari
	// Grafico.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Impostazione del colore della parete posteriore del grafico
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Impostazione del colore dell'area del grafico
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Salva presentazione
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo articolo, abbiamo esplorato il mondo delle entità grafico in Java Slides utilizzando Aspose.Slides per Java. Hai imparato a creare, personalizzare e manipolare grafici per migliorare le tue presentazioni. I grafici non solo rendono i tuoi dati visivamente accattivanti, ma aiutano anche il tuo pubblico a comprendere più facilmente informazioni complesse.

## Domande frequenti

### Come faccio a cambiare il tipo di grafico?

Per cambiare il tipo di grafico, utilizzare `chart.setType()` metodo e specificare il tipo di grafico desiderato.

### Posso aggiungere più serie di dati a un grafico?

Sì, puoi aggiungere più serie di dati a un grafico utilizzando `chart.getChartData().getSeries().addSeries()` metodo.

### Come posso personalizzare i colori del grafico?

È possibile personalizzare i colori del grafico impostando il formato di riempimento per vari elementi del grafico, come linee della griglia, titolo e legende.

### Posso creare grafici 3D?

Sì, Aspose.Slides per Java supporta la creazione di grafici 3D. È possibile impostare `ChartType` a un tipo di grafico 3D per crearne uno.

### Aspose.Slides per Java è compatibile con le ultime versioni di Java?

Sì, Aspose.Slides per Java viene aggiornato regolarmente per supportare le ultime versioni di Java e garantisce compatibilità con un'ampia gamma di ambienti Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}