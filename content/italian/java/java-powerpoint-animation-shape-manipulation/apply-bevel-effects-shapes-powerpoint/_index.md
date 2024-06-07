---
title: Applicare effetti smussati sulle forme in PowerPoint
linktitle: Applicare effetti smussati sulle forme in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come applicare effetti smussati alle forme in PowerPoint utilizzando Aspose.Slides per Java con la nostra guida passo passo. Migliora le tue presentazioni.
type: docs
weight: 13
url: /it/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/
---
## introduzione
Creare presentazioni visivamente accattivanti è fondamentale per catturare e mantenere l'attenzione del pubblico. L'aggiunta di effetti smussati alle forme può migliorare l'estetica generale delle tue diapositive, facendo risaltare la tua presentazione. In questo tutorial ti guideremo attraverso il processo di applicazione degli effetti smussati alle forme in PowerPoint utilizzando Aspose.Slides per Java. Che tu sia uno sviluppatore che desidera automatizzare la creazione di presentazioni o semplicemente qualcuno che ama armeggiare con il design, questa guida fa al caso tuo.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
-  Java Development Kit (JDK): assicurati di avere JDK installato. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides per Java Library: scarica la libreria da[Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
- IDE (ambiente di sviluppo integrato): utilizza qualsiasi IDE di tua scelta, come IntelliJ IDEA, Eclipse o NetBeans.
-  Licenza Aspose: per utilizzare Aspose.Slides senza limitazioni, ottenere una licenza da[Aspose l'acquisto](https://purchase.aspose.com/buy) o prendi un[licenza temporanea](https://purchase.aspose.com/temporary-license/) Per la valutazione.
## Importa pacchetti
Innanzitutto, devi importare i pacchetti necessari per lavorare con Aspose.Slides nel tuo progetto Java. Ecco come puoi farlo:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
```
## Passaggio 1: imposta il tuo progetto
 Prima di iniziare a scrivere codice, assicurati che il tuo progetto sia impostato correttamente. Includi la libreria Aspose.Slides nel percorso di creazione del tuo progetto. Se stai utilizzando Maven, aggiungi la seguente dipendenza al tuo file`pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## Passaggio 2: crea una presentazione
 Per iniziare a lavorare con Aspose.Slides, è necessario creare un'istanza di`Presentation` classe. Questa classe rappresenta un file PowerPoint.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla prima diapositiva
Dopo aver creato una presentazione, accedi alla prima diapositiva in cui aggiungerai e manipolerai le forme.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungi una forma alla diapositiva
Ora aggiungi una forma alla diapositiva. In questo esempio aggiungeremo un'ellisse.
```java
// Aggiungi una forma alla diapositiva
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.getFillFormat().setFillType(FillType.Solid);
shape.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
ILineFillFormat format = shape.getLineFormat().getFillFormat();
format.setFillType(FillType.Solid);
format.getSolidFillColor().setColor(Color.ORANGE);
shape.getLineFormat().setWidth(2.0);
```
## Passaggio 5: applica gli effetti smussati alla forma
Successivamente, applica gli effetti smussati alla forma per conferirle un aspetto tridimensionale.
```java
// Imposta le proprietà ThreeDFormat della forma
shape.getThreeDFormat().setDepth((short) 4);
shape.getThreeDFormat().getBevelTop().setBevelType(BevelPresetType.Circle);
shape.getThreeDFormat().getBevelTop().setHeight(6);
shape.getThreeDFormat().getBevelTop().setWidth(6);
shape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.OrthographicFront);
shape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.ThreePt);
shape.getThreeDFormat().getLightRig().setDirection(LightingDirection.Top);
```
## Passaggio 6: salva la presentazione
Infine, salva la presentazione come file PPTX nella directory specificata.
```java
// Scrivi la presentazione come file PPTX
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## Passaggio 7: smaltire l'oggetto della presentazione
 Per liberare risorse, assicurarsi sempre che il file`Presentation` l'oggetto venga smaltito correttamente.
```java
if (pres != null) pres.dispose();
```
## Conclusione
 L'applicazione di effetti smussati alle forme nelle presentazioni PowerPoint utilizzando Aspose.Slides per Java è un processo semplice che può migliorare in modo significativo l'attrattiva visiva delle tue diapositive. Seguendo i passaggi descritti in questa guida, puoi creare facilmente presentazioni professionali e coinvolgenti. Ricordati di esplorare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/) per informazioni più dettagliate e funzionalità avanzate.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API che consente agli sviluppatori di creare, modificare e gestire le presentazioni di PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides per Java gratuitamente?
 Aspose.Slides offre una prova gratuita da cui puoi scaricare[Qui](https://releases.aspose.com/). Per usufruire delle funzionalità complete è necessario acquistare una licenza.
### Quali tipi di forme posso aggiungere alle mie diapositive?
Puoi aggiungere varie forme come rettangoli, ellissi, linee e forme personalizzate utilizzando Aspose.Slides per Java.
### È possibile applicare altri effetti 3D oltre allo smusso?
Sì, Aspose.Slides per Java ti consente di applicare vari effetti 3D, inclusi profondità, illuminazione ed effetti della fotocamera.
### Dove posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto dalla comunità Aspose e dal team di supporto sul loro[Forum di assistenza](https://forum.aspose.com/c/slides/11).