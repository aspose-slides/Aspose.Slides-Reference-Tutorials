---
title: Imposta la lingua di presentazione e la forma del testo in Java
linktitle: Imposta la lingua di presentazione e la forma del testo in Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come automatizzare le presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Crea, modifica e migliora le diapositive a livello di programmazione con facilità.
weight: 19
url: /it/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
La creazione e la manipolazione di presentazioni PowerPoint a livello di programmazione in Java può semplificare l'automazione del flusso di lavoro e migliorare la produttività. Aspose.Slides per Java fornisce un robusto set di strumenti per svolgere queste attività in modo efficiente. Questo tutorial ti guida attraverso i passaggi essenziali per impostare il linguaggio di presentazione e modellare il testo utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
- Kit di sviluppo Java (JDK) installato
-  Aspose.Slides per la libreria Java, da cui è possibile scaricare[Qui](https://releases.aspose.com/slides/java/)
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse configurato sul tuo sistema
- Conoscenza base del linguaggio di programmazione Java
## Importa pacchetti
Per iniziare, importa i pacchetti Aspose.Slides necessari nel tuo file Java:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Passaggio 1: crea un oggetto di presentazione
 Inizia inizializzando a`Presentation` oggetto:
```java
Presentation pres = new Presentation();
```
Questo crea una nuova presentazione di PowerPoint.
## Passaggio 2: aggiungere e configurare una forma automatica
Successivamente, aggiungi una forma alla prima diapositiva e configura le sue proprietà:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Qui aggiungiamo una forma rettangolare alle coordinate (50, 50) con dimensioni 200x50 pixel.
## Passaggio 3: imposta testo e lingua
Imposta il contenuto del testo e specifica la lingua per il controllo ortografico:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 Sostituire`"Text to apply spellcheck language"` con il testo desiderato. L'ID della lingua`"en-EN"`specifica l'inglese (Stati Uniti).
## Passaggio 4: salva la presentazione
Salva la presentazione modificata in una directory di output specificata:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 Assicurarsi di sostituire`"Your Output Directory"` con il percorso effettivo della directory in cui desideri salvare il file.
## Passaggio 5: smaltimento delle risorse
 Smaltire correttamente il`Presentation` oggetto di rilasciare risorse:
```java
pres.dispose();
```
Questo passaggio è fondamentale per evitare perdite di memoria.

## Conclusione
In conclusione, Aspose.Slides per Java semplifica il processo di creazione e manipolazione delle presentazioni PowerPoint a livello di codice. Seguendo questi passaggi, puoi impostare in modo efficiente la lingua di presentazione e configurare le proprietà del testo in base alle tue esigenze.
## Domande frequenti
### Posso utilizzare Aspose.Slides per Java per creare presentazioni PowerPoint da zero?
Sì, Aspose.Slides fornisce API complete per creare presentazioni interamente a livello di programmazione.
### Come posso applicare caratteri diversi al testo nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java?
 È possibile impostare le proprietà del carattere tramite`IPortionFormat` oggetti associati a porzioni di testo.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 È disponibile la documentazione dettagliata[Qui](https://reference.aspose.com/slides/java/).
### Quali opzioni di supporto sono disponibili per Aspose.Slides per Java?
 È possibile visitare il forum Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
