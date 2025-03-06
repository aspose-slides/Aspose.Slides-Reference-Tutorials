---
title: Aggiungi animazioni alle forme in PowerPoint
linktitle: Aggiungi animazioni alle forme in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere animazioni alle forme in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial dettagliato. Perfetto per creare presentazioni accattivanti.
weight: 10
url: /it/java/java-powerpoint-animation-shape-manipulation/add-animations-to-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
La creazione di presentazioni accattivanti spesso richiede l'aggiunta di animazioni a forme e testo. Le animazioni possono rendere le tue diapositive più dinamiche e accattivanti, garantendo che il tuo pubblico rimanga interessato. In questo tutorial ti guideremo attraverso il processo di aggiunta di animazioni alle forme in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Alla fine di questo articolo sarai in grado di creare animazioni professionali senza sforzo.
## Prerequisiti
Prima di immergerci nel tutorial, assicuriamoci di avere tutto ciò di cui hai bisogno:
1.  Aspose.Slides per Java Library: è necessario che sia installata la libreria Aspose.Slides per Java. Puoi[scaricalo qui](https://releases.aspose.com/slides/java/).
2. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer.
3. Ambiente di sviluppo integrato (IDE): utilizza qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
4. Conoscenza di base di Java: questo tutorial presuppone che tu abbia una conoscenza di base della programmazione Java.
## Importa pacchetti
Per iniziare, dovrai importare i pacchetti necessari per Aspose.Slides e altre classi Java richieste.
```java
import com.aspose.slides.*;

import java.awt.geom.Point2D;
import java.io.File;
import java.lang.reflect.Array;
```
## Passaggio 1: imposta la directory del progetto
Innanzitutto, crea una directory per i file di progetto.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Passaggio 2: inizializzare l'oggetto di presentazione
 Successivamente, istanziare il file`Presentation` classe per rappresentare il tuo file PowerPoint.
```java
// Crea un'istanza della classe Presentation che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla prima diapositiva
Ora accedi alla prima diapositiva della presentazione in cui aggiungerai le animazioni.
```java
// Accedi alla prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungi una forma alla diapositiva
Aggiungi una forma rettangolare alla diapositiva e inserisci del testo al suo interno.
```java
// Aggiungi una forma rettangolare alla diapositiva
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 150, 250, 25);
ashp.addTextFrame("Animated TextBox");
```
## Passaggio 5: applica un effetto di animazione
Applica l'effetto di animazione "PathFootball" alla forma.
```java
// Aggiungi l'effetto di animazione PathFootBall
pres.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(ashp, EffectType.PathFootball,
        EffectSubtype.None, EffectTriggerType.AfterPrevious);
```
## Passaggio 6: crea un trigger interattivo
Crea una forma di pulsante che attiverà l'animazione quando viene cliccato.
```java
// Crea una forma a "pulsante" per attivare l'animazione
IShape shapeTrigger = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Bevel, 10, 10, 20, 20);
```
## Passaggio 7: definire la sequenza interattiva
Definire una sequenza di effetti per il pulsante.
```java
// Crea una sequenza di effetti per il pulsante
ISequence seqInter = pres.getSlides().get_Item(0).getTimeline().getInteractiveSequences().add(shapeTrigger);
```
## Passaggio 8: aggiungi un percorso utente personalizzato
Aggiungi un'animazione personalizzata del percorso utente alla forma.
```java
// Aggiungi un effetto di animazione del percorso utente personalizzato
IEffect fxUserPath = seqInter.addEffect(ashp, EffectType.PathUser, EffectSubtype.None, EffectTriggerType.OnClick);
// Crea effetti di movimento
IMotionEffect motionBhv = ((IMotionEffect) fxUserPath.getBehaviors().get_Item(0));
// Definire i punti del percorso
Point2D.Float[] pts = (Point2D.Float[]) Array.newInstance(Point2D.Float.class, 1);
pts[0] = new Point2D.Float(0.076f, 0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, true);
pts[0] = new Point2D.Float(-0.076f, -0.59f);
motionBhv.getPath().add(MotionCommandPathType.LineTo, pts, MotionPathPointsType.Auto, false);
motionBhv.getPath().add(MotionCommandPathType.End, null, MotionPathPointsType.Auto, false);
```
## Passaggio 9: salva la presentazione
Infine, salva la presentazione nella posizione desiderata.
```java
// Salva la presentazione come file PPTX
pres.save(dataDir + "AnimExample_out.pptx", SaveFormat.Pptx);
// Smaltire l'oggetto della presentazione
if (pres != null) pres.dispose();
```
## Conclusione
il gioco è fatto! Hai aggiunto con successo animazioni alle forme in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria semplifica il miglioramento delle tue presentazioni con effetti dinamici, garantendo che il tuo pubblico rimanga coinvolto. Ricorda, la pratica rende perfetti, quindi continua a sperimentare diversi effetti e trigger per vedere cosa funziona meglio per le tue esigenze.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare, modificare e manipolare presentazioni PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides gratuitamente?
 Puoi provare Aspose.Slides gratuitamente con a[licenza temporanea](https://purchase.aspose.com/temporary-license/). Per l'uso continuato è necessaria una licenza a pagamento.
### Quali versioni Java sono compatibili con Aspose.Slides?
Aspose.Slides supporta Java SE 6 e versioni successive.
### Come posso aggiungere animazioni diverse a più forme?
Puoi aggiungere animazioni diverse a più forme ripetendo i passaggi per ciascuna forma e specificando effetti diversi secondo necessità.
### Dove posso trovare altri esempi e documentazione?
 Dai un'occhiata a[documentazione](https://reference.aspose.com/slides/java/) E[Forum di assistenza](https://forum.aspose.com/c/slides/11)per ulteriori esempi e aiuto.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
