---
"description": "Scopri come aggiungere nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. Crea presentazioni dinamiche senza sforzo."
"linktitle": "Aggiungere nodi in una posizione specifica in SmartArt utilizzando Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Aggiungere nodi in una posizione specifica in SmartArt utilizzando Java"
"url": "/it/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aggiungere nodi in una posizione specifica in SmartArt utilizzando Java

## Introduzione
In questo tutorial, ti guideremo attraverso il processo di aggiunta di nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. SmartArt è una funzionalità di PowerPoint che consente di creare diagrammi e grafici visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK) installato sul sistema.
2. Scaricata la libreria Aspose.Slides per Java. Puoi scaricarla da [Qui](https://releases.aspose.com/slides/java/).
3. Conoscenza di base del linguaggio di programmazione Java.

## Importa pacchetti
Per prima cosa, importiamo i pacchetti necessari nel nostro codice Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Passaggio 1: creare un'istanza di presentazione
Iniziamo creando un'istanza della classe Presentation:
```java
Presentation pres = new Presentation();
```
## Passaggio 2: accedi alla diapositiva della presentazione
Accedi alla diapositiva in cui desideri aggiungere lo SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 3: aggiungi forma SmartArt
Aggiungere una forma SmartArt alla diapositiva:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Passaggio 4: accedi al nodo SmartArt
Accedi al nodo SmartArt all'indice desiderato:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Passaggio 5: aggiungere il nodo figlio in una posizione specifica
Aggiungere un nuovo nodo figlio in una posizione specifica nel nodo padre:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Passaggio 6: aggiungere testo al nodo
Imposta il testo per il nodo appena aggiunto:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Passaggio 7: Salva la presentazione
Salva la presentazione modificata:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Conclusione
In questo tutorial, hai imparato come aggiungere nodi in posizioni specifiche in SmartArt utilizzando Java con Aspose.Slides. Seguendo questi passaggi, puoi manipolare le forme SmartArt a livello di codice per creare presentazioni dinamiche.
## Domande frequenti
### Posso aggiungere più nodi contemporaneamente?
Sì, è possibile aggiungere più nodi a livello di programmazione, iterando sulle posizioni desiderate.
### Aspose.Slides è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides supporta vari formati PowerPoint, garantendo la compatibilità con la maggior parte delle versioni.
### Posso personalizzare l'aspetto dei nodi SmartArt?
Sì, puoi personalizzare l'aspetto dei nodi, comprese le dimensioni, il colore e lo stile.
### Aspose.Slides supporta altri linguaggi di programmazione?
Sì, Aspose.Slides fornisce librerie per diversi linguaggi di programmazione, tra cui .NET e Python.
### Esiste una versione di prova disponibile per Aspose.Slides?
Sì, puoi scaricare una versione di prova gratuita da [Qui](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}