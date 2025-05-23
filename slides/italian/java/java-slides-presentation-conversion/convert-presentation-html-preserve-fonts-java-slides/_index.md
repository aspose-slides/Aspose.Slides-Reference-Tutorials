---
"description": "Converti le presentazioni PowerPoint in HTML mantenendo i font originali utilizzando Aspose.Slides per Java."
"linktitle": "Conversione di una presentazione in HTML mantenendo i caratteri originali in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Conversione di una presentazione in HTML mantenendo i caratteri originali in Java Slides"
"url": "/it/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Conversione di una presentazione in HTML mantenendo i caratteri originali in Java Slides


## Introduzione alla conversione di presentazioni in HTML con conservazione dei caratteri originali in Java Slides

In questo tutorial, esploreremo come convertire una presentazione PowerPoint (PPTX) in HTML mantenendo i font originali utilizzando Aspose.Slides per Java. Questo garantirà che il codice HTML risultante assomigli il più possibile all'aspetto della presentazione originale.

## Passaggio 1: impostazione del progetto
Prima di immergerci nel codice, assicuriamoci di avere la configurazione necessaria:

1. Scarica Aspose.Slides per Java: se non l'hai ancora fatto, scarica e includi la libreria Aspose.Slides per Java nel tuo progetto.

2. Crea un progetto Java: imposta un progetto Java nel tuo IDE preferito e assicurati di avere una cartella "lib" in cui puoi posizionare il file JAR Aspose.Slides.

3. Importa le classi richieste: importa le classi necessarie all'inizio del tuo file Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Passaggio 2: conversione della presentazione in HTML con i caratteri originali

Ora convertiamo una presentazione PowerPoint in HTML mantenendo i font originali:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";

// Carica la presentazione
Presentation pres = new Presentation("input.pptx");

try {
    // Escludi i font di presentazione predefiniti come Calibri e Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Crea opzioni HTML e imposta il formattatore HTML personalizzato
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Salva la presentazione come HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Eliminare l'oggetto di presentazione
    if (pres != null) pres.dispose();
}
```

In questo frammento di codice:

- Carichiamo la presentazione PowerPoint in input utilizzando `Presentation`.

- Definiamo un elenco di font (`fontNameExcludeList`) che vogliamo escludere dall'incorporamento nell'HTML. Questo è utile per escludere font comuni come Calibri e Arial e ridurre le dimensioni del file.

- Creiamo un'istanza di `EmbedAllFontsHtmlController` e passargli l'elenco di esclusione dei font.

- Noi creiamo `HtmlOptions` e imposta un formattatore HTML personalizzato utilizzando `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Infine, salviamo la presentazione in formato HTML con le opzioni specificate.

## Codice sorgente completo per convertire la presentazione in HTML mantenendo i caratteri originali nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// escludi i font di presentazione predefiniti
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come convertire una presentazione PowerPoint in HTML mantenendo i font originali utilizzando Aspose.Slides per Java. Questo è utile quando vuoi mantenere la fedeltà visiva delle tue presentazioni quando le condividi sul web.

## Domande frequenti

### Come posso scaricare Aspose.Slides per Java?

Puoi scaricare Aspose.Slides per Java dal sito web di Aspose. Visita [Qui](https://downloads.aspose.com/slides/java/) per ottenere la versione più recente.

### Posso personalizzare l'elenco dei font esclusi?

Sì, puoi personalizzare il `fontNameExcludeList` array per includere o escludere specifici font in base alle tue esigenze.

### Questo metodo funziona anche per i vecchi formati di PowerPoint, come PPT?

Questo esempio di codice è progettato per file PPTX. Se è necessario convertire file PPT più vecchi, potrebbe essere necessario apportare modifiche al codice.

### Come posso personalizzare ulteriormente l'output HTML?

Puoi esplorare il `HtmlOptions` classe per personalizzare vari aspetti dell'output HTML, come le dimensioni della diapositiva, la qualità dell'immagine e altro ancora.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}