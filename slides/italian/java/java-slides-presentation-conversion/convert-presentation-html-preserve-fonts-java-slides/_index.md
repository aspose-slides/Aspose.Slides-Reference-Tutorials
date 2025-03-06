---
title: Conversione della presentazione in HTML preservando i caratteri originali nelle diapositive Java
linktitle: Conversione della presentazione in HTML preservando i caratteri originali nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Converti presentazioni PowerPoint in HTML preservando i caratteri originali utilizzando Aspose.Slides per Java.
weight: 14
url: /it/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione alla conversione della presentazione in HTML con la conservazione dei caratteri originali nelle diapositive Java

In questo tutorial esploreremo come convertire una presentazione PowerPoint (PPTX) in HTML preservando i caratteri originali utilizzando Aspose.Slides per Java. Ciò garantirà che l'HTML risultante assomigli molto all'aspetto della presentazione originale.

## Passaggio 1: impostazione del progetto
Prima di immergerci nel codice, assicuriamoci di avere la configurazione necessaria:

1. Scarica Aspose.Slides per Java: se non lo hai già fatto, scarica e includi la libreria Aspose.Slides per Java nel tuo progetto.

2. Crea un progetto Java: configura un progetto Java nel tuo IDE preferito e assicurati di avere una cartella "lib" in cui puoi posizionare il file JAR Aspose.Slides.

3. Importa classi richieste: importa le classi necessarie all'inizio del tuo file Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Passaggio 2: conversione della presentazione in HTML con caratteri originali

Ora convertiamo una presentazione PowerPoint in HTML preservando i caratteri originali:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";

// Carica la presentazione
Presentation pres = new Presentation("input.pptx");

try {
    // Escludi i caratteri di presentazione predefiniti come Calibri e Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Crea opzioni HTML e imposta il formattatore HTML personalizzato
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Salva la presentazione come HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Smaltire l'oggetto della presentazione
    if (pres != null) pres.dispose();
}
```

In questo frammento di codice:

-  Carichiamo la presentazione PowerPoint di input utilizzando`Presentation`.

- Definiamo un elenco di caratteri (`fontNameExcludeList`che vogliamo escludere dall'incorporamento nell'HTML. Ciò è utile per escludere caratteri comuni come Calibri e Arial per ridurre le dimensioni del file.

-  Creiamo un'istanza di`EmbedAllFontsHtmlController` e passargli l'elenco di esclusione dei caratteri.

-  Noi creiamo`HtmlOptions` e impostare un formattatore HTML personalizzato utilizzando`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Infine, salviamo la presentazione come HTML con le opzioni specificate.

## Codice sorgente completo per convertire la presentazione in HTML preservando i caratteri originali nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// escludere i caratteri di presentazione predefiniti
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

In questo tutorial hai imparato come convertire una presentazione PowerPoint in HTML preservando i caratteri originali utilizzando Aspose.Slides per Java. Ciò è utile quando desideri mantenere la fedeltà visiva delle tue presentazioni quando le condividi sul web.

## Domande frequenti

### Come posso scaricare Aspose.Slides per Java?

 È possibile scaricare Aspose.Slides per Java dal sito Web Aspose. Visita[Qui](https://downloads.aspose.com/slides/java/) per ottenere la versione più recente.

### Posso personalizzare l'elenco dei caratteri esclusi?

 Sì, puoi personalizzare il file`fontNameExcludeList` array per includere o escludere caratteri specifici in base alle proprie esigenze.

### Questo metodo funziona con i formati PowerPoint meno recenti come PPT?

Questo esempio di codice è progettato per i file PPTX. Se devi convertire file PPT più vecchi, potrebbe essere necessario apportare modifiche al codice.

### Come posso personalizzare ulteriormente l'output HTML?

 Puoi esplorare il`HtmlOptions` classe per personalizzare vari aspetti dell'output HTML, come dimensioni della diapositiva, qualità dell'immagine e altro.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
