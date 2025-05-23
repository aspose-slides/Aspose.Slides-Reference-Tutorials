---
"description": "Scopri come impostare le modalità di layout per le diapositive Java utilizzando Aspose.Slides. Personalizza il posizionamento e le dimensioni dei grafici in questa guida dettagliata con codice sorgente."
"linktitle": "Imposta la modalità di layout in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta la modalità di layout in Java Slides"
"url": "/it/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la modalità di layout in Java Slides


## Introduzione alla modalità di impostazione del layout in Java Slides

In questo tutorial, impareremo come impostare la modalità di layout per un grafico in Java Slides utilizzando Aspose.Slides per Java. La modalità di layout determina il posizionamento e le dimensioni del grafico all'interno della diapositiva.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: creare una presentazione

Per prima cosa dobbiamo creare una nuova presentazione.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungere una diapositiva e un grafico

Successivamente, aggiungeremo una diapositiva e un grafico. In questo esempio, creeremo un grafico a colonne raggruppate.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Passaggio 3: imposta il layout del grafico

Ora, impostiamo il layout del grafico. Regoleremo la posizione e le dimensioni del grafico all'interno della diapositiva utilizzando `setX`, `setY`, `setWidth`, `setHeight` metodi. Inoltre, imposteremo il `LayoutTargetType` per determinare la modalità di layout.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In questo esempio, abbiamo impostato il grafico in modo che abbia il tipo di destinazione del layout su "Interno", il che significa che verrà posizionato e ridimensionato in relazione all'area interna della diapositiva.

## Passaggio 4: salva la presentazione

Infine, salviamo la presentazione con le impostazioni di layout del grafico.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per impostare la modalità di layout in Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato come impostare la modalità di layout per un grafico in Java Slides utilizzando Aspose.Slides per Java. È possibile personalizzare la posizione e le dimensioni del grafico in base alle proprie esigenze specifiche, modificando i valori in `setX`, `setY`, `setWidth`, `setHeight`, E `setLayoutTargetType` metodi. In questo modo puoi controllare il posizionamento dei grafici nelle diapositive.

## Domande frequenti

### Come posso modificare la modalità di layout di un grafico in Aspose.Slides per Java?

Per modificare la modalità di layout di un grafico in Aspose.Slides per Java, è possibile utilizzare `setLayoutTargetType` metodo nell'area del grafico. Puoi impostarlo su `LayoutTargetType.Inner` O `LayoutTargetType.Outer` seconda del layout desiderato.

### Posso personalizzare la posizione e le dimensioni del grafico all'interno della diapositiva?

Sì, puoi personalizzare la posizione e le dimensioni del grafico all'interno della diapositiva utilizzando `setX`, `setY`, `setWidth`, E `setHeight` metodi nell'area del grafico. Regola questi valori per posizionare e ridimensionare il grafico in base alle tue esigenze.

### Dove posso trovare maggiori informazioni su Aspose.Slides per Java?

Puoi trovare maggiori informazioni su Aspose.Slides per Java in [documentazione](https://reference.aspose.com/slides/java/)Include riferimenti API dettagliati ed esempi per aiutarti a lavorare efficacemente con diapositive e grafici in Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}