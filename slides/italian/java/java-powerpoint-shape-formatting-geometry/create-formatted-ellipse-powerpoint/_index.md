---
"description": "Scopri come creare un'ellisse formattata in PowerPoint utilizzando Aspose.Slides per Java con la nostra guida dettagliata passo dopo passo."
"linktitle": "Crea un'ellisse formattata in PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Crea un'ellisse formattata in PowerPoint"
"url": "/it/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Crea un'ellisse formattata in PowerPoint

## Introduzione
Benvenuti a questo tutorial completo sulla creazione di un'ellisse formattata in PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori di manipolare i file di PowerPoint a livello di codice. Che stiate automatizzando la generazione di diapositive o migliorando le presentazioni con forme personalizzate, questa guida vi guiderà passo passo, assicurandovi di poter aggiungere facilmente un'ellisse perfettamente formattata alle vostre diapositive. Approfondiamo e vediamo come possiamo raggiungere questo obiettivo!
## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di aver installato JDK 1.6 o versione successiva.
2. Aspose.Slides per Java: scarica l'ultima versione da [Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizzare un IDE come IntelliJ IDEA o Eclipse.
4. Conoscenza di base di Java: è richiesta familiarità con la programmazione Java.
## Importa pacchetti
Per iniziare a utilizzare Aspose.Slides, è necessario importare i pacchetti necessari. Ecco come fare:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta la directory del progetto
Per prima cosa, ti serve una directory in cui archiviare i file di PowerPoint.
### Crea directory
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Assicurati di sostituire `"Your Document Directory"` con il percorso effettivo in cui vuoi archiviare i tuoi file.
## Passaggio 2: inizializzare la presentazione
Ora, creiamo un'istanza della classe Presentation, che rappresenta il file PowerPoint.
```java
// Crea un'istanza della classe Presentazione che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: Ottieni la prima diapositiva
Ora prendi la prima diapositiva della presentazione in cui aggiungerai l'ellisse.
```java
// Ottieni la prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungere una forma ellittica
Aggiungere una forma automatica di tipo ellisse alla diapositiva.
```java
// Aggiungi forma automatica di tipo ellisse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Qui, `50, 150, 150, 50` sono le coordinate e la dimensione dell'ellisse (posizione x, posizione y, larghezza, altezza).
## Passaggio 5: applicare la formattazione all'ellisse
Ora applichiamo un po' di formattazione all'ellisse. Imposteremo un colore di riempimento pieno e un colore per la linea.
### Imposta colore di riempimento
```java
// Applica un po' di formattazione alla forma ellittica
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Imposta il colore e la larghezza della linea
```java
// Applica un po' di formattazione alla linea di Ellisse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Passaggio 6: Salva la presentazione
Infine, salva la presentazione nella directory specificata.
```java
// Scrivi il file PPTX sul disco
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Passaggio 7: Eliminare l'oggetto di presentazione
Eliminare l'oggetto presentazione per liberare risorse.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusione
Congratulazioni! Hai creato con successo un'ellisse formattata in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti ha guidato nella configurazione del progetto, nell'aggiunta di un'ellisse, nell'applicazione della formattazione e nel salvataggio della presentazione. Grazie a queste competenze, ora puoi migliorare le tue diapositive di PowerPoint programmaticamente, rendendo le tue presentazioni più dinamiche e visivamente accattivanti.
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di creare, modificare e gestire le presentazioni di PowerPoint a livello di programmazione.
### Posso usare Aspose.Slides per Java con qualsiasi IDE?
Sì, puoi utilizzare Aspose.Slides per Java con qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
### Ho bisogno di una licenza per Aspose.Slides?
Sì, Aspose.Slides è un prodotto commerciale e per utilizzarlo appieno è necessaria una licenza. È possibile ottenere una licenza temporanea. [Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
Puoi trovare la documentazione dettagliata su Aspose.Slides per Java [pagina di documentazione](https://reference.aspose.com/slides/java/).
### È disponibile il supporto per Aspose.Slides?
Sì, Aspose offre supporto tramite il loro [foro](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}