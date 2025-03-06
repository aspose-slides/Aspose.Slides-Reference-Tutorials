---
title: Connetti forme utilizzando connettori in PowerPoint
linktitle: Connetti forme utilizzando connettori in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come collegare le forme utilizzando i connettori nelle presentazioni di PowerPoint con Aspose.Slides per Java. Tutorial passo passo per principianti.
type: docs
weight: 18
url: /it/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---
## introduzione
In questo tutorial esploreremo come connettere le forme utilizzando i connettori nelle presentazioni di PowerPoint con l'aiuto di Aspose.Slides per Java. Segui queste istruzioni dettagliate per collegare in modo efficiente le forme e creare diapositive visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
- Conoscenza base del linguaggio di programmazione Java.
- Java Development Kit (JDK) installato sul tuo sistema.
-  Scaricato e configurato Aspose.Slides per Java. Se non lo hai ancora installato, puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Un editor di codice come Eclipse o IntelliJ IDEA.

## Importa pacchetti
Innanzitutto, importa i pacchetti necessari per lavorare con Aspose.Slides nel tuo progetto Java.
```java
import com.aspose.slides.*;

```
## Passaggio 1: istanziare la lezione di presentazione
 Istanziare il`Presentation`class, che rappresenta il file PPTX su cui stai lavorando.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Passaggio 2: accedere alla raccolta di forme
Accedi alla raccolta di forme per la diapositiva selezionata a cui desideri aggiungere forme e connettori.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Passaggio 3: aggiungi forme
Aggiungi le forme richieste alla diapositiva. In questo esempio aggiungeremo un'ellisse e un rettangolo.
```java
// Aggiungi l'ellisse a forma automatica
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Aggiungi rettangolo a forma automatica
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Passaggio 4: aggiungi connettore
Aggiungi una forma connettore alla raccolta di forme diapositiva.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Passaggio 5: unisci le forme ai connettori
Collega le forme al connettore.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Passaggio 6: reindirizzare il connettore
Chiama il reindirizzamento per impostare il percorso più breve automatico tra le forme.
```java
connector.reroute();
```
## Passaggio 7: salva la presentazione
Salva la presentazione dopo aver collegato le forme utilizzando i connettori.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Infine, non dimenticare di eliminare l'oggetto Presentation.
```java
if (input != null) input.dispose();
```
Ora hai collegato con successo le forme utilizzando i connettori in PowerPoint utilizzando Aspose.Slides per Java.

## Conclusione
In questo tutorial, abbiamo imparato come collegare le forme utilizzando i connettori nelle presentazioni di PowerPoint con Aspose.Slides per Java. Seguendo questi semplici passaggi, puoi migliorare le tue presentazioni con diagrammi e diagrammi di flusso visivamente accattivanti.
## Domande frequenti
### Posso personalizzare l'aspetto dei connettori in Aspose.Slides per Java?
Sì, puoi personalizzare varie proprietà dei connettori come colore, stile della linea e spessore per adattarle alle tue esigenze di presentazione.
### Aspose.Slides per Java è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides per Java supporta vari formati PowerPoint, inclusi PPTX, PPT e ODP.
### Posso connettere più di due forme con un singolo connettore?
Sì, puoi connettere più forme utilizzando connettori complessi forniti da Aspose.Slides per Java.
### Aspose.Slides per Java offre supporto per l'aggiunta di testo alle forme?
Assolutamente, puoi aggiungere facilmente testo a forme e connettori a livello di codice utilizzando Aspose.Slides per Java.
### Esiste un forum della community o un canale di supporto disponibile per Aspose.Slides per gli utenti Java?
 Sì, puoi trovare risorse utili, porre domande e interagire con altri utenti sul forum Aspose.Slides[Qui](https://forum.aspose.com/c/slides/11).