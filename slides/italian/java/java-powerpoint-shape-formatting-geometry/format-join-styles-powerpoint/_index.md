---
title: Formato Unisci stili in PowerPoint
linktitle: Formato Unisci stili in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come migliorare le tue presentazioni PowerPoint impostando diversi stili di unione delle linee per le forme utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo.
type: docs
weight: 15
url: /it/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---
## introduzione
Creare presentazioni PowerPoint visivamente accattivanti può essere un compito arduo, soprattutto quando si desidera che ogni dettaglio sia perfetto. È qui che Aspose.Slides per Java torna utile. È una potente API che ti consente di creare, manipolare e gestire le presentazioni in modo programmatico. Una delle funzionalità che puoi utilizzare è l'impostazione di diversi stili di unione delle linee per le forme, che possono migliorare significativamente l'estetica delle tue diapositive. In questo tutorial, approfondiremo come utilizzare Aspose.Slides per Java per impostare gli stili di unione per le forme nelle presentazioni di PowerPoint. 
## Prerequisiti
Prima di iniziare, è necessario disporre di alcuni prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer. Puoi scaricarlo da[Il sito web di Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides per Java Library: devi scaricare e includere Aspose.Slides per Java nel tuo progetto. Puoi ottenerlo da[Qui](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA, Eclipse o NetBeans per scrivere ed eseguire il codice Java.
4. Conoscenza di base di Java: una comprensione fondamentale della programmazione Java ti aiuterà a seguire il tutorial.
## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per Aspose.Slides. Questo è essenziale per accedere alle classi e ai metodi richiesti per le nostre manipolazioni di presentazione.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Passaggio 1: impostazione della directory del progetto
Iniziamo creando una directory in cui archiviare i nostri file di presentazione. Ciò garantisce che tutti i nostri file siano organizzati e facilmente accessibili.
```java
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
In questo passaggio definiamo un percorso di directory e controlliamo se esiste. In caso contrario, creiamo la directory. Questo è un modo semplice ma efficace per mantenere i tuoi file organizzati.
## Passaggio 2: inizializzare la presentazione
 Successivamente, istanziamo il file`Presentation` class, che rappresenta il nostro file PowerPoint. Questa è la base su cui costruiremo le nostre diapositive e le nostre forme.
```java
Presentation pres = new Presentation();
```
Questa riga di codice crea una nuova presentazione. Pensalo come aprire un file PowerPoint vuoto in cui aggiungerai tutto il tuo contenuto.
## Passaggio 3: aggiungi forme alla diapositiva
### Ottieni la prima diapositiva
Prima di aggiungere forme, dobbiamo ottenere un riferimento alla prima diapositiva della nostra presentazione. Per impostazione predefinita, una nuova presentazione contiene una diapositiva vuota.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Aggiungi forme rettangolari
Ora aggiungiamo tre forme rettangolari alla nostra diapositiva. Queste forme dimostreranno i diversi stili di unione delle linee.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
In questo passaggio aggiungiamo tre rettangoli nelle posizioni specificate sulla diapositiva. Ciascun rettangolo verrà successivamente stilizzato in modo diverso per mostrare vari stili di unione.
## Passaggio 4: modella le forme
### Imposta il colore di riempimento
Vogliamo che i nostri rettangoli siano riempiti con un colore a tinta unita. Qui scegliamo il nero come colore di riempimento.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Imposta larghezza e colore della linea
Successivamente, definiamo la larghezza e il colore della linea per ciascun rettangolo. Ciò aiuta a differenziare visivamente gli stili di unione.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Passaggio 5: applica gli stili di unione
Il punto forte di questo tutorial è l'impostazione degli stili di unione delle linee. Utilizzeremo tre stili diversi: Mitra, Bevel e Round.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Ogni stile di unione delle linee conferisce alle forme un aspetto unico negli angoli in cui le linee si incontrano. Ciò può essere particolarmente utile per creare diagrammi o illustrazioni visivamente distinti.
## Passaggio 6: aggiungi testo alle forme
Per rendere chiaro cosa rappresenta ciascuna forma, aggiungiamo del testo a ciascun rettangolo che descrive lo stile di unione utilizzato.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
L'aggiunta di testo aiuta a identificare i diversi stili quando presenti o condividi la diapositiva.
## Passaggio 7: salva la presentazione
Infine, salviamo la nostra presentazione nella directory specificata.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Questo comando scrive la presentazione in un file PPTX, che puoi aprire con Microsoft PowerPoint o qualsiasi altro software compatibile.
## Conclusione
E il gioco è fatto! Hai appena creato una diapositiva PowerPoint con tre rettangoli, ciascuno dei quali mostra uno stile di unione di linee diverso utilizzando Aspose.Slides per Java. Questo tutorial non solo ti aiuta a comprendere le basi di Aspose.Slides, ma mostra anche come migliorare le tue presentazioni con stili unici. Buona presentazione!
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare, manipolare e gestire presentazioni PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides per Java in qualsiasi IDE?
Sì, puoi utilizzare Aspose.Slides per Java in qualsiasi IDE supportato da Java come IntelliJ IDEA, Eclipse o NetBeans.
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### Quali sono gli stili di unione delle linee in PowerPoint?
Gli stili di unione delle linee si riferiscono alla forma degli angoli in cui si incontrano due linee. Gli stili comuni includono Mitra, Smusso e Rotondo.
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
 Puoi trovare documentazione dettagliata[Qui](https://reference.aspose.com/slides/java/).