---
title: Aggiungi nodi secondari personalizzati in SmartArt utilizzando Java
linktitle: Aggiungi nodi secondari personalizzati in SmartArt utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere nodi figlio personalizzati a SmartArt nelle presentazioni di PowerPoint utilizzando Java con Aspose.Slides. Migliora le tue diapositive con grafica professionale senza sforzo.
type: docs
weight: 11
url: /it/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---
## introduzione
SmartArt è una potente funzionalità di PowerPoint che consente agli utenti di creare grafica dall'aspetto professionale in modo rapido e semplice. In questo tutorial impareremo come aggiungere nodi figlio personalizzati a SmartArt utilizzando Java con Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
2.  Aspose.Slides per Java: scarica e installa Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: caricare la presentazione
Carica la presentazione di PowerPoint in cui desideri aggiungere nodi secondari personalizzati alla SmartArt:
```java
String dataDir = "Your Document Directory";
// Carica la presentazione desiderata
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Passaggio 2: aggiungi SmartArt alla diapositiva
Ora aggiungiamo SmartArt alla diapositiva:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Passaggio 3: sposta la forma SmartArt
Sposta la forma SmartArt in una nuova posizione:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Passaggio 4: modifica la larghezza della forma
Modificare la larghezza della forma SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Passaggio 5: modifica l'altezza della forma
Modificare l'altezza della forma SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Passaggio 6: ruotare la forma
Ruota la forma SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Passaggio 7: salva la presentazione
Infine, salva la presentazione modificata:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, abbiamo imparato come aggiungere nodi figlio personalizzati a SmartArt utilizzando Java con Aspose.Slides. Seguendo questi passaggi potrai arricchire le tue presentazioni con una grafica personalizzata, rendendole più accattivanti e professionali.
## Domande frequenti
### Posso aggiungere diversi tipi di layout SmartArt utilizzando Aspose.Slides per Java?
Sì, Aspose.Slides per Java supporta vari layout SmartArt, permettendoti di scegliere quello che meglio si adatta alle tue esigenze di presentazione.
### Aspose.Slides per Java è compatibile con diverse versioni di PowerPoint?
Aspose.Slides per Java è progettato per funzionare perfettamente con diverse versioni di PowerPoint, garantendo compatibilità e coerenza tra le piattaforme.
### Posso personalizzare l'aspetto delle forme SmartArt a livello di codice?
Assolutamente! Con Aspose.Slides per Java, puoi personalizzare a livello di codice l'aspetto, le dimensioni, il colore e il layout delle forme SmartArt in base alle tue preferenze di progettazione.
### Aspose.Slides per Java fornisce documentazione e supporto?
Sì, puoi trovare documentazione completa e accesso ai forum di supporto della comunità sul sito Web Aspose.
### È disponibile una versione di prova per Aspose.Slides per Java?
 Sì, puoi scaricare una versione di prova gratuita di Aspose.Slides per Java dal sito Web per esplorarne le caratteristiche e le capacità prima di effettuare un acquisto[Qui](https://releases.aspose.com/slides/java/).