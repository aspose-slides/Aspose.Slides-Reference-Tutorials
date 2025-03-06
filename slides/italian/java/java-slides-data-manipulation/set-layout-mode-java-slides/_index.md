---
title: Imposta la modalità layout in Diapositive Java
linktitle: Imposta la modalità layout in Diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare le modalità di layout per le diapositive Java utilizzando Aspose.Slides. Personalizza il posizionamento e il dimensionamento del grafico in questa guida passo passo con il codice sorgente.
weight: 23
url: /it/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione alla modalità Imposta layout nelle diapositive Java

In questo tutorial impareremo come impostare la modalità di layout per un grafico nelle diapositive Java utilizzando Aspose.Slides per Java. La modalità layout determina il posizionamento e il dimensionamento del grafico all'interno della diapositiva.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: crea una presentazione

Per prima cosa dobbiamo creare una nuova presentazione.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Passaggio 2: aggiungi una diapositiva e un grafico

Successivamente, aggiungeremo una diapositiva e un grafico. In questo esempio creeremo un istogramma a colonne raggruppate.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Passaggio 3: imposta il layout del grafico

 Ora impostiamo il layout del grafico. Regoleremo la posizione e la dimensione del grafico all'interno della diapositiva utilizzando il file`setX`, `setY`, `setWidth`, `setHeight` metodi. Inoltre, imposteremo il file`LayoutTargetType` per determinare la modalità di layout.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

In questo esempio, abbiamo impostato il grafico in modo che il tipo di destinazione del layout sia "Interno", il che significa che sarà posizionato e dimensionato rispetto all'area interna della diapositiva.

## Passaggio 4: salva la presentazione

Infine, salviamo la presentazione con le impostazioni del layout del grafico.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Codice sorgente completo per la modalità Imposta layout nelle diapositive Java

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

 In questo tutorial, abbiamo imparato come impostare la modalità di layout per un grafico nelle diapositive Java utilizzando Aspose.Slides per Java. Puoi personalizzare la posizione e le dimensioni del grafico in base ai tuoi requisiti specifici regolando i valori nel file`setX`, `setY`, `setWidth`, `setHeight` , E`setLayoutTargetType`metodi. Ciò ti dà il controllo sul posizionamento dei grafici all'interno delle tue diapositive.

## Domande frequenti

### Come posso modificare la modalità di layout per un grafico in Aspose.Slides per Java?

 Per modificare la modalità di layout per un grafico in Aspose.Slides per Java, è possibile utilizzare il file`setLayoutTargetType` metodo nell'area del tracciato del grafico. Puoi impostarlo su entrambi`LayoutTargetType.Inner` O`LayoutTargetType.Outer` a seconda del layout desiderato.

### Posso personalizzare la posizione e la dimensione del grafico all'interno della diapositiva?

 Sì, puoi personalizzare la posizione e le dimensioni del grafico all'interno della diapositiva utilizzando il file`setX`, `setY`, `setWidth` , E`setHeight` metodi nell'area del tracciato del grafico. Modifica questi valori per posizionare e dimensionare il grafico in base alle tue esigenze.

### Dove posso trovare ulteriori informazioni su Aspose.Slides per Java?

 Puoi trovare ulteriori informazioni su Aspose.Slides per Java nel[documentazione](https://reference.aspose.com/slides/java/). Include riferimenti API dettagliati ed esempi per aiutarti a lavorare in modo efficace con diapositive e grafici in Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
