---
title: Applicare effetti bicromia sulle immagini in PowerPoint
linktitle: Applicare effetti bicromia sulle immagini in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come applicare gli effetti Due tonalità alle immagini in PowerPoint utilizzando Aspose.Slides per Java con la nostra guida passo passo. Migliora le tue presentazioni.
weight: 20
url: /it/java/java-powerpoint-animation-shape-manipulation/apply-duotone-effects-images-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Applicare effetti bicromia sulle immagini in PowerPoint

## introduzione
L'aggiunta di effetti visivi alle presentazioni PowerPoint può migliorarne significativamente l'attrattiva e l'efficacia. Uno di questi effetti avvincenti è l'effetto Due tonalità, che applica due colori contrastanti a un'immagine, conferendole un aspetto moderno e professionale. In questa guida completa, ti guideremo attraverso il processo di applicazione degli effetti Duotone alle immagini in PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere quanto segue:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer. Puoi scaricarlo da[Sito Web Oracle JDK](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides per Java Library: è possibile scaricare la libreria da[Pagina di download di Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): un IDE come IntelliJ IDEA o Eclipse per scrivere ed eseguire il codice Java.
4.  File immagine: un file immagine (ad es.`aspose-logo.jpg`) per applicare l'effetto Due tonalità.
## Importa pacchetti
Innanzitutto, dovrai importare i pacchetti necessari nel tuo programma Java. Ecco come farlo:
```java
import com.aspose.slides.*;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Paths;
```
## Passaggio 1: crea una nuova presentazione
Inizia creando un nuovo oggetto di presentazione. Questa sarà la tela in cui aggiungerai la tua immagine e applicherai l'effetto Due tonalità.
```java
Presentation presentation = new Presentation();
```
## Passaggio 2: leggere il file immagine
Successivamente, leggi il file immagine dalla tua directory. Questa immagine verrà aggiunta alla presentazione e ad essa verrà applicato l'effetto Due tonalità.
```java
try {
    byte[] imageBytes = Files.readAllBytes(Paths.get("Your Document Directory/aspose-logo.jpg"));
```
## Passaggio 3: aggiungi l'immagine alla presentazione
Aggiungi l'immagine alla raccolta di immagini della presentazione. Questo passaggio rende l'immagine disponibile per l'uso all'interno della presentazione.
```java
    IPPImage backgroundImage = presentation.getImages().addImage(imageBytes);
```
## Passaggio 4: imposta l'immagine come sfondo della diapositiva
Ora imposta l'immagine come sfondo per la prima diapositiva. Ciò comporta la configurazione del tipo di sfondo e del formato di riempimento.
```java
    presentation.getSlides().get_Item(0).getBackground().setType(BackgroundType.OwnBackground);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().setFillType(FillType.Picture);
    presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().setImage(backgroundImage);
```
## Passaggio 5: aggiungi l'effetto due tonalità
Aggiungi un effetto Due tonalità all'immagine di sfondo. Questo passaggio prevede la creazione di un oggetto Duotone e l'impostazione delle sue proprietà.
```java
    IDuotone duotone = presentation.getSlides().get_Item(0).getBackground().getFillFormat().getPictureFillFormat().getPicture().getImageTransform().addDuotoneEffect();
```
## Passaggio 6: impostare le proprietà due tonalità
Configura l'effetto Due tonalità impostando i colori. Qui utilizziamo i colori dello schema per l'effetto Due tonalità.
```java
    duotone.getColor1().setColorType(ColorType.Scheme);
    duotone.getColor1().setSchemeColor(SchemeColor.Accent1);
    duotone.getColor2().setColorType(ColorType.Scheme);
    duotone.getColor2().setSchemeColor(SchemeColor.Dark2);
```
## Passaggio 7: recuperare e visualizzare i valori effettivi di due tonalità
Per verificare l'effetto, recuperare i valori effettivi dell'effetto Duotone e stamparli sulla console.
```java
    IDuotoneEffectiveData duotoneEffective = duotone.getEffective();
    System.out.println("Duotone effective color1: " + duotoneEffective.getColor1());
    System.out.println("Duotone effective color2: " + duotoneEffective.getColor2());
} catch(IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusione
L'applicazione di un effetto Due tonalità alle immagini in PowerPoint può conferire alle tue presentazioni un aspetto elegante e professionale. Con Aspose.Slides per Java, questo processo è semplice e altamente personalizzabile. Segui i passaggi descritti in questo tutorial per aggiungere un effetto Due tonalità alle tue immagini e far risaltare le tue presentazioni.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di creare, modificare e manipolare le presentazioni di PowerPoint a livello di codice.
### Come installo Aspose.Slides per Java?
 È possibile scaricare Aspose.Slides per Java dal file[pagina di download](https://releases.aspose.com/slides/java/). Seguire le istruzioni di installazione fornite nella documentazione.
### Posso utilizzare Aspose.Slides per Java con qualsiasi IDE?
Sì, Aspose.Slides per Java è compatibile con tutti i principali IDE, inclusi IntelliJ IDEA, Eclipse e NetBeans.
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi ottenere una prova gratuita da[Pagina di prova gratuita di Aspose.Slides](https://releases.aspose.com/).
### Dove posso trovare altri esempi e documentazione per Aspose.Slides per Java?
 È possibile trovare documentazione completa ed esempi su[Pagina della documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
