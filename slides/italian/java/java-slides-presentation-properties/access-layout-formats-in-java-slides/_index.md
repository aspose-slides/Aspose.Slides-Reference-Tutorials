---
"description": "Scopri come accedere e manipolare i formati di layout in Java Slides con Aspose.Slides per Java. Personalizza facilmente gli stili di forme e linee nelle presentazioni di PowerPoint."
"linktitle": "Formati di layout di Access in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Formati di layout di Access in Java Slides"
"url": "/it/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formati di layout di Access in Java Slides


## Introduzione ai formati di layout di Access in Java Slides

In questo tutorial, esploreremo come accedere e utilizzare i formati di layout in Java Slides utilizzando l'API Aspose.Slides per Java. I formati di layout consentono di controllare l'aspetto di forme e linee all'interno delle diapositive di layout di una presentazione. Vedremo come recuperare i formati di riempimento e i formati di linea per le forme nelle diapositive di layout.

## Prerequisiti

1. Libreria Aspose.Slides per Java.
2. Una presentazione PowerPoint (formato PPTX) con diapositive di layout.

## Passaggio 1: caricare la presentazione

Per prima cosa, dobbiamo caricare la presentazione PowerPoint che contiene le diapositive del layout. Sostituisci `"Your Document Directory"` con il percorso effettivo verso la directory dei documenti.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Passaggio 2: accedere ai formati di layout

Ora scorriamo le diapositive del layout nella presentazione e accediamo ai formati di riempimento e ai formati di linea delle forme in ogni diapositiva del layout.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Accedi ai formati di riempimento delle forme
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Formati di linee di accesso delle forme
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

Nel codice sopra:

- Eseguiamo l'iterazione su ogni diapositiva di layout utilizzando un `for` ciclo continuo.
- Per ogni diapositiva di layout, creiamo matrici per memorizzare i formati di riempimento e i formati di linea per le forme su quella diapositiva.
- Usiamo annidato `for` cicli per scorrere le forme nella diapositiva di layout e recuperarne i formati di riempimento e linea.

## Passaggio 3: lavorare con i formati di layout

Ora che abbiamo accesso ai formati di riempimento e di linea per le forme nelle diapositive di layout, è possibile eseguire diverse operazioni su di esse a seconda delle esigenze. Ad esempio, è possibile modificare il colore di riempimento, lo stile della linea o altre proprietà delle forme.

## Codice sorgente completo per i formati di layout di Access in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo esplorato come accedere e manipolare i formati di layout in Java Slides utilizzando l'API Aspose.Slides per Java. I formati di layout sono essenziali per controllare l'aspetto di forme e linee all'interno delle diapositive di layout nelle presentazioni di PowerPoint.

## Domande frequenti

### Come faccio a cambiare il colore di riempimento di una forma?

Per cambiare il colore di riempimento di una forma, puoi usare `IFillFormat` metodi dell'oggetto. Ecco un esempio:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Imposta il tipo di riempimento su colore pieno
fillFormat.getSolidFillColor().setColor(Color.RED); // Imposta il colore di riempimento su rosso
```

### Come faccio a modificare lo stile della linea di una forma?

Per modificare lo stile della linea di una forma, puoi utilizzare `ILineFormat` metodi dell'oggetto. Ecco un esempio:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Imposta lo stile della linea su singolo
lineFormat.setWidth(2.0); // Imposta la larghezza della linea su 2,0 punti
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Imposta il colore della linea su blu
```

### Come applico queste modifiche a una forma in una diapositiva di layout?

Per applicare queste modifiche a una forma specifica in una diapositiva di layout, è possibile accedere alla forma utilizzando il suo indice nella raccolta forme della diapositiva di layout. Ad esempio:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Accedi alla prima forma nella diapositiva di layout
```

Puoi quindi utilizzare il `IFillFormat` E `ILineFormat` metodi come quelli mostrati nelle risposte precedenti per modificare i formati di riempimento e linea della forma.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}