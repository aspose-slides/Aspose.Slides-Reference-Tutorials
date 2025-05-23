---
"description": "Scopri come regolare l'altezza dei caratteri nelle presentazioni di PowerPoint usando Java con Aspose.Slides. Migliora la formattazione del testo nelle tue diapositive senza sforzo."
"linktitle": "Impostare i valori dell'altezza del carattere locale in PowerPoint utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Impostare i valori dell'altezza del carattere locale in PowerPoint utilizzando Java"
"url": "/it/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostare i valori dell'altezza del carattere locale in PowerPoint utilizzando Java

## Introduzione
In questo tutorial imparerai come gestire le altezze dei caratteri a vari livelli nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Il controllo delle dimensioni dei caratteri è fondamentale per creare presentazioni visivamente accattivanti e strutturate. Illustreremo passo dopo passo come impostare le altezze dei caratteri per diversi elementi di testo.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo sistema
- Libreria Aspose.Slides per Java. Puoi scaricarla. [Qui](https://releases.aspose.com/slides/java/).
- Una conoscenza di base della programmazione Java e delle presentazioni PowerPoint
## Importa pacchetti
Assicurati di includere i pacchetti Aspose.Slides necessari nel tuo file Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: inizializzare un oggetto di presentazione
Per prima cosa, crea un nuovo oggetto di presentazione di PowerPoint:
```java
Presentation pres = new Presentation();
```
## Passaggio 2: aggiungere una forma e una cornice di testo
Aggiungere una forma automatica con una cornice di testo alla prima diapositiva:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Passaggio 3: creare porzioni di testo
Definisci porzioni di testo con diverse altezze del carattere:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Passaggio 4: imposta l'altezza dei caratteri
Imposta altezze dei caratteri a livelli diversi:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Passaggio 5: Salva la presentazione
Salva la presentazione modificata in un file:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Conclusione
Questo tutorial ha mostrato come regolare l'altezza dei caratteri nelle diapositive di PowerPoint a livello di codice utilizzando Aspose.Slides per Java. Modificando le dimensioni dei caratteri a diversi livelli (a livello di presentazione, paragrafo e porzione), è possibile ottenere un controllo preciso sulla formattazione del testo nelle presentazioni.
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per la manipolazione programmatica delle presentazioni di PowerPoint.
### Dove posso trovare la documentazione per Aspose.Slides per Java?
Puoi trovare la documentazione [Qui](https://reference.aspose.com/slides/java/).
### Posso provare Aspose.Slides per Java prima di acquistarlo?
Sì, puoi ottenere una prova gratuita [Qui](https://releases.aspose.com/).
### Come posso ottenere supporto per Aspose.Slides per Java?
Per supporto, visita il [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Dove posso acquistare una licenza per Aspose.Slides per Java?
Puoi acquistare una licenza [Qui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}