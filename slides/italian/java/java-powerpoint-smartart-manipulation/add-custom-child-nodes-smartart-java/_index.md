---
"description": "Scopri come aggiungere nodi figlio personalizzati a SmartArt nelle presentazioni di PowerPoint utilizzando Java con Aspose.Slides. Migliora le tue diapositive con grafica professionale senza sforzo."
"linktitle": "Aggiungere nodi figlio personalizzati in SmartArt utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere nodi figlio personalizzati in SmartArt utilizzando Java"
"url": "/it/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere nodi figlio personalizzati in SmartArt utilizzando Java

## Introduzione
SmartArt è una potente funzionalità di PowerPoint che consente agli utenti di creare grafici dall'aspetto professionale in modo rapido e semplice. In questo tutorial, impareremo come aggiungere nodi figlio personalizzati a SmartArt utilizzando Java con Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema.
2. Aspose.Slides per Java: Scarica e installa Aspose.Slides per Java da [Qui](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: caricare la presentazione
Carica la presentazione di PowerPoint in cui desideri aggiungere nodi figlio personalizzati allo SmartArt:
```java
String dataDir = "Your Document Directory";
// Carica la presentazione desiderata
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Passaggio 2: aggiungere SmartArt alla diapositiva
Ora aggiungiamo SmartArt alla diapositiva:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Passaggio 3: sposta la forma SmartArt
Spostare la forma SmartArt in una nuova posizione:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Passaggio 4: modifica la larghezza della forma
Modifica la larghezza della forma SmartArt:
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
## Passaggio 7: Salva la presentazione
Infine, salva la presentazione modificata:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial abbiamo imparato come aggiungere nodi figlio personalizzati a SmartArt utilizzando Java con Aspose.Slides. Seguendo questi passaggi, puoi migliorare le tue presentazioni con grafica personalizzata, rendendole più coinvolgenti e professionali.
## Domande frequenti
### Posso aggiungere diversi tipi di layout SmartArt utilizzando Aspose.Slides per Java?
Sì, Aspose.Slides per Java supporta vari layout SmartArt, consentendoti di scegliere quello più adatto alle tue esigenze di presentazione.
### Aspose.Slides per Java è compatibile con le diverse versioni di PowerPoint?
Aspose.Slides per Java è progettato per funzionare in modo ottimale con diverse versioni di PowerPoint, garantendo compatibilità e coerenza su tutte le piattaforme.
### Posso personalizzare l'aspetto delle forme SmartArt a livello di programmazione?
Assolutamente sì! Con Aspose.Slides per Java, puoi personalizzare a livello di programmazione l'aspetto, le dimensioni, il colore e il layout delle forme SmartArt in base alle tue preferenze di progettazione.
### Aspose.Slides per Java fornisce documentazione e supporto?
Sì, puoi trovare una documentazione completa e accedere ai forum di supporto della community sul sito web di Aspose.
### Esiste una versione di prova disponibile per Aspose.Slides per Java?
Sì, puoi scaricare una versione di prova gratuita di Aspose.Slides per Java dal sito Web per esplorare le sue funzionalità e capacità prima di effettuare un acquisto [Qui](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}