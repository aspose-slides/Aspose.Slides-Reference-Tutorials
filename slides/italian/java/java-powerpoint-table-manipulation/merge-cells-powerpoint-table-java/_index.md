---
title: Unisci celle nella tabella PowerPoint con Java
linktitle: Unisci celle nella tabella PowerPoint con Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come unire le celle nelle tabelle di PowerPoint utilizzando Aspose.Slides per Java. Migliora il layout della tua presentazione con questa guida passo passo.
weight: 17
url: /it/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Unisci celle nella tabella PowerPoint con Java

## introduzione
In questo tutorial imparerai come unire in modo efficace le celle all'interno di una tabella di PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint a livello di codice. Unendo le celle in una tabella, puoi personalizzare il layout e la struttura delle diapositive della presentazione, migliorandone la chiarezza e l'attrattiva visiva.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione Java.
- JDK (Java Development Kit) installato sul tuo computer.
- IDE (ambiente di sviluppo integrato) come IntelliJ IDEA o Eclipse.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, assicurati di aver importato i pacchetti necessari per lavorare con Aspose.Slides:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: imposta il tuo progetto
Innanzitutto, crea un nuovo progetto Java nel tuo IDE preferito e aggiungi la libreria Aspose.Slides per Java alle dipendenze del tuo progetto.
## Passaggio 2: creare un'istanza dell'oggetto di presentazione
 Istanziare il`Presentation` class per rappresentare il file PPTX con cui stai lavorando:
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: accedi alla diapositiva
Accedi alla diapositiva in cui desideri aggiungere la tabella. Ad esempio, per accedere alla prima diapositiva:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 4: definire le dimensioni della tabella
 Definisci le colonne e le righe per la tua tabella. Specificare la larghezza delle colonne e l'altezza delle righe come matrici di`double`:
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## Passaggio 5: aggiungi la forma della tabella alla diapositiva
Aggiungi una forma di tabella alla diapositiva utilizzando le dimensioni definite:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Passaggio 6: personalizza i bordi delle celle
Imposta il formato del bordo per ogni cella nella tabella. Questo esempio imposta un bordo rosso continuo con una larghezza di 5 per ogni cella:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // Imposta il formato del bordo per ciascun lato della cella
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## Passaggio 7: unisci le celle nella tabella
 Per unire le celle nella tabella, utilizzare il file`mergeCells` metodo. Questo esempio unisce le celle da (1, 1) a (2, 1) e da (1, 2) a (2, 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Passaggio 8: salva la presentazione
Infine, salva la presentazione modificata in un file PPTX sul tuo disco:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Seguendo questi passaggi, hai imparato con successo come unire le celle all'interno di una tabella di PowerPoint utilizzando Aspose.Slides per Java. Questa tecnica ti consente di creare presentazioni più complesse e visivamente accattivanti a livello di codice, migliorando la produttività e le opzioni di personalizzazione.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è un'API Java per creare, manipolare e convertire presentazioni PowerPoint a livello di codice.
### Come posso scaricare Aspose.Slides per Java?
 È possibile scaricare Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
### Posso provare Aspose.Slides per Java prima dell'acquisto?
 Sì, puoi ottenere una prova gratuita di Aspose.Slides per Java da[Qui](https://releases.aspose.com/).
### Dove posso trovare la documentazione per Aspose.Slides per Java?
 Puoi trovare la documentazione[Qui](https://reference.aspose.com/slides/java/).
### Come posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto dal forum della community Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
