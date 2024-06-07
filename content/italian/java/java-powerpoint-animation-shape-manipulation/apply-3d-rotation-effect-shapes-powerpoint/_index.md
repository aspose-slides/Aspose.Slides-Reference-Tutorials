---
title: Applica l'effetto di rotazione 3D sulle forme in PowerPoint
linktitle: Applica l'effetto di rotazione 3D sulle forme in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come applicare gli effetti di rotazione 3D sulle forme in PowerPoint utilizzando Aspose.Slides per Java con questo tutorial completo passo dopo passo.
type: docs
weight: 12
url: /it/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---
## introduzione
Sei pronto a portare le tue presentazioni PowerPoint al livello successivo? L'aggiunta di effetti di rotazione 3D può rendere le tue diapositive più dinamiche e coinvolgenti. Che tu sia uno sviluppatore esperto o abbia appena iniziato, questo tutorial passo passo ti mostrerà come applicare gli effetti di rotazione 3D alle forme in PowerPoint utilizzando Aspose.Slides per Java. Immergiamoci subito!
## Prerequisiti
Prima di iniziare, assicurati di avere a disposizione quanto segue:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides per Java: scarica l'ultima versione di Aspose.Slides per Java da[Link per scaricare](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse per la codifica.
4.  Una licenza valida: se non disponi di una licenza, puoi ottenerne una[licenza temporanea](https://purchase.aspose.com/temporary-license/) per provare le funzionalità.
## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari nel tuo progetto Java. Queste importazioni ti aiuteranno a gestire presentazioni e forme con Aspose.Slides.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Passaggio 1: imposta il tuo progetto
Prima di immergerti nel codice, configura l'ambiente del tuo progetto. Assicurati di aver aggiunto Aspose.Slides per Java alle dipendenze del tuo progetto.
Aggiungi Aspose.Slides al tuo progetto:
1.  Scarica i file JAR Aspose.Slides dal file[pagina di download](https://releases.aspose.com/slides/java/).
2. Aggiungi questi file JAR al percorso di compilazione del tuo progetto.
## Passaggio 2: crea una nuova presentazione PowerPoint
In questo passaggio creeremo una nuova presentazione PowerPoint.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentation
Presentation pres = new Presentation();
```
Questo frammento di codice inizializza un nuovo oggetto di presentazione in cui aggiungeremo le nostre forme.
## Passaggio 3: aggiungi una forma rettangolare
Successivamente, aggiungiamo una forma rettangolare alla prima diapositiva.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Questo codice aggiunge una forma rettangolare nella posizione e dimensione specificate sulla prima diapositiva.
## Passaggio 4: applica la rotazione 3D al rettangolo
Ora applichiamo un effetto di rotazione 3D alla forma rettangolare.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Qui impostiamo la profondità, gli angoli di rotazione della telecamera, il tipo di telecamera e il tipo di illuminazione per dare al nostro rettangolo un aspetto 3D.
## Passaggio 5: aggiungi una forma di linea
Aggiungiamo un'altra forma, questa volta una linea, alla diapositiva.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Questo codice posiziona una forma di linea sulla diapositiva.
## Passaggio 6: applicare la rotazione 3D alla linea
Infine, applicheremo un effetto di rotazione 3D alla forma della linea.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Similmente al rettangolo, impostiamo le proprietà 3D per la forma della linea.
## Passaggio 7: salva la presentazione
Dopo aver aggiunto e configurato le forme, salva la presentazione.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Questo codice salva la presentazione con il nome file specificato nel formato desiderato.
## Conclusione
Congratulazioni! Hai applicato con successo effetti di rotazione 3D alle forme in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi creare presentazioni visivamente accattivanti e dinamiche. Per ulteriori personalizzazioni e funzionalità più avanzate, fare riferimento a[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/).
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare, modificare e manipolare presentazioni PowerPoint a livello di codice.
### Posso provare Aspose.Slides per Java gratuitamente?
 Sì, puoi ottenere un[prova gratuita](https://releases.aspose.com/) o a[licenza temporanea](https://purchase.aspose.com/temporary-license/) per testare le funzionalità.
### A quali tipi di forme posso aggiungere effetti 3D in Aspose.Slides?
Puoi aggiungere effetti 3D a varie forme come rettangoli, linee, ellissi e forme personalizzate.
### Come posso ottenere supporto per Aspose.Slides per Java?
 Puoi visitare il[Forum di assistenza](https://forum.aspose.com/c/slides/11) per assistenza e per discutere eventuali problemi.
### Posso utilizzare Aspose.Slides per Java in progetti commerciali?
 Sì, ma è necessario acquistare una licenza. Puoi acquistarne uno da[pagina di acquisto](https://purchase.aspose.com/buy).