---
title: Aggiungi nodi in posizioni specifiche in SmartArt utilizzando Java
linktitle: Aggiungi nodi in posizioni specifiche in SmartArt utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. Crea presentazioni dinamiche senza sforzo.
weight: 16
url: /it/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungi nodi in posizioni specifiche in SmartArt utilizzando Java

## introduzione
In questo tutorial ti guideremo attraverso il processo di aggiunta di nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. SmartArt è una funzionalità di PowerPoint che consente di creare diagrammi e grafici visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul tuo sistema.
2.  Aspose.Slides per la libreria Java scaricata. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
3. Conoscenza base del linguaggio di programmazione Java.

## Importa pacchetti
Innanzitutto, importiamo i pacchetti necessari nel nostro codice Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Passaggio 1: crea un'istanza di presentazione
Inizia creando un'istanza della classe Presentation:
```java
Presentation pres = new Presentation();
```
## Passaggio 2: accedi alla diapositiva della presentazione
Accedi alla diapositiva in cui desideri aggiungere la SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 3: aggiungi la forma SmartArt
Aggiungi una forma SmartArt alla diapositiva:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Passaggio 4: accedi al nodo SmartArt
Accedi al nodo SmartArt all'indice desiderato:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Passaggio 5: aggiungi un nodo figlio in una posizione specifica
Aggiungi un nuovo nodo figlio in una posizione specifica nel nodo genitore:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Passaggio 6: aggiungi testo al nodo
Imposta il testo per il nodo appena aggiunto:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Passaggio 7: salva la presentazione
Salva la presentazione modificata:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial hai imparato come aggiungere nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. Seguendo questi passaggi è possibile manipolare le forme SmartArt a livello di codice per creare presentazioni dinamiche.
## Domande frequenti
### Posso aggiungere più nodi contemporaneamente?
Sì, puoi aggiungere più nodi a livello di codice eseguendo l'iterazione sulle posizioni desiderate.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta vari formati PowerPoint, garantendo la compatibilità con la maggior parte delle versioni.
### Posso personalizzare l'aspetto dei nodi SmartArt?
Sì, puoi personalizzare l'aspetto dei nodi, incluse dimensioni, colore e stile.
### Aspose.Slides offre supporto per altri linguaggi di programmazione?
Sì, Aspose.Slides fornisce librerie per più linguaggi di programmazione, inclusi .NET e Python.
### È disponibile una versione di prova per Aspose.Slides?
 Sì, puoi scaricare una versione di prova gratuita da[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
