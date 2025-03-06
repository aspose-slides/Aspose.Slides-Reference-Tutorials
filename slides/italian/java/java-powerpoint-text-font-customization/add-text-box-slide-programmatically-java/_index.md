---
title: Aggiungi casella di testo sulla diapositiva a livello di codice con Java
linktitle: Aggiungi casella di testo sulla diapositiva a livello di codice con Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere a livello di codice una casella di testo alle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Migliora la tua produttività con questa guida passo passo.
weight: 24
url: /it/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi casella di testo sulla diapositiva a livello di codice con Java

## introduzione
La creazione e la manipolazione di presentazioni PowerPoint a livello di programmazione può semplificare molti flussi di lavoro, dalla generazione di report all'automazione delle presentazioni. Aspose.Slides per Java fornisce una potente API che consente agli sviluppatori di eseguire queste attività in modo efficiente. In questo tutorial, ti guideremo attraverso l'aggiunta di una casella di testo a una diapositiva utilizzando Aspose.Slides per Java. Alla fine di questo tutorial avrai una chiara comprensione di come integrare questa funzionalità nelle tue applicazioni Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Kit di sviluppo Java (JDK) installato
- IDE (ambiente di sviluppo integrato) come IntelliJ IDEA o Eclipse
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/)
- Conoscenza base della programmazione Java
## Importa pacchetti
Innanzitutto, importa i pacchetti necessari da Aspose.Slides e le librerie core Java per iniziare la codifica.
```java
import com.aspose.slides.*;
import java.io.File;
```
## Passaggio 1: imposta il tuo progetto
Crea un nuovo progetto Java nel tuo IDE e aggiungi la libreria Aspose.Slides per Java al percorso di compilazione del tuo progetto. Se non l'hai ancora scaricato, scaricalo da[Qui](https://releases.aspose.com/slides/java/).
## Passaggio 2: inizializzare l'oggetto di presentazione
 Inizializzare a`Presentation` oggetto, che rappresenta il file PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva e aggiungi la forma automatica
Ottieni la prima diapositiva dalla presentazione e aggiungi una forma automatica (rettangolo).
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Passaggio 4: aggiungi una cornice di testo alla forma automatica
Aggiungere una cornice di testo alla forma per contenere testo.
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## Passaggio 5: imposta il contenuto del testo
Imposta il contenuto del testo all'interno della cornice di testo.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## Passaggio 6: salva la presentazione
Salva la presentazione modificata in un file.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo esplorato come aggiungere a livello di codice una casella di testo a una diapositiva utilizzando Aspose.Slides per Java. Questa funzionalità consente agli sviluppatori di automatizzare la creazione e la personalizzazione delle presentazioni PowerPoint, migliorando la produttività e l'efficienza in varie applicazioni.
## Domande frequenti
### Aspose.Slides per Java può gestire altre forme oltre ai rettangoli?
Sì, Aspose.Slides supporta varie forme come cerchi, linee e altro.
### Aspose.Slides per Java è adatto per applicazioni aziendali su larga scala?
Assolutamente sì, è progettato per gestire compiti complessi in modo efficiente.
### Dove posso trovare altri esempi e documentazione per Aspose.Slides?
 Visitare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/) per guide ed esempi completi.
### Come posso ottenere licenze temporanee per i test?
 Puoi ottenere a[licenza temporanea](https://purchase.aspose.com/temporary-license/) da Aspose.
### Aspose.Slides supporta la conversione di presentazioni in altri formati?
Sì, supporta vari formati tra cui PDF e immagini.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
