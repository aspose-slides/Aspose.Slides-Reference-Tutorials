---
date: '2026-02-09'
description: Scopri come disegnare cornici attorno al testo e aggiungere testo alle
  celle delle tabelle in PowerPoint usando Aspose.Slides per Java. Questo tutorial
  copre la creazione di tabelle, l'impostazione dell'allineamento del testo e il salvataggio
  della presentazione in formato pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Come disegnare cornici e aggiungere testo a una tabella con Aspose.Slides per
  Java
url: /it/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come disegnare cornici e aggiungere testo a una tabella nelle presentazioni con Aspose.Slides per Java

## Introduzione

Presentare i dati in modo chiaro in PowerPoint può essere una vera sfida, soprattutto quando è necessario **add text to table** alle celle e evidenziare valori importanti con indicatori visivi. In questa guida imparerai **how to draw frames** attorno a paragrafi specifici, impostare l'allineamento del testo all'interno delle forme e infine **save presentation as pptx** — tutto usando Aspose.Slides per Java. Alla fine avrai una presentazione curata che attira l'attenzione del pubblico esattamente dove desideri.

Pronto a far risaltare le tue diapositive? Procediamo passo passo attraverso il processo.

## Risposte rapide
- **What does “add text to table” mean?** Significa inserire o aggiornare il contenuto testuale delle singole celle della tabella in modo programmatico.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – questo passaggio **save presentation as pptx** finalizza le modifiche.  
- **How can I align text inside a shape?** Usa `TextAlignment.Left` (o Center/Right) tramite `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Sì – itera sui paragrafi, ottieni il loro rettangolo di delimitazione e aggiungi un `IAutoShape` senza riempimento e con una linea nera.  
- **Do I need a license?** Una licenza temporanea è sufficiente per la valutazione; è necessaria una licenza completa per l'uso in produzione.  

## Perché disegnare cornici attorno al testo?

Disegnare una cornice (o rettangolo) attorno a un paragrafo o a una porzione specifica (ad esempio, qualsiasi testo contenente il carattere **'0'**) attira immediatamente l'attenzione. Questa tecnica è ideale per:

- Mettere in evidenza le principali cifre finanziarie in una tabella.  
- Enfatizzare avvisi o note importanti in una diapositiva.  
- Creare separatori visivi senza aggiungere forme extra manualmente.

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

Per iniziare a usare Aspose.Slides, segui questi passaggi:

1. **Install the Library**: Usa Maven o Gradle per gestire le dipendenze, oppure scaricalo direttamente da [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Inizia con una prova gratuita scaricando una licenza temporanea da [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Per accesso completo, considera l'acquisto di una licenza su [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Inizializza l'ambiente della tua presentazione con il seguente frammento di codice:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Come aggiungere testo a una tabella in Aspose.Slides per Java

### Funzionalità 1: Creare una tabella e aggiungere testo alle celle

#### Panoramica
Questa funzionalità dimostra come **create table**, quindi **add text to table** alle celle e successivamente **save presentation as pptx**.

#### Passaggi

**1. Create a Table**  
Prima, inizializza la tua presentazione e aggiungi una tabella nella posizione (50, 50) con le larghezze di colonna e le altezze di riga specificate.
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

### Funzionalità 2: Aggiungere TextFrame a AutoShape e impostare l'allineamento

#### Panoramica
Impara come aggiungere un text frame con allineamento specifico a un auto shape — un esempio di **set text alignment java**.

#### Passaggi

**1. Add an AutoShape**  
Aggiungi un rettangolo come AutoShape nella posizione (400, 100) con le dimensioni specificate.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

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

### Funzionalità 3: Disegnare cornici attorno a paragrafi e porzioni nelle celle della tabella

#### Panoramica
Questa funzionalità si concentra su **draw frames around text** e anche su **draw rectangle around paragraph** per le porzioni contenenti il carattere ‘0’.

#### Passaggi

**1. Create a Table**  
Riutilizza il codice da “Create Table and Add Text to Cells” per la configurazione iniziale.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Riutilizza il codice di creazione dei paragrafi dalla funzionalità precedente.
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
- **Performance** – Quando lavori con tabelle molto grandi, considera di raggruppare le aggiunte di forme o riutilizzare una singola istanza `IAutoShape` con geometria aggiornata per ridurre l'overhead di memoria.

## Domande frequenti

**Q: Can I use these APIs with older JDK versions?**  
A: La libreria supporta JDK 8 e versioni successive, ma il classificatore `jdk16` offre le migliori prestazioni sui runtime più recenti.

**Q: How do I change the frame color?**  
A: Modifica il colore di riempimento del formato linea, ad esempio `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Sì — usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e poi salva l'array di byte.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Itera attraverso `cell.getTextFrame().getParagraphs()`, individua la porzione contenente “Total” e disegna un rettangolo attorno al bounding box di quella porzione.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: L'API trasmette i dati in streaming e rilascia le risorse quando viene chiamato `pres.dispose()`, il che aiuta nella gestione della memoria per file di grandi dimensioni.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}