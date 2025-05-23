---
"description": "Scopri come collegare le forme utilizzando i connettori nelle presentazioni di PowerPoint con Aspose.Slides per Java. Tutorial passo passo per principianti."
"linktitle": "Collega le forme utilizzando i connettori in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Collega le forme utilizzando i connettori in PowerPoint"
"url": "/it/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Collega le forme utilizzando i connettori in PowerPoint

## Introduzione
In questo tutorial, esploreremo come collegare le forme utilizzando i connettori nelle presentazioni di PowerPoint con l'aiuto di Aspose.Slides per Java. Segui queste istruzioni passo passo per collegare le forme in modo efficiente e creare diapositive visivamente accattivanti.
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Conoscenza di base del linguaggio di programmazione Java.
- Installato Java Development Kit (JDK) sul tuo sistema.
- Scaricato e installato Aspose.Slides per Java. Se non l'hai ancora installato, puoi scaricarlo da [Qui](https://releases.aspose.com/slides/java/).
- Un editor di codice come Eclipse o IntelliJ IDEA.

## Importa pacchetti
Per prima cosa, importa i pacchetti necessari per lavorare con Aspose.Slides nel tuo progetto Java.
```java
import com.aspose.slides.*;

```
## Passaggio 1: creare un'istanza della classe di presentazione
Istanziare il `Presentation` classe, che rappresenta il file PPTX su cui stai lavorando.
```java
// Percorso verso la directory dei documenti.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Passaggio 2: accedi alla raccolta di forme
Accedi alla raccolta di forme per la diapositiva selezionata in cui desideri aggiungere forme e connettori.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Passaggio 3: aggiungere forme
Aggiungi le forme desiderate alla diapositiva. In questo esempio, aggiungeremo un'ellisse e un rettangolo.
```java
// Aggiungi forma automatica Ellisse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Aggiungi forma automatica Rettangolo
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Passaggio 4: aggiungere il connettore
Aggiungere una forma connettore alla raccolta di forme diapositiva.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Passaggio 5: unire le forme ai connettori
Collega le forme al connettore.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Passaggio 6: reindirizzare il connettore
Chiama reroute per impostare automaticamente il percorso più breve tra le forme.
```java
connector.reroute();
```
## Passaggio 7: Salva la presentazione
Salvare la presentazione dopo aver collegato le forme tramite i connettori.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Infine, non dimenticare di eliminare l'oggetto Presentazione.
```java
if (input != null) input.dispose();
```
Ora hai collegato correttamente le forme utilizzando i connettori in PowerPoint utilizzando Aspose.Slides per Java.

## Conclusione
In questo tutorial abbiamo imparato come collegare le forme utilizzando i connettori nelle presentazioni PowerPoint con Aspose.Slides per Java. Seguendo questi semplici passaggi, puoi migliorare le tue presentazioni con diagrammi e diagrammi di flusso visivamente accattivanti.
## Domande frequenti
### Posso personalizzare l'aspetto dei connettori in Aspose.Slides per Java?
Sì, puoi personalizzare varie proprietà dei connettori, come colore, stile della linea e spessore, per adattarli alle tue esigenze di presentazione.
### Aspose.Slides per Java è compatibile con tutte le versioni di PowerPoint?
Aspose.Slides per Java supporta vari formati di PowerPoint, tra cui PPTX, PPT e ODP.
### Posso collegare più di due forme con un singolo connettore?
Sì, puoi connettere più forme utilizzando i connettori complessi forniti da Aspose.Slides per Java.
### Aspose.Slides per Java supporta l'aggiunta di testo alle forme?
Certamente, puoi aggiungere facilmente testo a forme e connettori a livello di programmazione utilizzando Aspose.Slides per Java.
### Esiste un forum della community o un canale di supporto disponibile per gli utenti di Aspose.Slides per Java?
Sì, puoi trovare risorse utili, porre domande e interagire con altri utenti sul forum Aspose.Slides [Qui](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}