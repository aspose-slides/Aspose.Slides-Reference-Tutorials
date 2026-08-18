---
date: '2026-06-23'
description: Scopri come creare una tabella in PowerPoint, aggiungere testo alle celle
  della tabella, disegnare cornici attorno al testo e salvare la presentazione come
  pptx utilizzando Aspose.Slides per Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: Come creare una tabella in PowerPoint e disegnare cornici con Aspose.Slides
  per Java
url: /it/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare una tabella in PowerPoint e disegnare cornici con Aspose.Slides per Java

## Introduzione

Creare una **create table in PowerPoint** programmaticamente può farti risparmiare ore di formattazione manuale, soprattutto quando devi evidenziare numeri chiave o aggiungere note esplicative. In questo tutorial scoprirai come aggiungere testo alle celle della tabella, disegnare cornici attorno a paragrafi specifici, impostare un allineamento preciso del testo e infine **save presentation as pptx** – il tutto con la potente API Aspose.Slides per Java. Alla fine avrai una diapositiva dall'aspetto curato, facile da leggere e che attira immediatamente l'attenzione del pubblico sui dati più importanti.

## Risposte rapide
- **What does “add text to table” mean?** Significa inserire o aggiornare il contenuto testuale delle singole celle della tabella in modo programmatico.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – questo passaggio **save presentation as pptx** finalizza le modifiche.  
- **How can I align text inside a shape?** Usa `TextAlignment.Left` (o Center/Right) tramite `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Sì – itera sui paragrafi, ottieni il loro rettangolo di delimitazione e aggiungi un `IAutoShape` senza riempimento e con una linea nera.  
- **Do I need a license?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per l'uso in produzione.  

## Perché disegnare cornici attorno al testo?

Disegnare una cornice (o rettangolo) attorno a un paragrafo o a una porzione specifica—come qualsiasi testo contenente il carattere **'0'**—attira immediatamente l'attenzione del pubblico su quel contenuto. Fornisce un chiaro indizio visivo senza modificare il testo sottostante, rendendola ideale per evidenziare cifre chiave, avvisi o separare sezioni all'interno di una diapositiva.

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

### Librerie richieste
Avrai bisogno di Aspose.Slides per Java. Ecco come includerlo usando Maven o Gradle:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

### Configurazione dell'ambiente
Assicurati di avere installato un Java Development Kit (JDK), preferibilmente JDK 16 o successivo, poiché questo esempio utilizza il classificatore `jdk16`.

### Prerequisiti di conoscenza
- Comprensione di base della programmazione Java.  
- Familiarità con software di presentazione come PowerPoint.  
- Esperienza nell'uso di un Integrated Development Environment (IDE) come IntelliJ IDEA o Eclipse.

## Configurazione di Aspose.Slides per Java

`Presentation` è la classe core di Aspose.Slides che rappresenta un file PowerPoint in memoria e fornisce l'accesso a diapositive, forme e tabelle. Per iniziare a usare Aspose.Slides, segui questi passaggi:

1. **Install the Library**: Usa Maven o Gradle per gestire le dipendenze, oppure scaricalo direttamente da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Inizia con una prova gratuita scaricando una licenza temporanea da [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Per l'accesso completo, considera l'acquisto di una licenza su [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:  
   Inizializza il tuo ambiente di presentazione con il seguente frammento di codice:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Come aggiungere testo a una tabella in Aspose.Slides per Java?

Carica una nuova `Presentation`, crea una tabella alle coordinate desiderate, popola le celle con oggetti `TextFrame` e infine chiama `pres.save("output.pptx", SaveFormat.Pptx)`. Questa sequenza crea una **create table in PowerPoint**, inserisce testo personalizzato in ogni cella e scrive il risultato in un file PPTX in un unico flusso di lavoro efficiente.

### Funzione 1: Creare una tabella e aggiungere testo alle celle

#### Panoramica
Questa funzione dimostra come **create table**, poi **add text to table** alle celle e successivamente **save presentation as pptx**.

#### Passaggi

**1. Create a Table**  
Prima, inizializza la tua presentazione e aggiungi una tabella nella posizione (50, 50) con le larghezze delle colonne e le altezze delle righe specificate.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
Crea paragrafi con porzioni di testo e aggiungili a una cella specifica.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Funzione 2: Aggiungere TextFrame a AutoShape e impostare l'allineamento

#### Panoramica
Scopri come aggiungere un text frame con allineamento specifico a un auto shape—un esempio di **set text alignment java**.

#### Passaggi

Un AutoShape è una forma che può contenere testo e grafica.

**1. Add an AutoShape**  
Aggiungi un rettangolo come AutoShape nella posizione (400, 100) con le dimensioni specificate.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum definisce le opzioni di allineamento orizzontale per il testo all'interno di una forma.

**2. Set Text Alignment**  
Imposta il testo a “Text in shape” e allinealo a sinistra.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Funzione 3: Disegnare cornici attorno a paragrafi e porzioni nelle celle della tabella

#### Panoramica
Questa funzione si concentra su **draw frames around text** e persino **draw rectangle around paragraph** per le porzioni contenenti il carattere ‘0’.

#### Passaggi

`IAutoShape` rappresenta un oggetto forma che può essere disegnato su una diapositiva, come i rettangoli usati per le cornici.

**1. Create a Table**  
Riutilizza il codice da “Create Table and Add Text to Cells” per la configurazione iniziale.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
Riutilizza il codice di creazione dei paragrafi dalla funzione precedente.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Draw Frames**  
Itera sui paragrafi e sulle porzioni per disegnare cornici attorno a essi.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Problemi comuni e consigli

- **Null checks** – Avvolgi sempre l'uso di `Presentation` in un blocco try‑finally per garantire che `pres.dispose()` venga eseguito e liberi le risorse native.  
- **Bounding rectangle accuracy** – Il rettangolo restituito da `para.getRect()` riflette il layout corrente; se cambi la dimensione del carattere o i margini, ricalcola il rettangolo prima di disegnare la cornice.  
- **Performance** – Quando lavori con tabelle molto grandi, considera di raggruppare le aggiunte di forme o riutilizzare una singola istanza di `IAutoShape` con geometria aggiornata per ridurre l'overhead di memoria.  

## Domande frequenti

**Q: Can I use these APIs with older JDK versions?**  
A: La libreria supporta JDK 8 in poi, ma il classificatore `jdk16` offre le migliori prestazioni sui runtime più recenti.

**Q: How do I change the frame color?**  
A: Modifica il colore di riempimento del formato linea, ad esempio `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Sì—usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e poi salva l'array di byte.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Itera attraverso `cell.getTextFrame().getParagraphs()`, individua la porzione contenente “Total” e disegna un rettangolo attorno al riquadro di delimitazione di quella porzione.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: L'API trasmette i dati in streaming e rilascia le risorse quando viene chiamato `pres.dispose()`, il che aiuta nella gestione della memoria per file di grandi dimensioni.

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutorial correlati

- [Aspose.Slides per Java&#58; Gestione avanzata di tabelle PPTX e testo nelle presentazioni PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Come creare cornici di testo dinamiche in PowerPoint usando Aspose.Slides per Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aggiungere colonne in Text Frame usando Aspose.Slides per Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}