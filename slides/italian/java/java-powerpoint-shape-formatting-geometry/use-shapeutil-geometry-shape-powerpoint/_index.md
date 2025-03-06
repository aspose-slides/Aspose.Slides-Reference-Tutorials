---
title: Utilizzare ShapeUtil per la forma geometrica in PowerPoint
linktitle: Utilizzare ShapeUtil per la forma geometrica in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Crea forme personalizzate in PowerPoint con Aspose.Slides per Java. Segui questa guida passo passo per migliorare le tue presentazioni.
type: docs
weight: 23
url: /it/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---
## introduzione
La creazione di presentazioni PowerPoint visivamente accattivanti spesso richiede molto più del semplice utilizzo di forme e testo standard. Immagina di poter aggiungere forme e percorsi di testo personalizzati direttamente nelle tue diapositive, migliorando l'impatto visivo della tua presentazione. Utilizzando Aspose.Slides per Java, puoi raggiungere questo obiettivo facilmente. Questo tutorial ti guiderà attraverso il processo di utilizzo di`ShapeUtil` classe per creare forme geometriche nelle presentazioni di PowerPoint. Che tu sia uno sviluppatore esperto o abbia appena iniziato, questa guida passo passo ti aiuterà a sfruttare la potenza di Aspose.Slides per Java per creare contenuti straordinari e personalizzati.
## Prerequisiti
Prima di immergerci nel tutorial, ci sono alcune cose di cui avrai bisogno:
1. Java Development Kit (JDK): assicurati di avere JDK 8 o versione successiva installata sul tuo computer.
2.  Aspose.Slides per Java: scarica l'ultima versione da[pagina di download](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo: utilizza qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
4.  Licenza temporanea: ottieni una licenza temporanea gratuita da[Pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/) per sbloccare la piena funzionalità di Aspose.Slides per Java.
## Importa pacchetti
Per iniziare, è necessario importare i pacchetti necessari per lavorare con Aspose.Slides e Java AWT (Abstract Window Toolkit):
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## Passaggio 1: impostazione del progetto
Innanzitutto, imposta il tuo progetto Java e aggiungi Aspose.Slides per Java alle dipendenze del tuo progetto. Puoi farlo aggiungendo direttamente i file JAR o utilizzando uno strumento di creazione come Maven o Gradle.
## Passaggio 2: crea una nuova presentazione
Inizia creando un nuovo oggetto di presentazione di PowerPoint. Questo oggetto sarà la tela in cui aggiungerai le tue forme personalizzate.
```java
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungi una forma rettangolare
Successivamente, aggiungi una forma rettangolare di base alla prima diapositiva della presentazione. Questa forma verrà modificata successivamente per includere un percorso geometrico personalizzato.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## Passaggio 4: recuperare e modificare il percorso della geometria
 Recupera il percorso geometrico della forma rettangolare e modifica la modalità di riempimento in`None`. Questo passaggio è fondamentale in quanto ti consente di combinare questo percorso con un altro percorso geometrico personalizzato.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## Passaggio 5: crea un percorso geometrico personalizzato dal testo
Ora crea un percorso geometrico personalizzato basato sul testo. Ciò comporta la conversione di una stringa di testo in un percorso grafico e quindi la conversione di tale percorso in un percorso geometrico.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## Passaggio 6: combina i percorsi geometrici
Combina il percorso geometrico originale con il nuovo percorso geometrico basato su testo e imposta questa combinazione sulla forma.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## Passaggio 7: salva la presentazione
Infine, salva la presentazione modificata in un file. Verrà generato un file PowerPoint con le tue forme personalizzate.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## Conclusione
Congratulazioni! Hai appena creato una forma geometrica personalizzata in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti ha guidato attraverso ogni passaggio, dall'impostazione del tuo progetto alla generazione e combinazione di percorsi geometrici. Padroneggiando queste tecniche, puoi aggiungere elementi unici e accattivanti alle tue presentazioni, facendole risaltare.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per lavorare con file PowerPoint in Java. Ti consente di creare, modificare e convertire presentazioni a livello di codice.
### Come installo Aspose.Slides per Java?
 È possibile scaricare la versione più recente da[pagina di download](https://releases.aspose.com/slides/java/) e aggiungi i file JAR al tuo progetto.
### Posso utilizzare Aspose.Slides gratuitamente?
Aspose.Slides offre una versione di prova gratuita, da cui puoi scaricare[Qui](https://releases.aspose.com/)Per la piena funzionalità è necessario acquistare una licenza.
### Qual è l'uso della classe ShapeUtil?
 IL`ShapeUtil` La classe in Aspose.Slides fornisce metodi di utilità per lavorare con le forme, come la conversione di percorsi grafici in percorsi geometrici.
### Dove posso ottenere supporto per Aspose.Slides?
 Puoi ottenere supporto da[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).