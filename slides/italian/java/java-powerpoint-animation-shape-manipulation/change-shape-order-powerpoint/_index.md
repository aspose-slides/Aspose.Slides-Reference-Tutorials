---
title: Cambia l'ordine delle forme in PowerPoint
linktitle: Cambia l'ordine delle forme in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come modificare l'ordine delle forme in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial passo passo. Migliora le tue capacità di presentazione senza sforzo.
weight: 15
url: /it/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Creare presentazioni visivamente accattivanti e ben strutturate può essere un compito arduo. Tuttavia, con gli strumenti e le tecniche giuste, puoi renderlo molto più semplice. Aspose.Slides per Java è una potente libreria che ti aiuta a manipolare e gestire le presentazioni di PowerPoint a livello di codice. In questo tutorial, ti guideremo attraverso i passaggi per modificare l'ordine delle forme in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di disporre dei seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides per Java Library: scarica la versione più recente da[Aspose.Slides per la pagina di download di Java](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse per la codifica.
4. File di presentazione: tieni pronto un file PowerPoint che desideri manipolare.
## Importa pacchetti
Per iniziare, è necessario importare i pacchetti necessari dalla libreria Aspose.Slides. Queste importazioni ti consentiranno di lavorare con presentazioni, diapositive e forme.
```java
import com.aspose.slides.*;

```
In questa guida suddivideremo il processo di modifica dell'ordine delle forme in diversi passaggi per una migliore comprensione e facilità di implementazione.
## Passaggio 1: caricare la presentazione
 Innanzitutto, devi caricare il file di presentazione di PowerPoint con cui vuoi lavorare. Questo passaggio prevede l'inizializzazione del file`Presentation` class con il percorso del file PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## Passaggio 2: accedi alla diapositiva desiderata
Una volta caricata la presentazione, accedi alla diapositiva in cui desideri riordinare le forme. Le diapositive sono indicizzate a partire da 0, quindi per accedere alla prima diapositiva utilizzare l'indice 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## Passaggio 3: aggiungi forme alla diapositiva
Successivamente, aggiungi le forme alla diapositiva. A scopo dimostrativo, aggiungeremo alla diapositiva una forma rettangolare e triangolare.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Passaggio 4: riordina le forme
 Ora riordina le forme sulla diapositiva. IL`reorder` Il metodo consente di specificare la nuova posizione per la forma all'interno della raccolta di forme della diapositiva.
```java
slide.getShapes().reorder(2, shp3);
```
## Passaggio 5: salva la presentazione modificata
Dopo aver riordinato le forme, salva la presentazione modificata in un nuovo file. Ciò garantisce che il file originale rimanga invariato.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## Passaggio 6: ripulire le risorse
Infine, elimina l'oggetto di presentazione per liberare risorse.
```java
if (presentation1 != null) presentation1.dispose();
```
## Conclusione
Seguendo questi passaggi, puoi facilmente modificare l'ordine delle forme in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria semplifica molte attività associate alle presentazioni PowerPoint, consentendoti di creare e manipolare le diapositive a livello di codice. Che tu stia automatizzando la creazione di presentazioni o semplicemente desideri apportare modifiche in blocco, Aspose.Slides per Java è uno strumento inestimabile.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è un'API Java per creare e manipolare presentazioni PowerPoint senza utilizzare Microsoft PowerPoint.
### Posso utilizzare Aspose.Slides per Java con altri IDE Java?
Sì, puoi utilizzarlo con qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
### Aspose.Slides per Java è compatibile con tutti i formati PowerPoint?
Sì, Aspose.Slides per Java supporta PPT, PPTX e altri formati PowerPoint.
### Come posso ottenere una prova gratuita di Aspose.Slides per Java?
 È possibile scaricare una versione di prova gratuita da[Aspose.Slides per la pagina di download di Java](https://releases.aspose.com/).
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
 È possibile trovare documentazione dettagliata su[Aspose.Slides per la pagina della documentazione Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
