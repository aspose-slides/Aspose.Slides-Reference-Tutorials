---
title: Riempi le forme con gradiente in PowerPoint
linktitle: Riempi le forme con gradiente in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come riempire le forme con sfumatura in PowerPoint utilizzando Aspose.Slides per Java con questa guida dettagliata passo passo.
weight: 10
url: /it/java/java-powerpoint-shape-formatting-geometry/fill-shapes-gradient-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## introduzione
Creare presentazioni PowerPoint visivamente accattivanti è fondamentale per affascinare il tuo pubblico. Uno dei modi efficaci per migliorare le tue diapositive è riempire le forme con sfumature. Questo tutorial ti guiderà attraverso il processo di utilizzo di Aspose.Slides per Java per riempire forme con sfumature in PowerPoint. Che tu sia uno sviluppatore esperto o che tu abbia appena iniziato, troverai questa guida utile e facile da seguire. Immergiamoci nel mondo dei gradienti e vediamo come possono trasformare le tue presentazioni.
## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- Java Development Kit (JDK): assicurati di avere JDK installato. Puoi scaricarlo da[Sito web dell'Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
-  Aspose.Slides per Java: scarica l'ultima versione da[Qui](https://releases.aspose.com/slides/java/).
- Ambiente di sviluppo integrato (IDE): un IDE come IntelliJ IDEA o Eclipse renderà la tua esperienza di codifica più fluida.
- Conoscenza di base di Java: la familiarità con la programmazione Java è essenziale.
## Importa pacchetti
Per iniziare con Aspose.Slides, è necessario importare i pacchetti necessari. Assicurati di aver aggiunto Aspose.Slides per Java alle dipendenze del tuo progetto.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Passaggio 1: impostazione della directory del progetto
Innanzitutto, hai bisogno di una directory per salvare il tuo file PowerPoint.
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean isExists = new File(dataDir).exists();
if (!isExists)
	new File(dataDir).mkdirs();
```
Questo passaggio garantisce che la directory in cui intendi salvare il file PowerPoint esista. In caso contrario, il codice lo creerà per te.
## Passaggio 2: istanziare la lezione di presentazione
Successivamente, crea un'istanza della classe Presentation che rappresenta un file PowerPoint.
```java
// Crea un'istanza della classe Presentation che rappresenta il PPTX
Presentation pres = new Presentation();
```
Questo oggetto fungerà da contenitore per le diapositive e le forme.
## Passaggio 3: accedi alla prima diapositiva
Dopo aver creato l'istanza della presentazione, devi accedere alla prima diapositiva in cui aggiungerai le forme.
```java
// Ottieni la prima diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
Questo codice recupera la prima diapositiva della presentazione in cui puoi iniziare ad aggiungere forme.
## Passaggio 4: aggiungi una forma ellittica
Ora aggiungi una forma ellittica alla diapositiva.
```java
// Aggiungi forma automatica di tipo ellisse
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
Qui viene aggiunta un'ellisse in una posizione specificata con dimensioni definite.
## Passaggio 5: applica il riempimento sfumato alla forma
Per rendere la forma visivamente accattivante, applica un riempimento sfumato.
```java
// Applica una formattazione sfumata alla forma dell'ellisse
shp.getFillFormat().setFillType(FillType.Gradient);
shp.getFillFormat().getGradientFormat().setGradientShape(GradientShape.Linear);
```
Questo codice imposta il tipo di riempimento della forma su gradiente e specifica la forma del gradiente come lineare.
## Passaggio 6: imposta la direzione del gradiente
Definisci la direzione del gradiente per un migliore effetto visivo.
```java
// Imposta la direzione del gradiente
shp.getFillFormat().getGradientFormat().setGradientDirection(GradientDirection.FromCorner2);
```
Ciò fa sì che la sfumatura scorra da un angolo all'altro, migliorando il fascino estetico della forma.
## Passaggio 7: aggiungi interruzioni di gradiente
Le interruzioni della sfumatura definiscono i colori e le posizioni all'interno della sfumatura.
```java
// Aggiungi due interruzioni di gradiente
shp.getFillFormat().getGradientFormat().getGradientStops().add((float) 1.0, new Color(PresetColor.Purple));
shp.getFillFormat().getGradientFormat().getGradientStops().add((float) 0, Color.RED);
```
Questo codice aggiunge due interruzioni di gradiente, sfumando dal viola al rosso.
## Passaggio 8: salva la presentazione
Infine, salva la presentazione nella directory specificata.
```java
// Scrivi il file PPTX su disco
pres.save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Questa riga di codice salva la presentazione con l'effetto sfumato applicato.
## Passaggio 9: smaltire l'oggetto della presentazione
Assicurati sempre di liberare le risorse smaltendo l'oggetto della presentazione.
```java
finally {
	if (pres != null) pres.dispose();
}
```
Ciò garantisce che tutte le risorse vengano ripulite correttamente.
## Conclusione
L'utilizzo delle sfumature nelle forme di PowerPoint può migliorare in modo significativo l'attrattiva visiva delle tue presentazioni. Con Aspose.Slides per Java, hai un potente strumento a tua disposizione per creare presentazioni straordinarie a livello di codice. Seguendo questa guida passo passo, puoi aggiungere facilmente forme con gradiente alle tue diapositive, rendendo i tuoi contenuti più coinvolgenti e visivamente accattivanti.
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API per creare e manipolare presentazioni PowerPoint a livello di codice.
### Posso utilizzare Aspose.Slides gratuitamente?
 Puoi utilizzare Aspose.Slides con a[prova gratuita](https://releases.aspose.com/) per testarne le funzionalità prima di acquistare una licenza.
### Cosa sono le interruzioni del gradiente?
Le interruzioni della sfumatura sono punti specifici all'interno di una sfumatura che definiscono il colore e la sua posizione all'interno della sfumatura.
### Come posso ottenere supporto per Aspose.Slides?
 Per supporto, visitare il[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Dove posso scaricare l'ultima versione di Aspose.Slides per Java?
 È possibile scaricare la versione più recente da[Pagina di download di Aspose.Slides](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
