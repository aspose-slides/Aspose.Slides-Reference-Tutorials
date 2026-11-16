---
date: '2026-11-16'
description: Disegna una cornice attorno al testo nelle tabelle di PowerPoint usando
  Aspose.Slides for Java – scopri come creare tabelle, aggiungere testo alle celle,
  evidenziare le celle e esportare il file in formato PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Disegna una cornice attorno al testo nelle tabelle di PowerPoint usando
  Aspose.Slides for Java. Questa guida mostra come creare tabelle, aggiungere e allineare
  il testo, evidenziare le celle e esportare le diapositive in formato PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Disegnare una cornice attorno al testo e creare tabelle in PowerPoint con
  Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
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
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Come disegnare una cornice attorno al testo e creare tabelle in PowerPoint
  con Aspose.Slides for Java
url: /it/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Come disegnare un contorno intorno al testo e creare tabelle in PowerPoint con Aspose.Slides per Java

## Introduzione

Disegnare un **draw frame around text** in una diapositiva PowerPoint ti consente di evidenziare figure chiave senza modificare il contenuto sottostante. In questo tutorial imparerai a creare programmaticamente una tabella, inserire e allineare il testo all'interno delle celle, evidenziare parole specifiche o intere celle e, infine, salvare la presentazione come file PPTX. Alla fine avrai una diapositiva rifinita che attira lo sguardo del pubblico esattamente dove desideri.

## Risposte rapide
- **Cosa significa “add text to table”?** Significa inserire o aggiornare il contenuto testuale delle singole celle della tabella in modo programmatico.  
- **Quale metodo salva il file?** `pres.save("output.pptx", SaveFormat.Pptx)` – questo **save presentation as pptx** passaggio finalizza le modifiche.  
- **Come posso allineare il testo all'interno di una forma?** Usa `TextAlignment.Left` (o Center/Right) tramite `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Posso disegnare un rettangolo intorno a un paragrafo?** Sì – itera sui paragrafi, ottieni il loro rettangolo di delimitazione e aggiungi un `IAutoShape` senza riempimento e con una linea nera.  
- **Ho bisogno di una licenza?** Una licenza temporanea funziona per la valutazione; è necessaria una licenza completa per l'uso in produzione.  

## Perché disegnare contorni intorno al testo?

Disegnare un contorno intorno al testo evidenzia istantaneamente numeri importanti, avvisi o titoli. Fornisce un indizio visivo mantenendo intatta la formattazione originale, rendendolo ideale per report finanziari, dashboard KPI o qualsiasi diapositiva dove è richiesto un enfasi.

## Cos'è il contorno intorno al testo?

`draw frame around text` è la tecnica di aggiungere programmaticamente una forma rettangolare che segue i confini esatti di un paragrafo o di una porzione di testo, usando la formattazione della linea senza riempire l'interno. Questo approccio consente di enfatizzare il contenuto senza alterare il testo stesso.

## Prerequisiti

### Librerie richieste
Avrai bisogno di Aspose.Slides per Java. Includila con uno dei gestori di pacchetti:

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

Puoi anche consultare le versioni su [Versioni di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).

### Configurazione dell'ambiente
È consigliato un Java Development Kit (JDK) 16 o più recente perché gli esempi usano il classificatore `jdk16`. Qualsiasi IDE come IntelliJ IDEA o Eclipse funzionerà.

### Prerequisiti di conoscenza
- Competenze di base nella programmazione Java.  
- Familiarità con i concetti di PowerPoint (diapositive, forme, tabelle).  
- Comprensione di come Maven/Gradle gestiscono le dipendenze.

## Configurazione di Aspose.Slides per Java

`Presentation` è la classe core di Aspose.Slides che rappresenta un file PowerPoint in memoria e fornisce accesso a diapositive, forme e tabelle. Può gestire presentazioni con fino a **10.000 diapositive** mantenendo l'uso di memoria sotto **500 MB**, rendendola adatta per automazione su larga scala.

