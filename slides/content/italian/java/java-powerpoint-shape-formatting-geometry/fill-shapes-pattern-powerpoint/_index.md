---
title: Riempi le forme con il motivo in PowerPoint
linktitle: Riempi le forme con il motivo in PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Impara a riempire le forme con motivi in PowerPoint utilizzando Aspose.Slides per Java. Segui la nostra semplice guida passo passo per migliorare visivamente le tue presentazioni.
type: docs
weight: 11
url: /it/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---
## introduzione
Creare presentazioni visivamente accattivanti è essenziale per coinvolgere il pubblico. Un modo per migliorare le diapositive di PowerPoint è riempire le forme con motivi. In questo tutorial, esamineremo i passaggi per riempire le forme con motivi utilizzando Aspose.Slides per Java. Questa guida è pensata per gli sviluppatori che desiderano sfruttare le potenti funzionalità di Aspose.Slides per creare presentazioni straordinarie a livello di programmazione.
## Prerequisiti
Prima di immergerti nel codice, assicurati di avere i seguenti prerequisiti:
- Java Development Kit (JDK) installato sul tuo computer.
- Ambiente di sviluppo integrato (IDE) come IntelliJ IDEA o Eclipse.
-  Aspose.Slides per la libreria Java. Puoi scaricarlo da[Qui](https://releases.aspose.com/slides/java/).
- Conoscenza base della programmazione Java.
## Importa pacchetti
Per prima cosa importiamo i pacchetti necessari per il nostro esempio.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Passaggio 1: imposta il tuo progetto
Prima di scrivere il codice, assicurati che il tuo progetto sia impostato correttamente. Crea un nuovo progetto Java nel tuo IDE e aggiungi la libreria Aspose.Slides per Java alle dipendenze del tuo progetto.
## Passaggio 2: creare la directory dei documenti
Per gestire i tuoi file in modo efficiente, creiamo una directory in cui salveremo la nostra presentazione PowerPoint.
```java
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Questo frammento controlla se la directory esiste e la crea in caso contrario.
## Passaggio 3: creare un'istanza della classe di presentazione
 Successivamente, dobbiamo creare un'istanza di`Presentation` class, che rappresenta il nostro file PowerPoint.
```java
Presentation pres = new Presentation();
```
Questo inizializza un nuovo oggetto di presentazione che utilizzeremo per aggiungere diapositive e forme.
## Passaggio 4: accedi alla prima diapositiva
Per iniziare, dobbiamo accedere alla prima diapositiva della nostra presentazione. Qui è dove aggiungeremo le nostre forme.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Passaggio 5: aggiungi una forma rettangolare
Aggiungiamo una forma rettangolare alla nostra diapositiva. Questo rettangolo verrà riempito con un motivo.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Questo frammento di codice aggiunge un rettangolo alla diapositiva nella posizione e dimensione specificate.
## Passaggio 6: impostare il tipo di riempimento su Motivo
Ora dobbiamo impostare il tipo di riempimento del nostro rettangolo su un riempimento a motivo.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Passaggio 7: scegli uno stile di modello
Aspose.Slides fornisce vari stili di pattern. In questo esempio utilizzeremo il modello "Trellis".
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Passaggio 8: imposta i colori del motivo
Possiamo personalizzare i colori del nostro modello. Impostiamo il colore di sfondo sul grigio chiaro e il colore di primo piano sul giallo.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Passaggio 9: salva la presentazione
Dopo aver impostato la nostra forma con il modello desiderato, dobbiamo salvare la presentazione in un file.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Ciò salva la presentazione nella directory specificata con il nome file "RectShpPatt_out.pptx".
## Passaggio 10: ripulire le risorse
È buona norma smaltire l'oggetto di presentazione per liberare risorse.
```java
if (pres != null) pres.dispose();
```
## Conclusione
Congratulazioni! Hai riempito con successo una forma con un motivo in una diapositiva di PowerPoint utilizzando Aspose.Slides per Java. Questa potente libreria ti consente di creare e manipolare presentazioni con facilità, aggiungendo un tocco professionale ai tuoi progetti.
 Seguendo questa guida passo passo, puoi migliorare le tue presentazioni con vari modelli, rendendole più coinvolgenti e visivamente accattivanti. Per funzionalità più avanzate e opzioni di personalizzazione, assicurati di controllare il[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente API che consente agli sviluppatori di creare, manipolare e convertire presentazioni PowerPoint in applicazioni Java.
### Come posso ottenere Aspose.Slides per Java?
 È possibile scaricare Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
### È disponibile una prova gratuita per Aspose.Slides per Java?
 Sì, puoi ottenere una prova gratuita da[Qui](https://releases.aspose.com/).
### Posso utilizzare Aspose.Slides per Java per manipolare presentazioni esistenti?
Sì, Aspose.Slides per Java ti consente di aprire, modificare e salvare presentazioni PowerPoint esistenti.
### Dove posso ottenere supporto per Aspose.Slides per Java?
 Puoi ottenere supporto da[Forum di supporto di Aspose.Slides](https://forum.aspose.com/c/slides/11).