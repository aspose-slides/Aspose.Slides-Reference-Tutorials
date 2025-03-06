---
title: Aggiungi collegamento ipertestuale alla casella di testo in PowerPoint utilizzando Java
linktitle: Aggiungi collegamento ipertestuale alla casella di testo in PowerPoint utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere collegamenti ipertestuali alle caselle di testo di PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con esempi per sviluppatori Java.
type: docs
weight: 23
url: /it/java/java-powerpoint-text-font-customization/add-hyperlink-text-box-powerpoint-java/
---
## introduzione
Nell'era digitale di oggi, creare presentazioni dinamiche che coinvolgano e informino è fondamentale per una comunicazione efficace. Gli sviluppatori Java che cercano di migliorare le loro applicazioni con funzionalità interattive spesso si rivolgono ad Aspose.Slides per Java, una potente libreria che consente la manipolazione delle presentazioni PowerPoint a livello di codice. Questo tutorial approfondisce una di queste funzionalità: l'aggiunta di collegamenti ipertestuali alle caselle di testo nelle presentazioni PowerPoint utilizzando Java. Al termine di questa guida avrai una chiara comprensione di come implementare facilmente questa funzionalità nelle tue applicazioni Java.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione Java.
- JDK (Java Development Kit) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java scaricata e configurata. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse installato.

## Importa pacchetti
Prima di immergerti nell'esempio, assicurati di importare i pacchetti necessari:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Passaggio 1: crea un oggetto di presentazione
Innanzitutto, crea un'istanza di un oggetto Presentation che rappresenta una presentazione di PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pptxPresentation = new Presentation();
```
## Passaggio 2: accedi e modifica la diapositiva
Ottieni la prima diapositiva della presentazione per manipolarla.
```java
ISlide slide = pptxPresentation.getSlides().get_Item(0);
```
## Passaggio 3: aggiungere una forma automatica (casella di testo)
Aggiungi una forma automatica di tipo Rettangolo alla diapositiva alle coordinate specificate.
```java
IShape pptxShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 150, 50);
```
## Passaggio 4: accedi alla cornice di testo
Trasmetti la forma a Forma automatica e accedi alla sua cornice di testo.
```java
IAutoShape pptxAutoShape = (IAutoShape) pptxShape;
pptxAutoShape.addTextFrame("");
ITextFrame textFrame = pptxAutoShape.getTextFrame();
```
## Passaggio 5: aggiungi testo alla cornice di testo
Aggiungi il contenuto di testo desiderato alla cornice di testo.
```java
textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0).setText("Aspose.Slides");
```
## Passaggio 6: imposta il collegamento ipertestuale per il testo
Imposta un collegamento ipertestuale per la porzione di testo aggiunta nel passaggio precedente.
```java
IPortion portion = textFrame.getParagraphs().get_Item(0).getPortions().get_Item(0);
IHyperlinkManager hyperlinkManager = portion.getPortionFormat().getHyperlinkManager();
hyperlinkManager.setExternalHyperlinkClick("http://www.aspose.com");
```
## Passaggio 7: salva la presentazione
Salva la presentazione modificata in una posizione specificata.
```java
pptxPresentation.save(dataDir + "hLinkPPTX_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Seguendo questi passaggi, hai imparato con successo come aggiungere collegamenti ipertestuali alle caselle di testo nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Questa funzionalità ti consente di creare contenuti dinamici e interattivi all'interno delle tue applicazioni Java, migliorando il coinvolgimento e l'interattività dell'utente.
## Domande frequenti
### Posso utilizzare Aspose.Slides per Java gratuitamente?
 Sì, puoi iniziare con una prova gratuita disponibile[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 È disponibile la documentazione dettagliata[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto se riscontro problemi?
 Puoi ottenere supporto dalla comunità Aspose[Qui](https://forum.aspose.com/c/slides/11).
### Posso acquistare una licenza temporanea per Aspose.Slides per Java?
 Sì, è possibile acquistare licenze temporanee[Qui](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides è compatibile con altre librerie Java?
Aspose.Slides si integra bene con varie librerie Java per una manipolazione completa di PowerPoint.