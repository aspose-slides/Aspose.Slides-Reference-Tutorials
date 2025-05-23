---
"description": "Scopri come aggiungere un nodo assistente a SmartArt nelle presentazioni Java di PowerPoint utilizzando Aspose.Slides. Migliora le tue capacità di editing in PowerPoint."
"linktitle": "Aggiungi il nodo Assistente a SmartArt in Java PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungi il nodo Assistente a SmartArt in Java PowerPoint"
"url": "/it/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi il nodo Assistente a SmartArt in Java PowerPoint

## Introduzione
In questo tutorial ti guideremo attraverso il processo di aggiunta di un nodo assistente a SmartArt nelle presentazioni Java PowerPoint utilizzando Aspose.Slides.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. Puoi scaricare e installare la versione più recente del JDK da [Qui](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides per Java: scarica e installa la libreria Aspose.Slides per Java da [questo collegamento](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo codice Java:
```java
import com.aspose.slides.*;
```
## Passaggio 1: impostare la presentazione
Inizia creando un'istanza di Presentazione utilizzando il percorso del file PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Fase 2: attraversare le forme
Esplora ogni forma all'interno della prima diapositiva della presentazione:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Passaggio 3: verifica la presenza di forme SmartArt
Controlla se la forma è di tipo SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Passaggio 4: spostarsi tra i nodi SmartArt
Attraversa tutti i nodi della forma SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Passaggio 5: verifica del nodo assistente
Controlla se il nodo è un nodo assistente:
```java
if (node.isAssistant())
```
## Passaggio 6: impostare il nodo Assistente su Normale
Se il nodo è un nodo assistente, impostalo come nodo normale:
```java
node.setAssistant(false);
```
## Passaggio 7: Salva la presentazione
Salva la presentazione modificata:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Conclusione
Congratulazioni! Hai aggiunto correttamente un nodo assistente a SmartArt nella tua presentazione Java di PowerPoint utilizzando Aspose.Slides.

## Domande frequenti
### Posso aggiungere più nodi assistente a uno SmartArt nella presentazione?
Sì, puoi aggiungere più nodi assistente ripetendo il processo per ciascun nodo.
### Questo tutorial funziona sia per PowerPoint sia per i modelli di PowerPoint?
Sì, puoi applicare questo tutorial sia alle presentazioni che ai modelli di PowerPoint.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta le versioni di PowerPoint dalla 97 alla 2003 fino alla versione più recente.
### Posso personalizzare l'aspetto del nodo assistente?
Sì, puoi personalizzare l'aspetto utilizzando varie proprietà e metodi forniti da Aspose.Slides.
### Esiste un limite al numero di nodi in uno SmartArt?
SmartArt in PowerPoint supporta un gran numero di nodi, ma è consigliabile mantenerlo su un numero ragionevole per una migliore leggibilità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}