---
"description": "Scopri come collegare le forme in PowerPoint usando Aspose.Slides per Java. Automatizza le tue presentazioni senza sforzo."
"linktitle": "Collega le forme utilizzando i siti di connessione in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Collega le forme utilizzando i siti di connessione in PowerPoint"
"url": "/it/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Collega le forme utilizzando i siti di connessione in PowerPoint

## Introduzione
In questo tutorial, esploreremo come connettere le forme utilizzando i punti di connessione in PowerPoint con Aspose.Slides per Java. Questa potente libreria ci permette di manipolare programmaticamente le presentazioni di PowerPoint, rendendo operazioni come la connessione di forme fluide ed efficienti.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. Puoi scaricarlo e installarlo da [sito web](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides per Java: Scarica e installa Aspose.Slides per Java da [pagina di download](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): scegli un IDE per lo sviluppo Java, come IntelliJ IDEA, Eclipse o NetBeans.

## Importa pacchetti
Per iniziare, importa i pacchetti necessari nel tuo progetto Java:
```java
import com.aspose.slides.*;

```
## Passaggio 1: accesso alla raccolta di forme
Accedi alla raccolta di forme per la diapositiva selezionata:
```java
// Percorso verso la directory dei documenti.                    
String dataDir = "Your Document Directory";
// Crea un'istanza della classe Presentazione che rappresenta il file PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Passaggio 2: aggiunta della forma del connettore
Aggiungere una forma di connettore alla raccolta di forme diapositiva:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Passaggio 3: aggiunta di forme automatiche
Aggiungi forme automatiche come ellisse e rettangolo:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Fase 4: Unire le forme ai connettori
Unisci le forme al connettore:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Passaggio 5: impostazione dell'indice del sito di connessione
Imposta l'indice del sito di connessione desiderato per le forme:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusione
In questo tutorial, abbiamo imparato come connettere le forme utilizzando i punti di connessione in PowerPoint con Aspose.Slides per Java. Grazie a queste conoscenze, ora puoi automatizzare e personalizzare le tue presentazioni PowerPoint con facilità.
## Domande frequenti
### Aspose.Slides per Java può essere utilizzato per altre attività di manipolazione di PowerPoint?
Sì, Aspose.Slides per Java offre un'ampia gamma di funzionalità per creare, modificare e convertire presentazioni PowerPoint.
### Aspose.Slides per Java è gratuito?
Aspose.Slides per Java è una libreria commerciale, ma puoi esplorarne le funzionalità con una prova gratuita. Visita [Qui](https://releases.aspose.com/) per iniziare.
### Posso ricevere assistenza se riscontro problemi durante l'utilizzo di Aspose.Slides per Java?
Sì, puoi ottenere supporto dai forum della community Aspose [Qui](https://forum.aspose.com/c/slides/11).
### Sono disponibili licenze temporanee per Aspose.Slides per Java?
Sì, sono disponibili licenze temporanee per scopi di test e valutazione. Puoi ottenerne una [Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso acquistare una licenza per Aspose.Slides per Java?
È possibile acquistare una licenza dal sito web di Aspose [Qui](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}