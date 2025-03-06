---
title: Aggiungi il nodo assistente a SmartArt in Java PowerPoint
linktitle: Aggiungi il nodo assistente a SmartArt in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere un nodo assistente a SmartArt nelle presentazioni Java PowerPoint utilizzando Aspose.Slides. Migliora le tue capacità di editing di PowerPoint.
type: docs
weight: 17
url: /it/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---
## introduzione
In questo tutorial, ti guideremo attraverso il processo di aggiunta di un nodo assistente a SmartArt nelle presentazioni PowerPoint Java utilizzando Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1.  Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. È possibile scaricare e installare l'ultimo JDK da[Qui](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides per Java: scarica e installa la libreria Aspose.Slides per Java da[questo link](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per cominciare, importa i pacchetti necessari nel tuo codice Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: impostare la presentazione
Inizia creando un'istanza di presentazione utilizzando il percorso del tuo file PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Passaggio 2: attraversamento delle forme
Attraversa ogni forma all'interno della prima diapositiva della presentazione:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Passaggio 3: verificare la presenza di forme SmartArt
Controlla se la forma è di tipo SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Passaggio 4: attraversa i nodi SmartArt
Attraversa tutti i nodi della forma SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Passaggio 5: controlla il nodo assistente
Controlla se il nodo è un nodo assistente:
```java
if (node.isAssistant())
```
## Passaggio 6: imposta Nodo Assistente su Normale
Se il nodo è un nodo assistente, impostalo su un nodo normale:
```java
node.setAssistant(false);
```
## Passaggio 7: salva la presentazione
Salva la presentazione modificata:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai aggiunto con successo un nodo assistente a SmartArt nella presentazione Java PowerPoint utilizzando Aspose.Slides.

## Domande frequenti
### Posso aggiungere più nodi assistente a una SmartArt nella presentazione?
Sì, puoi aggiungere più nodi assistente ripetendo la procedura per ciascun nodo.
### Questo tutorial funziona sia per i modelli PowerPoint che per quelli PowerPoint?
Sì, puoi applicare questo tutorial sia alle presentazioni che ai modelli PowerPoint.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta le versioni di PowerPoint dal 97-2003 all'ultima versione.
### Posso personalizzare l'aspetto del nodo assistente?
Sì, puoi personalizzare l'aspetto utilizzando varie proprietà e metodi forniti da Aspose.Slides.
### Esiste un limite al numero di nodi in una SmartArt?
SmartArt in PowerPoint supporta un numero elevato di nodi, ma è consigliabile mantenerlo ragionevole per una migliore leggibilità.