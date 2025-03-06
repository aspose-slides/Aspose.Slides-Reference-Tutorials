---
title: Aggiungi immagine all'interno delle celle della tabella in Java PowerPoint
linktitle: Aggiungi immagine all'interno delle celle della tabella in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere immagini all'interno delle celle della tabella nelle presentazioni Java PowerPoint con questa guida dettagliata passo passo utilizzando Aspose.Slides per Java.
weight: 10
url: /it/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi immagine all'interno delle celle della tabella in Java PowerPoint

## introduzione
Se stai cercando di migliorare le tue presentazioni Java PowerPoint incorporando immagini all'interno delle celle della tabella, sei arrivato nel posto giusto! Oggi approfondiremo una guida dettagliata passo passo utilizzando Aspose.Slides per Java. Questo tutorial ti guiderà attraverso l'intero processo, assicurando che anche un principiante possa seguirlo e ottenere risultati sorprendenti.
## Prerequisiti
Prima di iniziare, assicuriamoci di avere tutto ciò di cui hai bisogno:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer. Puoi scaricarlo da[Il sito di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides per Java: scarica la libreria Aspose.Slides da[sito web](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): consigliamo di utilizzare IntelliJ IDEA o Eclipse per lo sviluppo Java.
4. File immagine: tieni pronto un file immagine che desideri incorporare nelle celle della tabella PowerPoint.
Ora che hai tutti i prerequisiti, passiamo all'importazione dei pacchetti necessari e alla scrittura del codice.
## Importa pacchetti
Innanzitutto, importa i pacchetti richiesti nel tuo progetto Java. Questi pacchetti ti permetteranno di utilizzare le funzionalità fornite da Aspose.Slides e la gestione delle immagini di Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Suddividiamo l'esempio in più passaggi per renderlo più semplice da seguire.
## Passaggio 1: impostare la presentazione
Inizia impostando l'oggetto della presentazione e accedendo alla prima diapositiva.
```java
// Definisci il percorso della directory dei tuoi documenti
String dataDir = "Your Document Directory";
// Istanziare l'oggetto della classe Presentation
Presentation presentation = new Presentation();
```
Questo frammento di codice inizializza una nuova presentazione di PowerPoint e la prepara per ulteriori modifiche.
## Passaggio 2: accedi alla prima diapositiva
Successivamente, accedi alla prima diapositiva della presentazione. Questa diapositiva sarà la tela in cui aggiungeremo la tabella.
```java
try {
    // Accedi alla prima diapositiva
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 3: definire le dimensioni della tabella
Definire la larghezza delle colonne e l'altezza delle righe per la tabella. Questo passaggio è fondamentale per garantire che le celle della tabella abbiano le dimensioni corrette.
```java
    // Definisci colonne con larghezze e righe con altezze
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## Passaggio 4: aggiungi tabella alla diapositiva
Aggiungi la forma della tabella alla diapositiva utilizzando le dimensioni specificate.
```java
    // Aggiungi la forma della tabella alla diapositiva
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## Passaggio 5: caricare l'immagine
Carica l'immagine che desideri incorporare nella cella della tabella. Assicurati che il file immagine sia disponibile nella directory specificata.
```java
    // Crea un oggetto BufferedImage per contenere il file immagine
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // Crea un oggetto IPPImage utilizzando l'oggetto bitmap
    IPPImage imgx = presentation.getImages().addImage(image);
```
## Passaggio 6: aggiungi l'immagine alla cella della tabella
Ora è il momento di aggiungere l'immagine alla prima cella della tabella. Configura il formato di riempimento e imposta le proprietà dell'immagine.
```java
    // Aggiungi l'immagine alla prima cella della tabella
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## Passaggio 7: regola il ritaglio dell'immagine
Se necessario, regola il ritaglio dell'immagine per adattarla perfettamente alla cella. Questo passaggio garantisce che la tua immagine abbia l'aspetto giusto.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## Passaggio 8: salva la presentazione
Infine, salva la presentazione modificata nella directory desiderata.
```java
    // Salva il PPTX su disco
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Conclusione
Ecco qua! Seguendo questi passaggi, puoi aggiungere correttamente immagini all'interno delle celle della tabella in una presentazione Java PowerPoint utilizzando Aspose.Slides. Questa guida ha trattato tutto, dalla configurazione dell'ambiente al salvataggio della presentazione finale. Spero che questo tutorial ti aiuti a creare presentazioni visivamente più accattivanti.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare, modificare e gestire presentazioni PowerPoint nelle applicazioni Java.
### È disponibile una prova gratuita per Aspose.Slides?
 Sì, puoi ottenere un[prova gratuita](https://releases.aspose.com/) per provare Aspose.Slides prima dell'acquisto.
### Posso utilizzare qualsiasi formato di immagine con Aspose.Slides?
Aspose.Slides supporta vari formati di immagine tra cui JPEG, PNG, BMP e altri.
### Dove posso trovare documentazione più dettagliata?
 Puoi fare riferimento a[documentazione](https://reference.aspose.com/slides/java/) per informazioni più dettagliate ed esempi.
### Come posso acquistare Aspose.Slides per Java?
 Puoi acquistarlo da[Sito web Aspose](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
