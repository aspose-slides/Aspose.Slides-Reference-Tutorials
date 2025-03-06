---
title: Imposta i valori di altezza del carattere locale in PowerPoint utilizzando Java
linktitle: Imposta i valori di altezza del carattere locale in PowerPoint utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come regolare l'altezza dei caratteri nelle presentazioni di PowerPoint utilizzando Java con Aspose.Slides. Migliora facilmente la formattazione del testo nelle tue diapositive.
type: docs
weight: 17
url: /it/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---
## introduzione
In questo tutorial imparerai come manipolare le altezze dei caratteri a vari livelli all'interno delle presentazioni PowerPoint utilizzando Aspose.Slides per Java. Il controllo delle dimensioni dei caratteri è fondamentale per creare presentazioni visivamente accattivanti e strutturate. Esamineremo esempi passo passo per illustrare come impostare l'altezza dei caratteri per diversi elementi di testo.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo sistema
-  Aspose.Slides per la libreria Java. Puoi scaricarlo[Qui](https://releases.aspose.com/slides/java/).
- Una conoscenza di base della programmazione Java e delle presentazioni PowerPoint
## Importa pacchetti
Assicurati di includere i pacchetti Aspose.Slides necessari nel tuo file Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: inizializzare un oggetto di presentazione
Innanzitutto, crea un nuovo oggetto di presentazione di PowerPoint:
```java
Presentation pres = new Presentation();
```
## Passaggio 2: aggiungi una forma e una cornice di testo
Aggiungi una forma automatica con una cornice di testo alla prima diapositiva:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Passaggio 3: crea porzioni di testo
Definisci porzioni di testo con diverse altezze di carattere:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Passaggio 4: imposta l'altezza dei caratteri
Imposta l'altezza dei caratteri a diversi livelli:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Passaggio 5: salva la presentazione
Salva la presentazione modificata in un file:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusione
Questo tutorial ha dimostrato come regolare l'altezza dei caratteri all'interno delle diapositive di PowerPoint a livello di codice utilizzando Aspose.Slides per Java. Manipolando le dimensioni dei caratteri a diversi livelli (a livello della presentazione, paragrafo e porzione), puoi ottenere un controllo preciso sulla formattazione del testo nelle presentazioni.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per manipolare le presentazioni di PowerPoint a livello di codice.
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/java/).
### Posso provare Aspose.Slides per Java prima dell'acquisto?
 Sì, puoi ottenere una prova gratuita[Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per Java?
 Per supporto, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Dove posso acquistare una licenza per Aspose.Slides per Java?
 È possibile acquistare una licenza[Qui](https://purchase.aspose.com/buy).