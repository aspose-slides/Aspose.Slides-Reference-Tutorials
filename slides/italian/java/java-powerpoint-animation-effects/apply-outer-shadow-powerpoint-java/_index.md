---
"description": "Scopri come applicare l'effetto ombra esterna in PowerPoint usando Java con Aspose.Slides. Arricchisci le tue presentazioni con profondità e impatto visivo."
"linktitle": "Applicare l'ombra esterna in PowerPoint con Java"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Applicare l'ombra esterna in PowerPoint con Java"
"url": "/it/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Applicare l'ombra esterna in PowerPoint con Java

## Introduzione
Creare presentazioni PowerPoint visivamente accattivanti spesso richiede l'aggiunta di vari effetti a forme e testo. Uno di questi è l'ombra esterna, che può far risaltare gli elementi e aggiungere profondità alle diapositive. In questo tutorial, imparerai come applicare un effetto ombra esterna a una forma in PowerPoint utilizzando Java con Aspose.Slides.
## Prerequisiti

Prima di iniziare questo tutorial, assicurati di avere i seguenti prerequisiti:

1. Java Development Kit (JDK): assicurati di avere Java installato sul tuo sistema. Puoi scaricare e installare la versione più recente del JDK dal sito web di Oracle.

2. Aspose.Slides per Java: Scarica e installa Aspose.Slides per Java da [pagina di download](https://releases.aspose.com/slides/java/).

3. Ambiente di sviluppo integrato (IDE): scegli il tuo IDE Java preferito, come Eclipse, IntelliJ IDEA o NetBeans, per la codifica e l'esecuzione di applicazioni Java.

4. Conoscenza di base di Java: la familiarità con i fondamenti del linguaggio di programmazione Java e con i concetti orientati agli oggetti sarà utile per comprendere gli esempi di codice.

## Importa pacchetti

Per prima cosa, importa i pacchetti necessari per lavorare con Aspose.Slides e le funzionalità correlate nel tuo progetto Java:

```java
import com.aspose.slides.*;
```

Ora scomponiamo il codice di esempio in più passaggi per applicare l'effetto ombra esterna a una forma in PowerPoint utilizzando Java con Aspose.Slides:

## Passaggio 1: configura l'ambiente del progetto

Crea un nuovo progetto Java nel tuo IDE preferito e aggiungi la libreria Aspose.Slides per Java al percorso di build del tuo progetto.

## Passaggio 2: inizializzare l'oggetto Presentazione

Crea un'istanza di `Presentation` classe, che rappresenta un file di presentazione di PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Passaggio 3: aggiungere una diapositiva e una forma

Ottieni un riferimento alla diapositiva in cui vuoi aggiungere la forma, quindi aggiungi una forma automatica (ad esempio un rettangolo) alla diapositiva.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Passaggio 4: personalizza la forma

Imposta il tipo di riempimento della forma su "NoFill" e aggiungi del testo alla forma.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Passaggio 5: personalizza il testo

Accedi alle proprietà del testo della forma e personalizza la dimensione del carattere.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Passaggio 6: abilita l'effetto Ombra esterna

Abilita l'effetto ombra esterna per la porzione di testo.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Passaggio 7: impostare i parametri dell'ombra

Definisci i parametri per l'effetto ombra esterna, come raggio di sfocatura, direzione, distanza e colore dell'ombra.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Passaggio 8: salvare la presentazione

Salvare la presentazione modificata con l'effetto ombra esterna applicato alla forma.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Conclusione

Congratulazioni! Hai applicato con successo un effetto ombra esterna a una forma in PowerPoint utilizzando Java con Aspose.Slides. Sperimenta diversi parametri per ottenere gli effetti visivi desiderati nelle tue presentazioni.

## Domande frequenti

### Posso applicare l'effetto ombra esterna anche ad altre forme oltre ai rettangoli?
Sì, puoi applicare l'effetto ombra esterna a varie forme supportate da Aspose.Slides, come cerchi, triangoli e forme personalizzate.

### È possibile personalizzare il colore e l'intensità dell'ombra?
Assolutamente! Hai il pieno controllo sui parametri dell'ombra, inclusi colore, raggio di sfocatura, direzione e distanza.

### Posso applicare più effetti alla stessa forma?
Sì, puoi combinare più effetti, come ombra esterna, ombra interna, bagliore e riflesso, per migliorare l'aspetto visivo di forme e testo nelle tue presentazioni.

### Aspose.Slides supporta l'applicazione di effetti agli elementi di testo?
Sì, puoi applicare effetti non solo alle forme, ma anche a singole porzioni di testo all'interno delle forme, il che ti offre un'ampia flessibilità nella progettazione delle tue diapositive.

### Dove posso trovare ulteriori risorse e supporto per Aspose.Slides?
Puoi fare riferimento al [documentazione](https://reference.aspose.com/slides/java/) per riferimenti API dettagliati ed esplorare [Forum di Aspose.Slides](https://forum.aspose.com/c/slides/11) per il supporto e le discussioni della comunità.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}