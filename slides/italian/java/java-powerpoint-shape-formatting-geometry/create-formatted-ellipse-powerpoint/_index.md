---
title: Crea un'ellisse formattata in PowerPoint
linktitle: Crea un'ellisse formattata in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come creare un'ellisse formattata in PowerPoint utilizzando Aspose.Slides per Java con la nostra guida dettagliata passo passo.
weight: 17
url: /it/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
Benvenuti in questo tutorial completo sulla creazione di un'ellisse formattata in PowerPoint utilizzando Aspose.Slides per Java. Aspose.Slides è una potente libreria che consente agli sviluppatori di manipolare i file PowerPoint a livello di codice. Che tu stia automatizzando la generazione di diapositive o migliorando le presentazioni con forme personalizzate, questa guida ti guiderà attraverso ogni passaggio, assicurandoti di poter aggiungere facilmente un'ellisse perfettamente formattata alle tue diapositive. Immergiamoci e vediamo come possiamo raggiungere questo obiettivo!
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
1. Java Development Kit (JDK): assicurati di avere installato JDK 1.6 o versione successiva.
2.  Aspose.Slides per Java: scarica l'ultima versione da[Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse.
4. Conoscenza base di Java: è richiesta familiarità con la programmazione Java.
## Importa pacchetti
Per iniziare a utilizzare Aspose.Slides, è necessario importare i pacchetti necessari. Ecco come puoi farlo:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta la directory del progetto
Innanzitutto, hai bisogno di una directory in cui archiviare i tuoi file PowerPoint.
### Crea directory
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo in cui desideri archiviare i tuoi file.
## Passaggio 2: inizializzare la presentazione
Ora crea un'istanza della classe Presentation, che rappresenta il file PowerPoint.
```java
// Crea un'istanza della classe Presentation che rappresenta il PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: ottieni la prima diapositiva
Successivamente, ottieni la prima diapositiva dalla presentazione in cui aggiungerai l'ellisse.
```java
// Ottieni la prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
## Passaggio 4: aggiungi una forma ellittica
Aggiungi una forma automatica del tipo ellisse alla diapositiva.
```java
// Aggiungi forma automatica di tipo ellisse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Qui,`50, 150, 150, 50` sono le coordinate e la dimensione dell'ellisse (posizione x, posizione y, larghezza, altezza).
## Passaggio 5: applica la formattazione all'ellisse
Ora applica un po' di formattazione all'ellisse. Imposteremo un colore di riempimento solido e un colore della linea.
### Imposta il colore di riempimento
```java
// Applicare una certa formattazione alla forma dell'ellisse
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Imposta il colore e la larghezza della linea
```java
// Applicare qualche formattazione alla linea di Ellisse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Passaggio 6: salva la presentazione
Infine, salva la presentazione nella directory specificata.
```java
// Scrivi il file PPTX su disco
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Passaggio 7: smaltire l'oggetto della presentazione
Eliminare l'oggetto della presentazione per liberare risorse.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusione
Congratulazioni! Hai creato con successo un'ellisse formattata in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo tutorial ti ha guidato attraverso la configurazione del tuo progetto, l'aggiunta di un'ellisse, l'applicazione della formattazione e il salvataggio della presentazione. Con queste competenze, ora puoi migliorare le tue diapositive di PowerPoint a livello di codice, rendendo le tue presentazioni più dinamiche e visivamente accattivanti.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente agli sviluppatori di creare, modificare e gestire presentazioni PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides per Java con qualsiasi IDE?
Sì, puoi utilizzare Aspose.Slides per Java con qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
### Ho bisogno di una licenza per Aspose.Slides?
Sì, Aspose.Slides è un prodotto commerciale e per usufruire di tutte le funzionalità è necessaria una licenza. Puoi ottenere una licenza temporanea[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare ulteriore documentazione su Aspose.Slides per Java?
 È possibile trovare la documentazione dettagliata su Aspose.Slides per Java[pagina della documentazione](https://reference.aspose.com/slides/java/).
### È disponibile supporto per Aspose.Slides?
 Sì, Aspose offre supporto tramite il loro[Forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
