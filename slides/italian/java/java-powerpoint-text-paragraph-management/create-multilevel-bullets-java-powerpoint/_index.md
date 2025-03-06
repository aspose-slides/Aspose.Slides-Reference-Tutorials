---
title: Crea elenchi puntati multilivello in Java PowerPoint
linktitle: Crea elenchi puntati multilivello in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare punti elenco multilivello in PowerPoint utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice e domande frequenti.
weight: 14
url: /it/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
In questo tutorial esploreremo come creare punti elenco multilivello nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. L'aggiunta di punti elenco è un requisito comune per la creazione di contenuti organizzati e visivamente accattivanti nelle presentazioni. Seguiremo il processo passo dopo passo, assicurandoci che entro la fine di questa guida sarai in grado di migliorare le tue presentazioni con elenchi puntati strutturati a più livelli.
## Prerequisiti
Prima di iniziare, assicurati di avere la seguente configurazione:
- Ambiente di sviluppo Java: assicurati che Java Development Kit (JDK) sia installato sul tuo sistema.
-  Aspose.Slides per Java Library: scarica e installa Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
- IDE: utilizza il tuo ambiente di sviluppo integrato Java (IDE) preferito come IntelliJ IDEA, Eclipse o altri.
- Conoscenze di base: sarà utile avere familiarità con la programmazione Java e i concetti di base di PowerPoint.

## Importa pacchetti
Prima di immergerci nel tutorial, importiamo i pacchetti necessari da Aspose.Slides per Java che utilizzeremo durante il tutorial.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta il tuo progetto
Innanzitutto, crea un nuovo progetto Java nel tuo IDE e aggiungi Aspose.Slides per Java alle dipendenze del tuo progetto. Assicurati che il file JAR Aspose.Slides necessario sia incluso nel percorso di compilazione del tuo progetto.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
```
## Passaggio 2: inizializzare l'oggetto di presentazione
Inizia creando una nuova istanza di presentazione. Questo servirà come documento PowerPoint in cui aggiungerai diapositive e contenuti.
```java
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva
Successivamente, accedi alla diapositiva in cui desideri aggiungere i punti elenco multilivello. Per questo esempio, lavoreremo con la prima diapositiva (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungi forma automatica con cornice di testo
Aggiungi una forma alla diapositiva in cui posizionerai il testo con punti elenco multilivello.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Passaggio 5: accedi alla cornice di testo
Accedi alla cornice di testo all'interno della forma in cui aggiungerai paragrafi con punti elenco.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Cancella i paragrafi predefiniti
```
## Passaggio 6: aggiungi paragrafi con punti elenco
Aggiungi paragrafi con diversi livelli di punti elenco. Ecco come puoi aggiungere punti elenco multilivello:
```java
// Primo livello
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// Secondo livello
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Terzo livello
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Quarto livello
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Passaggio 7: salva la presentazione
Infine, salva la presentazione come file PPTX nella directory desiderata.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo spiegato come creare punti elenco multilivello nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi strutturare in modo efficace i tuoi contenuti con elenchi puntati organizzati a diversi livelli, migliorando la chiarezza e l'attrattiva visiva delle tue presentazioni.
## Domande frequenti
### Posso personalizzare ulteriormente i simboli dei punti elenco?
Sì, puoi personalizzare i simboli dei punti elenco modificando i caratteri Unicode o utilizzando forme diverse.
### Aspose.Slides supporta altri tipi di punti elenco?
Sì, Aspose.Slides supporta una varietà di tipi di punti elenco inclusi simboli, numeri e immagini personalizzate.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides genera presentazioni compatibili con Microsoft PowerPoint 2007 e versioni successive.
### Posso automatizzare la generazione di diapositive utilizzando Aspose.Slides?
Sì, Aspose.Slides fornisce API per automatizzare la creazione, la modifica e la manipolazione delle presentazioni PowerPoint.
### Dove posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto dalla community e dagli esperti di Aspose.Slides su[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