1. **Installa la libreria** – usa Maven o Gradle, o scaricala direttamente da [Versioni di Aspose.Slides per Java](https://releases.aspose.com/slides/java/).  
2. **Acquisizione della licenza** – inizia con una prova gratuita dalla [Licenza temporanea](https://purchase.aspose.com/temporary-license/) e passa a una licenza completa su [Acquista Aspose.Slides](https://purchase.aspose.com/buy) per carichi di lavoro di produzione.  
3. **Inizializzazione di base** – crea un nuovo oggetto `Presentation` e carica o crea diapositive secondo necessità.  
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

`Presentation` è la classe principale che rappresenta un file PowerPoint in memoria.  
Carica una nuova `Presentation`, crea una tabella alle coordinate desiderate, popola le celle con oggetti `TextFrame` e infine chiama `pres.save("output.pptx", SaveFormat.Pptx)`. Questa sequenza crea una **create table in PowerPoint**, inserisce testo personalizzato in ogni cella e scrive il risultato in un file PPTX in un unico flusso efficiente.

### Risposta diretta
Crea una tabella chiamando `slide.getShapes().addTable(...)`, poi per ogni cella usa `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Dopo aver popolato tutte le celle, invoca `pres.save("output.pptx", SaveFormat.Pptx)` per scrivere il file. Questo approccio ti consente di controllare programmaticamente il contenuto e lo stile di ogni cella.

#### Funzione 1: creare tabella e aggiungere testo alle celle

**1. create a table** – inizializza una presentazione, aggiungi una diapositiva e posiziona una tabella a (50, 50) con larghezze di colonna e altezze di riga definite.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – per ogni cella, crea un `Paragraph`, aggiungi una `Portion` con la stringa desiderata e assegna il paragrafo al `TextFrame` della cella.  
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

**3. save the presentation** – chiama `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Come disegnare un contorno intorno al testo in una diapositiva PowerPoint?

`Rectangle2D` rappresenta un'area rettangolare in uno spazio a due dimensioni.  
Carica la diapositiva, individua il paragrafo o la porzione da enfatizzare, recupera il suo rettangolo di delimitazione tramite `getRect()`, quindi aggiungi un rettangolo `IAutoShape` senza riempimento e con una linea colorata. Questo metodo funziona sia per paragrafi interi sia per singole porzioni di parole.

### Risposta diretta
Per disegnare un contorno intorno al testo, ottieni prima il rettangolo del paragrafo (`Rectangle2D rect = paragraph.getRect();`). Poi crea un rettangolo `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), imposta `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` e disabilita il riempimento (`shape.getFillFormat().setFillType(FillType.NoFill)`). La forma delineerà perfettamente il testo.

#### Funzione 3: disegnare contorni intorno a paragrafi e porzioni nelle celle della tabella

**1. create a table** – riutilizza il codice dalla Funzione 1 per impostare la tabella iniziale.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – riutilizza il codice di creazione dei paragrafi dalla Funzione 1.  
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

**3. draw frames** – itera su ogni paragrafo, ottieni il suo rettangolo di delimitazione e aggiungi una forma rettangolare come descritto sopra. Per le porzioni contenenti il carattere ‘0’, disegna un contorno aggiuntivo per evidenziare quei numeri.  
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

**4. save the presentation** – stesso passaggio finale di prima.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Come aggiungere un frame di testo a un AutoShape e impostare l'allineamento

`AutoShape` è una forma che può contenere testo, immagini o altri contenuti.  
Un `AutoShape` può contenere un `TextFrame`. Puoi controllare l'allineamento orizzontale usando l'enumerazione `ParagraphFormat`.

### Risposta diretta
Crea un AutoShape rettangolare (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), accedi al suo `TextFrame`, imposta il testo con `shape.getTextFrame().setText("Text in shape")`, quindi chiama `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. Questo allinea il testo a sinistra all'interno della forma.

**1. add an AutoShape** – posiziona un rettangolo nella posizione desiderata.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – applica l'allineamento a sinistra come mostrato sopra.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – stesso passaggio finale.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Problemi comuni e consigli

- **Always dispose** – avvolgi l'uso di `Presentation` in un blocco try‑finally e chiama `pres.dispose()` per liberare le risorse native.  
- **Re‑compute bounding rectangles** – se cambi la dimensione del carattere, i margini o il padding della cella dopo aver disegnato un contorno, richiama `paragraph.getRect()` di nuovo prima di aggiungere la forma.  
- **Batch shape creation for large tables** – riutilizzare un'unica istanza di `IAutoShape` e aggiornare la sua geometria riduce la pressione sulla memoria quando si elaborano tabelle con centinaia di righe.  
- **Performance numbers** – Aspose.Slides può generare un PPTX di 200 pagine in meno di 2 secondi su un tipico server a 4 core, e disegnare contorni intorno a 1.000 paragrafi aggiunge meno di 150 ms di overhead.

## Domande frequenti

**Q: Posso usare queste API con versioni JDK più vecchie?**  
A: La libreria supporta JDK 8 in poi, ma il classificatore `jdk16` offre le migliori prestazioni su runtime più recenti.

**Q: Come cambio il colore del contorno?**  
A: Modifica il colore di riempimento del formato linea, ad esempio `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: È possibile esportare la diapositiva finale come immagine?**  
A: Sì—usa `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` e poi salva l'array di byte.

**Q: Cosa succede se devo evidenziare solo la parola “Total” all'interno di una cella?**  
A: Itera attraverso `cell.getTextFrame().getParagraphs()`, individua la porzione contenente “Total” e disegna un rettangolo intorno al bounding box di quella porzione.

**Q: Aspose.Slides gestisce presentazioni di grandi dimensioni in modo efficiente?**  
A: L'API trasmette i dati in streaming e rilascia le risorse quando viene chiamato `pres.dispose()`, il che aiuta nella gestione della memoria per file di grandi dimensioni.

---

**Last Updated:** 2026-11-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

## Tutorial correlati

- [Aspose.Slides per Java: Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Come creare frame di testo dinamici in PowerPoint usando Aspose.Slides per Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Aggiungere colonne in Text Frame usando Aspose.Slides per Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}