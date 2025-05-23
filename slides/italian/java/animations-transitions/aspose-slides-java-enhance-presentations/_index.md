---
"date": "2025-04-18"
"description": "Scopri come migliorare le tue presentazioni padroneggiando la manipolazione di tabelle e cornici con Aspose.Slides per Java. Questa guida illustra come creare tabelle, aggiungere cornici di testo e disegnare cornici attorno a contenuti specifici."
"title": "Aspose.Slides per Java&#58; padronanza della manipolazione di tabelle e frame nelle presentazioni"
"url": "/it/java/animations-transitions/aspose-slides-java-enhance-presentations/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare la manipolazione di tabelle e frame nelle presentazioni con Aspose.Slides per Java

## Introduzione

Presentare i dati in modo efficace può essere difficile in PowerPoint. Che tu sia uno sviluppatore software o un designer di presentazioni, l'utilizzo di tabelle visivamente accattivanti e l'aggiunta di cornici di testo possono rendere le tue diapositive più accattivanti. Questo tutorial illustra come utilizzare Aspose.Slides per Java per aggiungere testo alle celle di una tabella e disegnare cornici attorno a paragrafi e porzioni contenenti caratteri specifici come "0". Padroneggiando queste tecniche, migliorerai le tue presentazioni con precisione e stile.

### Cosa imparerai:
- Creare tabelle nelle diapositive e inserirvi testo.
- Allineamento del testo all'interno delle forme automatiche per una migliore presentazione.
- Disegnare cornici attorno a paragrafi e porzioni per enfatizzare il contenuto.
- Applicazioni pratiche di queste funzionalità in scenari reali.

Pronti a trasformare le vostre presentazioni? Iniziamo!

## Prerequisiti

Prima di immergerti nel codice, assicurati di avere quanto segue:

### Librerie richieste
Avrai bisogno di Aspose.Slides per Java. Ecco come includerlo usando Maven o Gradle:

**Esperto:**
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
Assicurati di avere installato un Java Development Kit (JDK), preferibilmente JDK 16 o successivo, poiché questo esempio utilizza il `jdk16` classificatore.

### Prerequisiti di conoscenza
- Conoscenza di base della programmazione Java.
- Familiarità con software di presentazione come PowerPoint.
- Esperienza nell'uso di un ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse.

## Impostazione di Aspose.Slides per Java

Per iniziare a utilizzare Aspose.Slides, segui questi passaggi:

1. **Installa la libreria**: Utilizza Maven o Gradle per gestire le dipendenze oppure scaricalo direttamente da [Aspose.Slides per le versioni Java](https://releases.aspose.com/slides/java/).

2. **Acquisizione della licenza**:
   - Inizia con una prova gratuita scaricando una licenza temporanea da [Licenza temporanea](https://purchase.aspose.com/temporary-license/).
   - Per un accesso completo, si consiglia di acquistare una licenza presso [Acquista Aspose.Slides](https://purchase.aspose.com/buy).

3. **Inizializzazione di base**:
Inizializza il tuo ambiente di presentazione con il seguente frammento di codice:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Il tuo codice qui
} finally {
    if (pres != null) pres.dispose();
}
```

## Guida all'implementazione

Questa sezione illustra le diverse funzionalità che è possibile implementare utilizzando Aspose.Slides per Java.

### Funzionalità 1: crea una tabella e aggiungi testo alle celle

#### Panoramica
Questa funzione illustra come creare una tabella nella prima diapositiva e popolare celle specifiche con del testo. 

##### Passaggi:
**1. Crea una tabella**
Per prima cosa, inizializza la presentazione e aggiungi una tabella nella posizione (50, 50) con le larghezze delle colonne e le altezze delle righe specificate.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. Aggiungi testo alle celle**
Crea paragrafi con porzioni di testo e aggiungile a una cella specifica.
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
**3. Salva la presentazione**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Funzionalità 2: aggiungi TextFrame ad AutoShape e imposta l'allineamento

#### Panoramica
Scopri come aggiungere una cornice di testo con un allineamento specifico a una forma automatica.

##### Passaggi:
**1. Aggiungi una forma automatica**
Aggiungere un rettangolo come forma automatica nella posizione (400, 100) con le dimensioni specificate.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```
**2. Imposta l'allineamento del testo**
Imposta il testo su "Testo in forma" e allinealo a sinistra.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
**3. Salva la presentazione**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Funzionalità 3: Disegna cornici attorno a paragrafi e porzioni nelle celle della tabella

#### Panoramica
Questa funzionalità si concentra sul disegno di cornici attorno ai paragrafi e alle parti che contengono '0' nelle celle della tabella.

##### Passaggi:
**1. Crea una tabella**
Riutilizzare il codice da "Crea tabella e aggiungi testo alle celle" per la configurazione iniziale.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
**2. Aggiungi paragrafi**
Riutilizza il codice di creazione dei paragrafi della funzionalità precedente.
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
**3. Disegnare le cornici**
Passa attraverso paragrafi e porzioni per disegnare cornici attorno ad essi.
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
**4. Salva la presentazione**
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusione
Seguendo questa guida, puoi migliorare efficacemente le tue presentazioni utilizzando Aspose.Slides per Java. Padroneggiare la manipolazione di tabelle e frame ti consente di creare diapositive più coinvolgenti e visivamente accattivanti. Per ulteriori approfondimenti, valuta la possibilità di approfondire le funzionalità aggiuntive di Aspose.Slides o di integrarlo con altre applicazioni Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}