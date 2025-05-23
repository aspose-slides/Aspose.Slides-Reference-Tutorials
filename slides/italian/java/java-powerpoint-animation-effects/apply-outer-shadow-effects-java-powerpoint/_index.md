---
"description": "Scopri come applicare facilmente effetti di ombra esterna nelle presentazioni Java PowerPoint utilizzando Aspose.Slides con la nostra guida dettagliata e passo dopo passo."
"linktitle": "Applicare effetti ombra esterna in Java PowerPoint"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Applicare effetti ombra esterna in Java PowerPoint"
"url": "/it/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Applicare effetti ombra esterna in Java PowerPoint

## Introduzione
Creare presentazioni accattivanti richiede spesso l'aggiunta di vari effetti per migliorare l'aspetto visivo delle diapositive. Uno di questi effetti è l'ombra esterna, che può far risaltare gli elementi e aggiungere profondità ai contenuti. In questo tutorial, illustreremo il processo di applicazione degli effetti di ombra esterna alle forme in una presentazione PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerci nella guida passo passo, assicuriamoci di avere tutto ciò di cui hai bisogno:
1. Java Development Kit (JDK): assicurati di aver installato il JDK sul tuo computer. Puoi scaricarlo da [Sito web di Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides per la libreria Java: scarica l'ultima versione da [Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse per scrivere ed eseguire il codice Java.
4. Una licenza Aspose valida: puoi acquistare una licenza da [Posare](https://purchase.aspose.com/buy) o ottenere un [licenza temporanea](https://purchase.aspose.com/temporary-license/) per la valutazione.
## Importa pacchetti
Per prima cosa, è necessario importare i pacchetti necessari per Aspose.Slides. Questo è il punto di partenza per utilizzare le potenti funzionalità offerte dalla libreria.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Analizziamo nel dettaglio il processo di applicazione degli effetti ombra esterna in passaggi gestibili:
## Passaggio 1: impostare la directory del progetto
Prima di iniziare a scrivere il codice, è necessario impostare la directory del progetto in cui verranno archiviati e accessibili i file di PowerPoint.
Assicurati che la directory del tuo progetto esista. In caso contrario, creala utilizzando il seguente codice:
```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Creare la directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Passaggio 2: inizializzare la presentazione
Adesso dobbiamo inizializzare la presentazione, dove aggiungeremo forme ed effetti.

Crea una nuova istanza di `Presentation` classe per iniziare a lavorare con un nuovo file di PowerPoint.
```java
// Creare un'istanza di una classe PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungere una diapositiva e una forma
Successivamente, aggiungi una diapositiva alla presentazione e poi aggiungi una forma a cui applicherai l'effetto ombra.
### Ottieni il riferimento alla diapositiva
Recupera un riferimento alla prima diapositiva della presentazione.
```java
// Ottieni il riferimento della diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
### Aggiungi una forma automatica
Aggiungere una forma automatica rettangolare alla diapositiva in base alle coordinate specificate.
```java
// Aggiungi una forma automatica di tipo rettangolo
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Passaggio 4: personalizza la forma
Aggiungi del testo alla forma e regola le impostazioni di riempimento per rendere più visibile l'effetto ombra.
### Aggiungi TextFrame alla forma
Inserire il testo nella forma rettangolare.
```java
// Aggiungi TextFrame al rettangolo
aShp.addTextFrame("Aspose TextBox");
```
### Disabilita Riempimento forma
Disattiva il riempimento della forma per enfatizzare l'ombra del testo.
```java
// Disabilitare il riempimento della forma nel caso in cui si voglia ottenere l'ombra del testo
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Passaggio 5: applica l'effetto ombra esterna
Adesso è il momento di applicare l'effetto ombra esterna alla forma.
### Abilita effetto ombra esterna
Abilita l'effetto ombra esterna per la forma.
```java
// Aggiungi l'ombra esterna e imposta tutti i parametri necessari
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Configurare i parametri ombra
Imposta varie proprietà dell'ombra, come raggio di sfocatura, direzione, distanza, allineamento e colore.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Passaggio 6: Salva la presentazione
Infine, salva la presentazione sul disco.
```java
//Scrivi la presentazione su disco
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Fase 7: Smaltimento delle risorse
Assicurarsi di liberare risorse eliminando l'oggetto presentazione.
```java
// Pulisci le risorse
if (pres != null) pres.dispose();
```
## Conclusione
Ed ecco fatto! Hai applicato con successo un effetto ombra esterna a una forma in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo effetto può migliorare significativamente l'aspetto visivo delle tue diapositive, facendo risaltare i tuoi contenuti.
Se riscontri problemi o hai bisogno di ulteriore assistenza, non esitare a consultare il [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/) o visitare il [forum di supporto](https://forum.aspose.com/c/slides/11)Buona programmazione!
## Domande frequenti
### Che cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che consente di creare, modificare e convertire presentazioni PowerPoint nelle applicazioni Java.
### Come posso ottenere una prova gratuita di Aspose.Slides per Java?
Puoi scaricare una versione di prova gratuita da [Sito web di Aspose](https://releases.aspose.com/).
### Posso usare Aspose.Slides per Java con qualsiasi IDE?
Sì, puoi utilizzare Aspose.Slides per Java con qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
Puoi ottenere una licenza temporanea dal [Sito web di Aspose](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare altri esempi e documentazione per Aspose.Slides?
Puoi trovare altri esempi e documentazione dettagliata su [Pagina di documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}