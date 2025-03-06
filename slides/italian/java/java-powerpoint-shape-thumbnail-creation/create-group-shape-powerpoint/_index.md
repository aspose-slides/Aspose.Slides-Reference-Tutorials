---
title: Crea forma di gruppo in PowerPoint
linktitle: Crea forma di gruppo in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare forme di gruppo nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Migliora l'organizzazione e l'attrattiva visiva senza sforzo.
weight: 11
url: /it/java/java-powerpoint-shape-thumbnail-creation/create-group-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
Nelle presentazioni moderne, incorporare elementi visivamente accattivanti e ben strutturati è fondamentale per trasmettere efficacemente le informazioni. Le forme di gruppo in PowerPoint consentono di organizzare più forme in una singola unità, facilitando la manipolazione e la formattazione più semplici. Aspose.Slides per Java fornisce potenti funzionalità per creare e manipolare forme di gruppo a livello di codice, offrendo flessibilità e controllo sul design della presentazione.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di aver impostato i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere JDK installato sul tuo sistema.
2. Aspose.Slides per Java Library: scarica e includi la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): scegli un IDE Java di tua preferenza, come IntelliJ IDEA o Eclipse.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari per utilizzare Aspose.Slides per le funzionalità Java:
```java
import com.aspose.slides.*;

```
## Passaggio 1: configura il tuo ambiente
 Assicurati di avere una directory impostata per il tuo progetto in cui puoi creare e salvare presentazioni PowerPoint. Sostituire`"Your Document Directory"` con il percorso della directory desiderata.
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: istanziare la lezione di presentazione
 Crea un'istanza di`Presentation` classe per inizializzare una nuova presentazione di PowerPoint.
```java
Presentation pres = new Presentation();
```
## Passaggio 3: ottieni le raccolte Slide e Shape
Recupera la prima diapositiva dalla presentazione e accedi alla sua raccolta di forme.
```java
ISlide sld = pres.getSlides().get_Item(0);
IShapeCollection slideShapes = sld.getShapes();
```
## Passaggio 4: aggiungi una forma di gruppo
 Aggiungi una forma di gruppo alla diapositiva utilizzando`addGroupShape()` metodo.
```java
IGroupShape groupShape = slideShapes.addGroupShape();
```
## Passaggio 5: aggiungi forme all'interno della forma del gruppo
Popolare la forma del gruppo aggiungendo forme individuali al suo interno.
```java
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.getShapes().addAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```
## Passaggio 6: personalizzare la cornice della forma del gruppo
Facoltativamente, personalizza la cornice della forma del gruppo in base alle tue preferenze.
```java
groupShape.setFrame(new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0));
```
## Passaggio 7: salva la presentazione
Salva la presentazione di PowerPoint nella directory specificata.
```java
pres.save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

## Conclusione
La creazione di forme di gruppo nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Java offre un approccio semplificato all'organizzazione e alla strutturazione dei contenuti. Seguendo la guida passo passo sopra descritta, puoi incorporare in modo efficiente le forme di gruppo nelle tue presentazioni, migliorando l'attrattiva visiva e trasmettendo le informazioni in modo efficace.

## Domande frequenti
### Posso nidificare le forme di gruppo all'interno di altre forme di gruppo?
Sì, Aspose.Slides per Java consente di annidare forme di gruppo l'una nell'altra per creare strutture gerarchiche complesse.
### Aspose.Slides per Java è compatibile con diverse versioni di PowerPoint?
Aspose.Slides per Java genera presentazioni PowerPoint compatibili con varie versioni, garantendo la compatibilità incrociata.
### Aspose.Slides per Java supporta l'aggiunta di immagini alle forme di gruppo?
Assolutamente, puoi aggiungere immagini insieme ad altre forme per raggruppare forme utilizzando Aspose.Slides per Java.
### Esistono limitazioni al numero di forme all'interno di una forma di gruppo?
Aspose.Slides per Java non impone limitazioni rigorose al numero di forme che possono essere aggiunte a una forma di gruppo.
### Posso applicare animazioni alle forme di gruppo utilizzando Aspose.Slides per Java?
Sì, Aspose.Slides per Java fornisce un supporto completo per l'applicazione di animazioni alle forme di gruppo, consentendo presentazioni dinamiche.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
