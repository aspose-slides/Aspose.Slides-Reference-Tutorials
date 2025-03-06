---
title: Modifica il testo sul nodo SmartArt utilizzando Java
linktitle: Modifica il testo sul nodo SmartArt utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiornare il testo del nodo SmartArt in PowerPoint utilizzando Java con Aspose.Slides, migliorando la personalizzazione della presentazione.
weight: 22
url: /it/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
SmartArt in PowerPoint è una potente funzionalità per creare diagrammi visivamente accattivanti. Aspose.Slides per Java fornisce un supporto completo per manipolare gli elementi SmartArt a livello di codice. In questo tutorial ti guideremo attraverso il processo di modifica del testo su un nodo SmartArt utilizzando Java.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK) installato sul tuo sistema.
- Aspose.Slides per la libreria Java scaricata e referenziata nel tuo progetto Java.
- Conoscenza di base della programmazione Java.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari per accedere alla funzionalità Aspose.Slides all'interno del tuo codice Java.
```java
import com.aspose.slides.*;
```
Suddividiamo l'esempio in più passaggi:
## Passaggio 1: inizializzare l'oggetto di presentazione
```java
Presentation presentation = new Presentation();
```
 Crea una nuova istanza di`Presentation` lezione per lavorare con una presentazione PowerPoint.
## Passaggio 2: aggiungi SmartArt alla diapositiva
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Aggiungi SmartArt alla prima diapositiva. In questo esempio, stiamo utilizzando il file`BasicCycle` disposizione.
## Passaggio 3: accedi al nodo SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Ottieni un riferimento al secondo nodo radice della SmartArt.
## Passaggio 4: imposta il testo sul nodo
```java
node.getTextFrame().setText("Second root node");
```
Imposta il testo per il nodo SmartArt selezionato.
## Passaggio 5: salva la presentazione
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Salva la presentazione modificata in una posizione specificata.

## Conclusione
In questo tutorial, abbiamo dimostrato come modificare il testo su un nodo SmartArt utilizzando Java e Aspose.Slides. Con questa conoscenza, puoi manipolare dinamicamente gli elementi SmartArt nelle tue presentazioni PowerPoint, migliorandone l'attrattiva visiva e la chiarezza.
## Domande frequenti
### Posso modificare il layout della SmartArt dopo averla aggiunta alla diapositiva?
 Sì, puoi modificare il layout accedendo al file`SmartArt.setAllNodes(LayoutType)` metodo.
### Aspose.Slides è compatibile con Java 11?
Sì, Aspose.Slides per Java è compatibile con Java 11 e versioni successive.
### Posso personalizzare l'aspetto dei nodi SmartArt a livello di codice?
Certamente, puoi modificare varie proprietà come colore, dimensione e forma utilizzando l'API Aspose.Slides.
### Aspose.Slides supporta altri tipi di layout SmartArt?
Sì, Aspose.Slides supporta un'ampia gamma di layout SmartArt, permettendoti di scegliere quello che meglio si adatta alle tue esigenze di presentazione.
### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides?
 Puoi visitare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/) per riferimenti API dettagliati ed esercitazioni. Inoltre, puoi chiedere aiuto a[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) o considera l'acquisto di a[licenza temporanea](https://purchase.aspose.com/temporary-license/) per il supporto professionale.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
