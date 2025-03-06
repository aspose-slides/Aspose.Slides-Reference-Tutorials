---
title: Aggiungi punti elenco paragrafi in PowerPoint utilizzando Java
linktitle: Aggiungi punti elenco paragrafi in PowerPoint utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere punti elenco di paragrafo nelle diapositive di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti guida passo dopo passo con esempi di codice.
weight: 15
url: /it/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
L'aggiunta di punti elenco di paragrafo migliora la leggibilità e la struttura delle presentazioni PowerPoint. Aspose.Slides per Java fornisce strumenti robusti per manipolare le presentazioni a livello di codice, inclusa la possibilità di formattare il testo con vari stili di punti elenco. In questo tutorial imparerai come integrare i punti elenco nelle diapositive di PowerPoint utilizzando il codice Java, sfruttando Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Conoscenza base della programmazione Java.
- JDK (Java Development Kit) installato sul tuo sistema.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti Aspose.Slides necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta il tuo progetto
Innanzitutto, crea un nuovo progetto Java e aggiungi la libreria Aspose.Slides per Java al percorso di compilazione del tuo progetto.
## Passaggio 2: inizializzare una presentazione
Inizializza un oggetto di presentazione (`Presentation`) per iniziare a lavorare con le diapositive.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Creazione di un'istanza di presentazione
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla diapositiva e alla cornice di testo
Accedi alla diapositiva (`ISlide`e la relativa cornice di testo (`ITextFrame`) dove vuoi aggiungere punti elenco.
```java
// Accesso alla prima diapositiva
ISlide slide = pres.getSlides().get_Item(0);
// Aggiunta e accesso a Autoshape
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Accesso alla cornice di testo della forma automatica creata
ITextFrame txtFrm = aShp.getTextFrame();
```
## Passaggio 4: crea e formatta paragrafi con punti elenco
Crea paragrafi (`Paragraph`) e impostare gli stili dei punti elenco, il rientro e il testo.
```java
// Creazione di un paragrafo
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Creare un altro paragrafo
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Passaggio 5: salva la presentazione
Salvare la presentazione modificata in un file PowerPoint (`PPTX`).
```java
// Scrivere la presentazione come file PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Passaggio 6: ripulire le risorse
Eliminare l'oggetto della presentazione per liberare risorse.
```java
// Smaltire l'oggetto della presentazione
if (pres != null) {
    pres.dispose();
}
```

## Conclusione
L'aggiunta di punti elenco di paragrafo in PowerPoint utilizzando Aspose.Slides per Java è semplice con gli esempi di codice forniti. Personalizza gli stili e la formattazione dei punti elenco per adattarli perfettamente alle tue esigenze di presentazione.

## Domande frequenti
### Posso personalizzare i colori dei proiettili?
Sì, puoi impostare colori personalizzati per i punti elenco utilizzando l'API Aspose.Slides.
### Come faccio ad aggiungere punti elenco nidificati?
L'annidamento dei punti elenco implica l'aggiunta di paragrafi all'interno dei paragrafi, regolando di conseguenza il rientro.
### Posso creare stili di punti elenco diversi per diapositive diverse?
Sì, puoi applicare stili di punti elenco univoci a diapositive diverse a livello di codice.
### Aspose.Slides è compatibile con Java 11?
Sì, Aspose.Slides supporta Java 11 e versioni successive.
### Dove posso trovare altri esempi e documentazione?
 Visita[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/) per guide ed esempi completi.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
