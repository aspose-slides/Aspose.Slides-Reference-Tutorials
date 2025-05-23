---
"description": "Scopri come dividere, unire e formattare le celle delle tabelle di PowerPoint a livello di codice utilizzando Aspose.Slides per Java. Padroneggia la progettazione delle presentazioni."
"linktitle": "Dividi le celle in una tabella di PowerPoint usando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Dividi le celle in una tabella di PowerPoint usando Java"
"url": "/it/java/java-powerpoint-table-manipulation/split-cells-powerpoint-table-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dividi le celle in una tabella di PowerPoint usando Java

## Introduzione
In questo tutorial imparerai a manipolare le tabelle di PowerPoint in Java utilizzando Aspose.Slides. Le tabelle sono un componente fondamentale nelle presentazioni, spesso utilizzate per organizzare e presentare i dati in modo efficace. Aspose.Slides offre funzionalità avanzate per creare, modificare e migliorare le tabelle a livello di codice, offrendo flessibilità nel design e nel layout.
## Prerequisiti
Prima di iniziare questo tutorial, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base della programmazione Java.
- JDK (Java Development Kit) installato sul computer.
- Libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
- Ambiente di sviluppo integrato (IDE) come Eclipse, IntelliJ IDEA o qualsiasi altro di tua scelta.

## Importa pacchetti
Per iniziare a lavorare con Aspose.Slides per Java, è necessario importare i pacchetti necessari nel progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Fase 1: Impostazione della presentazione
Per prima cosa, crea un'istanza del `Presentation` classe per creare una nuova presentazione PowerPoint.
```java
// Il percorso verso la directory in cui si desidera salvare la presentazione di output
String dataDir = "Your_Document_Directory/";
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
```
## Passaggio 2: accesso alla diapositiva e aggiunta di una tabella
Accedi alla prima diapositiva e aggiungi una forma tabella. Definisci le colonne con la larghezza e le righe con l'altezza.
```java
try {
    // Accedi alla prima diapositiva
    ISlide slide = presentation.getSlides().get_Item(0);
    // Definisci le colonne con larghezze e le righe con altezze
    double[] dblCols = {70, 70, 70, 70};
    double[] dblRows = {70, 70, 70, 70};
    // Aggiungi forma tabella alla diapositiva
    ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Passaggio 3: impostazione del formato del bordo per ogni cella
Scorrere ogni cella della tabella e impostare la formattazione del bordo (colore, larghezza, ecc.).
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
Unisci le celle della tabella secondo necessità. Ad esempio, unisci le celle (1,1) con (2,1) e (1,2) con (2,2).
```java
    // Unione di celle (1, 1) x (2, 1)
    table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
    // Unione delle celle (1, 2) x (2, 2)
    table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Passaggio 5: divisione delle celle
Dividere una cella specifica in più celle in base alla larghezza.
```java
    // Cellula divisa (1, 1)
    table.get_Item(1, 1).splitByWidth(table.get_Item(2, 1).getWidth() / 2);
```
## Passaggio 6: salvataggio della presentazione
Salvare la presentazione modificata sul disco.
```java
    // Scrivi PPTX su disco
    presentation.save(dataDir + "CellSplit_out.pptx", SaveFormat.Pptx);
} finally {
    // Eliminare l'oggetto Presentazione
    if (presentation != null) presentation.dispose();
}
```

## Conclusione
La manipolazione programmatica delle tabelle di PowerPoint con Aspose.Slides per Java offre un modo potente per personalizzare le presentazioni in modo efficiente. Seguendo questo tutorial, hai imparato a dividere, unire e impostare dinamicamente i bordi delle celle, migliorando la tua capacità di creare presentazioni visivamente accattivanti a livello di codice.

## Domande frequenti
### Dove posso trovare la documentazione per Aspose.Slides per Java?
Puoi trovare la documentazione [Qui](https://reference.aspose.com/slides/java/).
### Come posso scaricare Aspose.Slides per Java?
Puoi scaricarlo da [questo collegamento](https://releases.aspose.com/slides/java/).
### È disponibile una versione di prova gratuita di Aspose.Slides per Java?
Sì, puoi ottenere una prova gratuita da [Qui](https://releases.aspose.com/).
### Dove posso ottenere supporto per Aspose.Slides per Java?
Puoi ottenere supporto dal forum Aspose.Slides [Qui](https://forum.aspose.com/c/slides/11).
### Posso ottenere una licenza temporanea per Aspose.Slides per Java?
Sì, puoi ottenere una licenza temporanea da [Qui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}