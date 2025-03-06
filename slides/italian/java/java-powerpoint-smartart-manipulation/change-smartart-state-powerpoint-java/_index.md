---
title: Cambia lo stato SmartArt in PowerPoint con Java
linktitle: Cambia lo stato SmartArt in PowerPoint con Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come modificare gli stati SmartArt nelle presentazioni di PowerPoint utilizzando Java e Aspose.Slides. Migliora le tue capacità di automazione delle presentazioni.
weight: 21
url: /it/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
In questo tutorial imparerai come manipolare oggetti SmartArt nelle presentazioni di PowerPoint utilizzando Java con la libreria Aspose.Slides. SmartArt è una potente funzionalità di PowerPoint che ti consente di creare diagrammi e grafica visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1.  Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides per Java: scarica e installa la libreria Aspose.Slides per Java da[sito web](https://releases.aspose.com/slides/java/).

## Importa pacchetti
Per iniziare a lavorare con Aspose.Slides nel tuo progetto Java, importa i pacchetti necessari:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
Ora suddividiamo il codice di esempio fornito in più passaggi:
## Passaggio 1: inizializzare l'oggetto di presentazione
```java
Presentation presentation = new Presentation();
```
 Qui ne creiamo uno nuovo`Presentation` oggetto, che rappresenta una presentazione di PowerPoint.
## Passaggio 2: aggiungi oggetto SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 Questo passaggio aggiunge un oggetto SmartArt alla prima diapositiva della presentazione. Specifichiamo la posizione e le dimensioni dell'oggetto SmartArt, nonché il tipo di layout (in questo caso,`BasicProcess`).
## Passaggio 3: imposta lo stato SmartArt
```java
smart.setReversed(true);
```
Qui impostiamo lo stato dell'oggetto SmartArt. In questo esempio, stiamo invertendo la direzione della SmartArt.
## Passaggio 4: controlla lo stato SmartArt
```java
boolean flag = smart.isReversed();
```
 Possiamo anche controllare lo stato corrente dell'oggetto SmartArt. Questa riga recupera se la SmartArt è invertita o meno e la memorizza nel file`flag` variabile.
## Passaggio 5: salva la presentazione
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
Infine, salviamo la presentazione modificata in una posizione specificata sul disco.

## Conclusione
In questo tutorial, abbiamo imparato come modificare lo stato degli oggetti SmartArt nelle presentazioni di PowerPoint utilizzando Java e la libreria Aspose.Slides. Con questa conoscenza, puoi creare presentazioni dinamiche e coinvolgenti a livello di programmazione.
## Domande frequenti
### Posso modificare altre proprietà di SmartArt utilizzando Aspose.Slides per Java?
Sì, puoi modificare vari aspetti degli oggetti SmartArt, come colori, stili e layout, utilizzando Aspose.Slides.
### Aspose.Slides è compatibile con diverse versioni di PowerPoint?
Sì, Aspose.Slides supporta le presentazioni PowerPoint in diverse versioni, garantendo compatibilità e integrazione perfetta.
### Posso creare layout SmartArt personalizzati con Aspose.Slides?
Assolutamente! Aspose.Slides fornisce API per creare layout SmartArt personalizzati su misura per le tue esigenze specifiche.
### Aspose.Slides offre supporto per altri formati di file oltre a PowerPoint?
Sì, Aspose.Slides supporta un'ampia gamma di formati di file, inclusi PPTX, PPT, PDF e altri.
### Esiste un forum della community in cui posso ottenere aiuto con le domande relative ad Aspose.Slides?
 Sì, puoi visitare il forum Aspose.Slides all'indirizzo[Qui](https://forum.aspose.com/c/slides/11) per assistenza e discussioni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
