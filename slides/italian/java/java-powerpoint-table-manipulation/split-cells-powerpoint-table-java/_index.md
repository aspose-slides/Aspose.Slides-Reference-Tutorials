---
title: Dividi celle nella tabella di PowerPoint utilizzando Java
linktitle: Dividi celle nella tabella di PowerPoint utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come dividere, unire e formattare le celle della tabella PowerPoint a livello di codice utilizzando Aspose.Slides per Java. Progettazione della presentazione principale.
type: docs
weight: 11
url: /it/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/
---
## introduzione
In questo tutorial imparerai come manipolare le tabelle di PowerPoint in Java utilizzando Aspose.Slides. Le tabelle sono un componente fondamentale nelle presentazioni, spesso utilizzate per organizzare e presentare i dati in modo efficace. Aspose.Slides offre solide funzionalità per creare, modificare e migliorare le tabelle a livello di codice, offrendo flessibilità nella progettazione e nel layout.
## Prerequisiti
Prima di iniziare questo tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
- JDK (Java Development Kit) installato sul tuo computer.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Ambiente di sviluppo integrato (IDE) come Eclipse, IntelliJ IDEA o qualsiasi altro a tua scelta.

## Importa pacchetti
Per iniziare a lavorare con Aspose.Slides per Java, devi importare i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: impostazione della presentazione
 Innanzitutto, istanziare il file`Presentation` classe per creare una nuova presentazione di PowerPoint.
```java
// Il percorso della directory in cui desideri salvare la presentazione di output
String dataDir = "Your_Document_Directory/";
// Crea un'istanza della classe di presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
```
## Passaggio 2: accesso alla diapositiva e aggiunta di una tabella
Accedi alla prima diapositiva e aggiungivi una forma di tabella. Definisci colonne con larghezze e righe con altezze.
```java
try {
    // Accedi alla prima diapositiva
    ISlide slide = presentation.getSlides().get_Item(0);
    // Definisci colonne con larghezze e righe con altezze
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // Aggiungi la forma della tabella alla diapositiva
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Passaggio 3: impostazione del formato del bordo per ciascuna cella
Scorri ogni cella della tabella e imposta la formattazione del bordo (colore, larghezza, ecc.).
```java
    // Imposta il formato del bordo per ogni cella
    for (IRow row : table.getRows()) {
        for (ICell cell : (Iterable<ICell>) row) {
            cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
            cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
            cell.getCellFormat().getBorderTop().setWidth(5);
            // Imposta una formattazione simile per gli altri bordi (in basso, a sinistra, a destra)
            // ...
        }
    }
```
## Passaggio 4: unione delle celle
Unisci le celle nella tabella secondo necessità. Ad esempio, unisci le celle da (1,1) a (2,1) e da (1,2) a (2,2).
```java
    // Unione celle (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // Unione celle (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Passaggio 5: divisione delle celle
Dividi una cella specifica in più celle in base alla larghezza.
```java
    // Cella divisa (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## Passaggio 6: salvataggio della presentazione
Salva la presentazione modificata su disco.
```java
    // Scrivi PPTX su disco
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // Smaltire l'oggetto della presentazione
    if (presentation != null) presentation.dispose();
}
```

## Conclusione
La manipolazione delle tabelle di PowerPoint a livello di codice utilizzando Aspose.Slides per Java offre un modo efficace per personalizzare le presentazioni in modo efficiente. Seguendo questo tutorial, hai imparato come dividere celle, unire celle e impostare i bordi delle celle in modo dinamico, migliorando la tua capacità di creare presentazioni visivamente accattivanti a livello di codice.

## Domande frequenti
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/java/).
### Come posso scaricare Aspose.Slides per Java?
 Puoi scaricarlo da[questo link](https://releases.aspose.com/slides/java/).
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto dal forum Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11).
### Posso ottenere una licenza temporanea per Aspose.Slides per Java?
 Sì, puoi ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).