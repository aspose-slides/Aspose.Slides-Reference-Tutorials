---
title: Applicare effetti ombra esterna in Java PowerPoint
linktitle: Applicare effetti ombra esterna in Java PowerPoint
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come applicare facilmente gli effetti dell'ombra esterna nelle presentazioni Java PowerPoint utilizzando Aspose.Slides con la nostra guida dettagliata passo passo.
weight: 11
url: /it/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## introduzione
La creazione di presentazioni accattivanti spesso richiede l'aggiunta di vari effetti per migliorare l'attrattiva visiva delle diapositive. Uno di questi effetti è l'ombra esterna, che può far risaltare i tuoi elementi e aggiungere profondità ai tuoi contenuti. In questo tutorial, esamineremo il processo di applicazione degli effetti d'ombra esterni alle forme in una presentazione di PowerPoint utilizzando Aspose.Slides per Java.
## Prerequisiti
Prima di immergerci nella guida passo passo, assicuriamoci di avere tutto ciò di cui hai bisogno:
1.  Java Development Kit (JDK): assicurati di avere JDK installato sul tuo computer. Puoi scaricarlo da[Il sito web di Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides per Java Library: scarica la versione più recente da[Aspose.Slides per Java](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza un IDE come IntelliJ IDEA o Eclipse per scrivere ed eseguire il codice Java.
4.  Una licenza Asporre valida: è possibile acquistare una licenza da[Aspose](https://purchase.aspose.com/buy) o prendi un[licenza temporanea](https://purchase.aspose.com/temporary-license/) Per la valutazione.
## Importa pacchetti
Innanzitutto, dovrai importare i pacchetti necessari per Aspose.Slides. Ciò pone le basi per l'utilizzo delle potenti funzionalità fornite dalla libreria.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Analizziamo il processo di applicazione degli effetti dell'ombra esterna in passaggi gestibili:
## Passaggio 1: impostare la directory del progetto
Prima di iniziare a scrivere il codice, devi impostare la directory del progetto in cui verranno archiviati e accessibili i file PowerPoint.
Assicurati che la directory del tuo progetto esista. In caso contrario, crealo utilizzando il seguente codice:
```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Crea directory se non è già presente.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Passaggio 2: inizializzare la presentazione
Ora dobbiamo inizializzare la presentazione in cui aggiungeremo le nostre forme ed effetti.

 Crea una nuova istanza di`Presentation` lezione per iniziare a lavorare con un nuovo file PowerPoint.
```java
// Istanziare una classe PPTX
Presentation pres = new Presentation();
```
## Passaggio 3: aggiungi una diapositiva e una forma
Successivamente, aggiungi una diapositiva alla presentazione e quindi aggiungi una forma a cui applicherai l'effetto ombra.
### Ottieni riferimento alla diapositiva
Recupera un riferimento alla prima diapositiva della presentazione.
```java
// Ottieni il riferimento della diapositiva
ISlide sld = pres.getSlides().get_Item(0);
```
### Aggiungi una forma automatica
Aggiungi una forma rettangolare alla diapositiva alle coordinate specificate.
```java
// Aggiungi una forma automatica di tipo rettangolo
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Passaggio 4: personalizza la forma
Aggiungi testo alla forma e regola le impostazioni di riempimento per rendere l'effetto ombra più visibile.
### Aggiungi TextFrame alla forma
Inserisci il testo nella forma rettangolare.
```java
// Aggiungi TextFrame al rettangolo
aShp.addTextFrame("Aspose TextBox");
```
### Disabilita riempimento forma
Disattiva il riempimento della forma per enfatizzare l'ombra del testo.
```java
// Disabilita il riempimento della forma nel caso in cui desideriamo ottenere l'ombra del testo
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Passaggio 5: applica l'effetto ombra esterna
Ora è il momento di applicare l'effetto ombra esterna alla forma.
### Abilita l'effetto ombra esterna
Abilita l'effetto ombra esterna per la forma.
```java
// Aggiungi l'ombra esterna e imposta tutti i parametri necessari
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Configura i parametri dell'ombra
Imposta varie proprietà dell'ombra come raggio di sfocatura, direzione, distanza, allineamento e colore.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Passaggio 6: salva la presentazione
Infine, salva la presentazione su disco.
```java
//Scrivere la presentazione su disco
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Passaggio 7: smaltimento delle risorse
Assicurati di rilasciare risorse eliminando l'oggetto della presentazione.
```java
// Pulisci le risorse
if (pres != null) pres.dispose();
```
## Conclusione
E il gioco è fatto! Hai applicato con successo un effetto ombra esterna a una forma in una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questo effetto può migliorare in modo significativo l'attrattiva visiva delle tue diapositive, facendo risaltare i tuoi contenuti.
 Se riscontri problemi o hai bisogno di ulteriore assistenza, non esitare a consultare il[Documentazione Aspose.Slides](https://reference.aspose.com/slides/java/) oppure visitare il[Forum di assistenza](https://forum.aspose.com/c/slides/11). Buona programmazione!
## Domande frequenti
### Cos'è Aspose.Slides per Java?
Aspose.Slides per Java è una potente libreria che ti consente di creare, manipolare e convertire presentazioni PowerPoint in applicazioni Java.
### Come posso ottenere una prova gratuita di Aspose.Slides per Java?
 È possibile scaricare una versione di prova gratuita da[Sito web Aspose](https://releases.aspose.com/).
### Posso utilizzare Aspose.Slides per Java con qualsiasi IDE?
Sì, puoi utilizzare Aspose.Slides per Java con qualsiasi IDE Java come IntelliJ IDEA, Eclipse o NetBeans.
### Come posso ottenere una licenza temporanea per Aspose.Slides?
 Puoi ottenere una licenza temporanea da[Sito web Aspose](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare altri esempi e documentazione per Aspose.Slides?
 Puoi trovare ulteriori esempi e documentazione dettagliata su[Pagina della documentazione di Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
