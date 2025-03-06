---
title: Allinea verticalmente il testo in Java PowerPoint
linktitle: Allinea verticalmente il testo in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come allineare verticalmente il testo nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per una formattazione perfetta delle diapositive.
type: docs
weight: 10
url: /it/java/java-powerpoint-text-alignment-formatting/vertically-align-text-java-powerpoint/
---
## introduzione
In questo tutorial imparerai come allineare verticalmente il testo all'interno delle celle della tabella in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. L'allineamento verticale del testo è un aspetto cruciale della progettazione delle diapositive, poiché garantisce che i tuoi contenuti siano presentati in modo ordinato e professionale. Aspose.Slides fornisce potenti funzionalità per manipolare e formattare le presentazioni in modo programmatico, dandoti il pieno controllo su ogni aspetto delle tue diapositive.
## Prerequisiti
Prima di immergerti in questo tutorial, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base della programmazione Java.
- JDK (Java Development Kit) installato sul tuo computer.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- IDE (ambiente di sviluppo integrato) come IntelliJ IDEA o Eclipse installato.

## Importa pacchetti
Prima di procedere con il tutorial, assicurati di importare i pacchetti Aspose.Slides necessari nel tuo file Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Passaggio 1: configura il tuo progetto Java
Assicurati di aver impostato un nuovo progetto Java nel tuo IDE preferito e di aver aggiunto la libreria Aspose.Slides al percorso di compilazione del tuo progetto.
## Passaggio 2: inizializzare l'oggetto Presentazione
 Crea un'istanza di`Presentation` classe per iniziare a lavorare con una nuova presentazione PowerPoint:
```java
Presentation presentation = new Presentation();
```
## Passaggio 3: accedi alla prima diapositiva
Ottieni la prima diapositiva della presentazione per aggiungervi contenuti:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Passaggio 4: definire le dimensioni della tabella e aggiungere una tabella
Definisci la larghezza delle colonne e l'altezza delle righe per la tabella, quindi aggiungi la forma della tabella alla diapositiva:
```java
double[] dblCols = {120, 120, 120, 120};
double[] dblRows = {100, 100, 100, 100};
ITable tbl = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Passaggio 5: imposta il contenuto del testo nelle celle della tabella
Imposta il contenuto del testo per righe specifiche nella tabella:
```java
tbl.getRows().get_Item(1).get_Item(0).getTextFrame().setText("10");
tbl.getRows().get_Item(2).get_Item(0).getTextFrame().setText("20");
tbl.getRows().get_Item(3).get_Item(0).getTextFrame().setText("30");
```
## Passaggio 6: accedi alla cornice di testo e formatta il testo
Accedi alla cornice di testo e formatta il testo all'interno di una cella specifica:
```java
ITextFrame txtFrame = tbl.get_Item(0, 0).getTextFrame();
IParagraph paragraph = txtFrame.getParagraphs().get_Item(0);
IPortion portion = paragraph.getPortions().get_Item(0);
portion.setText("Text here");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Passaggio 7: allinea il testo verticalmente
Imposta l'allineamento verticale per il testo all'interno della cella:
```java
ICell cell = tbl.get_Item(0, 0);
cell.setTextAnchorType(TextAnchorType.Center);
cell.setTextVerticalType(TextVerticalType.Vertical270);
```
## Passaggio 8: salva la presentazione
Salva la presentazione modificata in una posizione specifica sul tuo disco:
```java
String dataDir = "Your Document Directory";
presentation.save(dataDir + "Vertical_Align_Text_out.pptx", SaveFormat.Pptx);
```
## Passaggio 9: pulire le risorse
 Smaltire il`Presentation` oggetto di rilasciare risorse:
```java
if (presentation != null) presentation.dispose();
```

## Conclusione
Seguendo questi passaggi, puoi allineare verticalmente in modo efficace il testo all'interno delle celle della tabella nelle presentazioni Java PowerPoint utilizzando Aspose.Slides. Questa funzionalità migliora l'attrattiva visiva e la chiarezza delle tue diapositive, garantendo che i tuoi contenuti siano presentati in modo professionale.

## Domande frequenti
### Posso allineare verticalmente il testo in altre forme oltre alle tabelle?
Sì, Aspose.Slides fornisce metodi per allineare verticalmente il testo in varie forme, incluse caselle di testo e segnaposto.
### Aspose.Slides supporta anche l'allineamento del testo in orizzontale?
Sì, puoi allineare il testo orizzontalmente utilizzando diverse opzioni di allineamento fornite da Aspose.Slides.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta la generazione di presentazioni compatibili con tutte le principali versioni di Microsoft PowerPoint.
### Dove posso trovare altri esempi e documentazione per Aspose.Slides?
 Visitare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/) per guide complete, riferimenti API ed esempi di codice.
### Come posso ottenere supporto per Aspose.Slides?
 Per assistenza tecnica e supporto comunitario, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).