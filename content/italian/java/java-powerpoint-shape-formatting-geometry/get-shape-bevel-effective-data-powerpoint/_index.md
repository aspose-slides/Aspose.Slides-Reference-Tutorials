---
title: Ottieni dati effettivi sulla smussatura della forma in PowerPoint
linktitle: Ottieni dati effettivi sulla smussatura della forma in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come recuperare dati efficaci sulla smussatura della forma in PowerPoint utilizzando Aspose.Slides per Java. Migliora le tue presentazioni con straordinari effetti visivi.
type: docs
weight: 26
url: /it/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---
## introduzione
Nelle moderne presentazioni aziendali, l’attrattiva visiva gioca un ruolo cruciale nel trasmettere le informazioni in modo efficace. Uno degli elementi che possono migliorare l'impatto visivo delle forme nelle presentazioni PowerPoint è l'effetto smussato. Aspose.Slides per Java fornisce potenti strumenti per accedere e manipolare varie proprietà delle forme, inclusi i loro effetti smussati. In questo tutorial, ti guideremo attraverso il processo di recupero dei dati effettivi della smussatura della forma utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Conoscenza di base del linguaggio di programmazione Java.
2. Java Development Kit (JDK) installato sul tuo sistema.
3.  Scaricato e installato Aspose.Slides per Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
## Importa pacchetti
Inizia importando i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;
```
## Passaggio 1: configura la directory dei documenti
Definisci il percorso della directory dei documenti in cui si trova la presentazione di PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## Passaggio 2: caricare la presentazione
Carica la presentazione di PowerPoint utilizzando la libreria Aspose.Slides:
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## Passaggio 3: recuperare i dati effettivi dello smusso
Accedi ai dati di smussatura effettivi della forma:
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## Passaggio 4: stampa delle proprietà della smussatura
Stampa le proprietà di rilievo della faccia superiore della forma effettiva:
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## Conclusione
In questo tutorial, abbiamo dimostrato come recuperare dati efficaci sulla smussatura della forma in PowerPoint utilizzando Aspose.Slides per Java. Seguendo questi passaggi, puoi accedere e manipolare facilmente varie proprietà delle forme per migliorare l'attrattiva visiva delle tue presentazioni.
## Domande frequenti
### Posso applicare effetti smussati a più forme contemporaneamente?
Sì, puoi scorrere le forme in una diapositiva e applicare effetti smussati secondo necessità.
### Aspose.Slides supporta altri effetti 3D oltre allo smusso?
Sì, Aspose.Slides fornisce un'ampia gamma di effetti 3D che puoi applicare alle forme nelle presentazioni di PowerPoint.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Aspose.Slides garantisce la compatibilità con varie versioni di PowerPoint, consentendoti di lavorare senza problemi in diversi ambienti.
### Posso personalizzare ulteriormente le proprietà dell'effetto smusso?
Assolutamente, hai il pieno controllo sulle proprietà dell'effetto smussato e puoi personalizzarle in base alle tue esigenze.
### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides?
 Puoi visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) per qualsiasi domanda, supporto o risorse aggiuntive.