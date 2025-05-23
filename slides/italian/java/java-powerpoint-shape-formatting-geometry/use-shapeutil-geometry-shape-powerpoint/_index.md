---
"description": "Crea forme personalizzate in PowerPoint con Aspose.Slides per Java. Segui questa guida passo passo per migliorare le tue presentazioni."
"linktitle": "Utilizzare ShapeUtil per la forma geometrica in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Utilizzare ShapeUtil per la forma geometrica in PowerPoint"
"url": "/it/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Utilizzare ShapeUtil per la forma geometrica in PowerPoint

## Introduzione
Creare presentazioni PowerPoint visivamente accattivanti spesso richiede più del semplice utilizzo di forme e testo standard. Immagina di poter aggiungere forme e percorsi di testo personalizzati direttamente nelle diapositive, migliorando l'impatto visivo della tua presentazione. Utilizzando Aspose.Slides per Java, puoi ottenere questo risultato con facilità. Questo tutorial ti guiderà attraverso il processo di utilizzo di `ShapeUtil` Corso per creare forme geometriche nelle presentazioni di PowerPoint. Che tu sia uno sviluppatore esperto o alle prime armi, questa guida passo passo ti aiuterà a sfruttare la potenza di Aspose.Slides per Java per creare contenuti straordinari e personalizzati.
## Prerequisiti
Prima di immergerci nel tutorial, ecco alcune cose di cui avrai bisogno:
1. Java Development Kit (JDK): assicurati di avere installato sul tuo computer la versione JDK 8 o superiore.
2. Aspose.Slides per Java: scarica l'ultima versione da [pagina di download](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo: utilizzare qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
4. Licenza temporanea: Ottieni una licenza temporanea gratuita da [Pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/) per sbloccare tutte le funzionalità di Aspose.Slides per Java.
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
Per prima cosa, configura il tuo progetto Java e aggiungi Aspose.Slides per Java alle dipendenze del progetto. Puoi farlo aggiungendo direttamente i file JAR o utilizzando uno strumento di build come Maven o Gradle.
## Passaggio 2: creare una nuova presentazione
Inizia creando un nuovo oggetto di presentazione PowerPoint. Questo oggetto sarà l'area di lavoro su cui aggiungerai le tue forme personalizzate.
```java
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungere una forma rettangolare
Successivamente, aggiungi una forma rettangolare di base alla prima diapositiva della presentazione. Questa forma verrà modificata in seguito per includere un percorso geometrico personalizzato.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## Passaggio 4: recuperare e modificare il percorso geometrico
Recupera il percorso geometrico della forma rettangolare e modifica la sua modalità di riempimento in `None`Questo passaggio è fondamentale perché consente di combinare questo percorso con un altro percorso geometrico personalizzato.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## Passaggio 5: creare un percorso geometrico personalizzato dal testo
Ora, crea un percorso geometrico personalizzato basato sul testo. Ciò comporta la conversione di una stringa di testo in un percorso grafico e quindi la conversione di tale percorso in un percorso geometrico.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## Passaggio 6: combinare i percorsi geometrici
Combina il percorso geometrico originale con il nuovo percorso geometrico basato sul testo e imposta questa combinazione sulla forma.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## Passaggio 7: Salva la presentazione
Infine, salva la presentazione modificata in un file. Verrà generato un file PowerPoint con le tue forme personalizzate.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## Conclusione
Congratulazioni! Hai appena creato una forma geometrica personalizzata in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti ha guidato passo dopo passo, dalla configurazione del progetto alla generazione e combinazione di percorsi geometrici. Padroneggiando queste tecniche, puoi aggiungere elementi unici e accattivanti alle tue presentazioni, rendendole uniche.
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per lavorare con file PowerPoint in Java. Permette di creare, modificare e convertire presentazioni a livello di codice.
### Come faccio a installare Aspose.Slides per Java?
Puoi scaricare l'ultima versione da [pagina di download](https://releases.aspose.com/slides/java/) e aggiungi i file JAR al tuo progetto.
### Posso usare Aspose.Slides gratuitamente?
Aspose.Slides offre una versione di prova gratuita, che puoi scaricare da [Qui](https://releases.aspose.com/)Per usufruire di tutte le funzionalità è necessario acquistare una licenza.
### A cosa serve la classe ShapeUtil?
IL `ShapeUtil` La classe in Aspose.Slides fornisce metodi di utilità per lavorare con le forme, ad esempio convertendo percorsi grafici in percorsi geometrici.
### Dove posso ottenere supporto per Aspose.Slides?
Puoi ottenere supporto da [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}