---
"description": "Scopri come automatizzare le presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Crea, modifica e migliora le diapositive programmandole con facilità."
"linktitle": "Imposta la lingua di presentazione e la forma del testo in Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Imposta la lingua di presentazione e la forma del testo in Java"
"url": "/it/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Imposta la lingua di presentazione e la forma del testo in Java

## Introduzione
Creare e manipolare presentazioni PowerPoint in Java tramite codice può semplificare l'automazione del flusso di lavoro e migliorare la produttività. Aspose.Slides per Java offre un solido set di strumenti per svolgere queste attività in modo efficiente. Questo tutorial illustra i passaggi essenziali per impostare il linguaggio di presentazione e dare forma al testo utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato
- Libreria Aspose.Slides per Java, che puoi scaricare da [Qui](https://releases.aspose.com/slides/java/)
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse installato sul tuo sistema
- Conoscenza di base del linguaggio di programmazione Java
## Importa pacchetti
Per iniziare, importa i pacchetti Aspose.Slides necessari nel tuo file Java:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Passaggio 1: creare un oggetto di presentazione
Iniziare inizializzando un `Presentation` oggetto:
```java
Presentation pres = new Presentation();
```
Verrà creata una nuova presentazione PowerPoint.
## Passaggio 2: aggiungere e configurare una forma automatica
Successivamente, aggiungi una forma alla prima diapositiva e configurane le proprietà:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Qui aggiungiamo un rettangolo AutoShape alle coordinate (50, 50) con dimensioni 200x50 pixel.
## Passaggio 3: imposta testo e lingua
Imposta il contenuto del testo e specifica la lingua per il controllo ortografico:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
Sostituire `"Text to apply spellcheck language"` con il testo desiderato. L'ID della lingua `"en-EN"` specifica inglese (Stati Uniti).
## Passaggio 4: salva la presentazione
Salva la presentazione modificata in una directory di output specificata:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
Assicurarsi di sostituire `"Your Output Directory"` con il percorso effettivo della directory in cui vuoi salvare il file.
## Fase 5: Smaltimento delle risorse
Smaltire correttamente il `Presentation` oggetto per rilasciare risorse:
```java
pres.dispose();
```
Questo passaggio è fondamentale per evitare perdite di memoria.

## Conclusione
In conclusione, Aspose.Slides per Java semplifica il processo di creazione e gestione delle presentazioni PowerPoint a livello di codice. Seguendo questi passaggi, è possibile impostare in modo efficiente il linguaggio di presentazione e configurare le proprietà del testo in base alle proprie esigenze.
## Domande frequenti
### Posso usare Aspose.Slides per Java per creare presentazioni PowerPoint da zero?
Sì, Aspose.Slides fornisce API complete per creare presentazioni in modo interamente programmatico.
### Come posso applicare diversi tipi di carattere al testo nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java?
È possibile impostare le proprietà del carattere tramite `IPortionFormat` oggetti associati a porzioni di testo.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi ottenere una prova gratuita da [Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
È disponibile la documentazione dettagliata [Qui](https://reference.aspose.com/slides/java/).
### Quali opzioni di supporto sono disponibili per Aspose.Slides per Java?
Puoi visitare il forum Aspose.Slides [Qui](https://forum.aspose.com/c/slides/11) per il sostegno della comunità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}