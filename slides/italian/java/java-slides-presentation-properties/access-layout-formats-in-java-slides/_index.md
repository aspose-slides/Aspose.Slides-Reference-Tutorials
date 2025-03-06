---
title: Accedi ai formati di layout nelle diapositive Java
linktitle: Accedi ai formati di layout nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come accedere e manipolare i formati di layout in Diapositive Java con Aspose.Slides per Java. Personalizza facilmente gli stili di forme e linee nelle presentazioni PowerPoint.
weight: 10
url: /it/java/presentation-properties/access-layout-formats-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione ai formati di layout di accesso nelle diapositive Java

In questo tutorial, esploreremo come accedere e lavorare con i formati di layout in Java Slides utilizzando l'API Aspose.Slides per Java. I formati di layout ti consentono di controllare l'aspetto di forme e linee all'interno delle diapositive di layout di una presentazione. Tratteremo come recuperare i formati di riempimento e i formati di linea per le forme sulle diapositive di layout.

## Prerequisiti

1. Aspose.Slides per la libreria Java.
2. Una presentazione PowerPoint (formato PPTX) con diapositive di layout.

## Passaggio 1: caricare la presentazione

 Per prima cosa dobbiamo caricare la presentazione PowerPoint che contiene le diapositive di layout. Sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Passaggio 2: accedi ai formati di layout

Ora scorriamo le diapositive di layout nella presentazione e accediamo ai formati di riempimento e ai formati di linea delle forme su ciascuna diapositiva di layout.

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
        
        // Accedi ai formati di linea delle forme
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

- Iteriamo attraverso ogni diapositiva di layout utilizzando a`for` ciclo continuo.
- Per ogni diapositiva di layout, creiamo array per memorizzare formati di riempimento e formati di linea per le forme su quella diapositiva.
-  Usiamo nidificato`for` loop per scorrere le forme sulla diapositiva di layout e recuperare i formati di riempimento e linea.

## Passaggio 3: lavorare con i formati di layout

Ora che abbiamo avuto accesso ai formati di riempimento e ai formati di linea per le forme sulle diapositive di layout, puoi eseguire varie operazioni su di esse secondo necessità. Ad esempio, puoi modificare il colore di riempimento, lo stile della linea o altre proprietà delle forme.

## Codice sorgente completo per i formati di layout di accesso nelle diapositive Java

```java
// Il percorso della directory dei documenti.
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

### Come posso cambiare il colore di riempimento di una forma?

 Per modificare il colore di riempimento di una forma, puoi utilizzare`IFillFormat`metodi dell'oggetto. Ecco un esempio:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Imposta il tipo di riempimento su colore solido
fillFormat.getSolidFillColor().setColor(Color.RED); // Imposta il colore di riempimento su rosso
```

### Come posso modificare lo stile della linea di una forma?

 Per modificare lo stile della linea di una forma, puoi utilizzare il comando`ILineFormat`metodi dell'oggetto. Ecco un esempio:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Imposta lo stile della linea su singolo
lineFormat.setWidth(2.0); // Imposta la larghezza della linea su 2,0 punti
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Imposta il colore della linea su blu
```

### Come posso applicare queste modifiche a una forma su una diapositiva di layout?

Per applicare queste modifiche a una forma specifica su una diapositiva di layout, puoi accedere alla forma utilizzando il relativo indice nella raccolta di forme della diapositiva di layout. Per esempio:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Accedi alla prima forma nella diapositiva del layout
```

 È quindi possibile utilizzare il`IFillFormat` E`ILineFormat` metodi come mostrato nelle risposte precedenti per modificare i formati di riempimento e linea della forma.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
