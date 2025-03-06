---
title: Salva PowerPoint con il carattere regolare predefinito utilizzando Java
linktitle: Salva PowerPoint con il carattere regolare predefinito utilizzando Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come manipolare le presentazioni di PowerPoint a livello di codice utilizzando Aspose.Slides per Java. Padroneggia la gestione di Java PowerPoint con tutorial passo passo.
weight: 12
url: /it/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Salva PowerPoint con il carattere regolare predefinito utilizzando Java

## introduzione
Nell'ambito dello sviluppo Java, la creazione e la manipolazione di presentazioni PowerPoint a livello di codice può migliorare notevolmente la produttività e le opzioni di personalizzazione. Aspose.Slides per Java è una solida libreria che consente agli sviluppatori di gestire in modo efficiente i file PowerPoint, offrendo un set completo di funzionalità, da semplici modifiche a presentazioni complesse.
## Prerequisiti
Prima di immergerti nell'utilizzo di Aspose.Slides per Java, assicurati di avere i seguenti prerequisiti impostati:
1. Java Development Kit (JDK): Aspose.Slides per Java richiede JDK 1.8 o versione successiva per funzionare correttamente.
2. Aspose.Slides per Java JAR: scarica l'ultima versione di Aspose.Slides per Java da[Qui](https://releases.aspose.com/slides/java/).
3. Ambiente di sviluppo integrato (IDE): utilizza IntelliJ IDEA, Eclipse o un altro IDE Java a tua scelta.
4. Comprensione di base di Java: è necessaria la familiarità con i fondamenti del linguaggio di programmazione Java.

## Importa pacchetti
Per iniziare a utilizzare Aspose.Slides per Java, importa i pacchetti necessari:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Ciò garantisce l'accesso a tutte le classi e i metodi forniti da Aspose.Slides per Java.
## Passaggio 1: imposta il tuo progetto
Innanzitutto, crea un nuovo progetto Java nel tuo IDE e includi il file JAR Aspose.Slides per Java nel percorso di compilazione del tuo progetto.
## Passaggio 2: inizializzare l'oggetto di presentazione
 Istanziare a`Presentation` oggetto caricando un file PowerPoint esistente (.pptx) dalla directory locale.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Carica la presentazione
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Sostituire`"Your Document Directory"` E`"Your Output Directory"` con i percorsi dei file effettivi.
## Passaggio 3: salva la presentazione con i caratteri regolari predefiniti
 Specificare il carattere regolare predefinito per i formati di output (HTML e PDF) utilizzando`HtmlOptions` E`PdfOptions` rispettivamente.
```java
try {
    // Opzioni di salvataggio HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Opzioni di salvataggio del PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Assicurarsi di sostituire`"Arial Black"` E`"Lucida Console"` con i caratteri regolari predefiniti desiderati.

## Conclusione
Seguendo questi passaggi, hai imparato come manipolare le presentazioni di PowerPoint utilizzando Aspose.Slides per Java in modo efficace. Questa funzionalità ti consente di automatizzare le attività, personalizzare le presentazioni e migliorare le tue applicazioni Java con funzionalità avanzate di gestione di PowerPoint.
## Domande frequenti
### Aspose.Slides per Java può funzionare con versioni precedenti di JDK?
Aspose.Slides per Java richiede JDK 1.8 o versione successiva per la compatibilità.
### Come posso ottenere una licenza temporanea per Aspose.Slides per Java?
 È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).
### Dove posso trovare una documentazione più dettagliata su Aspose.Slides per Java?
 Esplora la documentazione completa[Qui](https://reference.aspose.com/slides/java/).
### È disponibile il supporto della community per Aspose.Slides per Java?
 Sì, puoi ottenere il supporto della comunità[Qui](https://forum.aspose.com/c/slides/11).
### Posso provare Aspose.Slides per Java gratuitamente?
 Sì, scarica una versione di prova gratuita[Qui](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
