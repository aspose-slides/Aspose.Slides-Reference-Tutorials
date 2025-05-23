---
"description": "Scopri come applicare effetti smussati alle forme in PowerPoint utilizzando Aspose.Slides per Java con la nostra guida passo passo. Migliora le tue presentazioni."
"linktitle": "Applicare effetti smussati alle forme in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Applicare effetti smussati alle forme in PowerPoint"
"url": "/it/java/java-powerpoint-animation-shape-manipulation/apply-bevel-effects-shapes-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Applicare effetti smussati alle forme in PowerPoint

## Introduzione
Creare presentazioni visivamente accattivanti è fondamentale per catturare e mantenere l'attenzione del pubblico. L'aggiunta di effetti smussati alle forme può migliorare l'estetica complessiva delle diapositive, rendendo la presentazione unica. In questo tutorial, ti guideremo attraverso il processo di applicazione di effetti smussati alle forme in PowerPoint utilizzando Aspose.Slides per Java. Che tu sia uno sviluppatore che desidera automatizzare la creazione di presentazioni o semplicemente qualcuno che ama sperimentare con il design, questa guida ti aiuterà.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di avere i seguenti prerequisiti:
- Java Development Kit (JDK): assicurati di aver installato JDK. Puoi scaricarlo da [Sito web di Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Slides per la libreria Java: scarica la libreria da [Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
- IDE (Integrated Development Environment): utilizza l'IDE che preferisci, come IntelliJ IDEA, Eclipse o NetBeans.
- Licenza Aspose: per utilizzare Aspose.Slides senza limitazioni, ottenere una licenza da [Acquisto Aspose](https://purchase.aspose.com/buy) o ottenere un [licenza temporanea](https://purchase.aspose.com/temporary-license/) per la valutazione.
## Importa pacchetti
Per prima cosa, devi importare i pacchetti necessari per lavorare con Aspose.Slides nel tuo progetto Java. Ecco come fare:
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Passaggio 1: imposta il tuo progetto
Prima di iniziare a scrivere codice, assicurati che il progetto sia configurato correttamente. Includi la libreria Aspose.Slides nel percorso di build del progetto. Se utilizzi Maven, aggiungi la seguente dipendenza al tuo `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>23.6</version>
</dependency>
```
## Passaggio 2: creare una presentazione
Per iniziare a lavorare con Aspose.Slides, è necessario creare un'istanza di `Presentation` classe. Questa classe rappresenta un file PowerPoint.
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione
Presentation pres = new Presentation();
```
## Passaggio 3: accedi alla prima diapositiva
Dopo aver creato una presentazione, accedi alla prima diapositiva in cui aggiungerai e manipolerai le forme.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungere una forma alla diapositiva
Ora aggiungi una forma alla diapositiva. In questo esempio, aggiungeremo un'ellisse.
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
## Passaggio 5: applicare effetti smussati alla forma
Successivamente, applica effetti di smussatura alla forma per conferirle un aspetto tridimensionale.
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
## Passaggio 6: Salva la presentazione
Infine, salva la presentazione come file PPTX nella directory specificata.
```java
// Scrivi la presentazione come file PPTX
pres.save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
## Passaggio 7: Eliminare l'oggetto di presentazione
Per liberare risorse, assicurati sempre che `Presentation` l'oggetto venga smaltito correttamente.
```java
if (pres != null) pres.dispose();
```
## Conclusione
Applicare effetti smussati alle forme nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java è un processo semplice che può migliorare significativamente l'aspetto visivo delle diapositive. Seguendo i passaggi descritti in questa guida, è possibile creare facilmente presentazioni professionali e accattivanti. Ricordatevi di esplorare [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/) per informazioni più dettagliate e funzionalità avanzate.
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API che consente agli sviluppatori di creare, modificare e gestire le presentazioni di PowerPoint a livello di programmazione.
### Posso utilizzare Aspose.Slides per Java gratuitamente?
Aspose.Slides offre una prova gratuita che puoi scaricare da [Qui](https://releases.aspose.com/)Per usufruire di tutte le funzionalità è necessario acquistare una licenza.
### Quali tipi di forme posso aggiungere alle mie diapositive?
Utilizzando Aspose.Slides per Java è possibile aggiungere varie forme, come rettangoli, ellissi, linee e forme personalizzate.
### È possibile applicare altri effetti 3D oltre alla smussatura?
Sì, Aspose.Slides per Java consente di applicare vari effetti 3D, tra cui effetti di profondità, di illuminazione e di telecamera.
### Dove posso ottenere supporto per Aspose.Slides per Java?
Puoi ottenere supporto dalla community Aspose e dal team di supporto su [forum di supporto](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}