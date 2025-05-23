---
"description": "Scopri come impostare tipi di visualizzazione predefiniti in Java Slides utilizzando Aspose.Slides per Java. Guida dettagliata con esempi di codice e FAQ."
"linktitle": "Salva come tipo di visualizzazione predefinito in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Salva come tipo di visualizzazione predefinito in Java Slides"
"url": "/it/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Salva come tipo di visualizzazione predefinito in Java Slides


## Introduzione al tipo di visualizzazione predefinita Salva come in Java Slides

In questa guida passo passo, esploreremo come salvare una presentazione con un tipo di visualizzazione predefinito utilizzando Aspose.Slides per Java. Ti forniremo il codice e le spiegazioni necessarie per eseguire questa operazione con successo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza di base della programmazione Java.
- Libreria Aspose.Slides per Java installata.
- Ambiente di sviluppo integrato (IDE) di tua scelta.

## Impostazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Crea un nuovo progetto Java nel tuo IDE.
2. Aggiungi la libreria Aspose.Slides per Java al tuo progetto come dipendenza.

Ora che l'ambiente è configurato, procediamo con il codice.

## Fase 1: Creazione di una presentazione

Per dimostrare come salvare una presentazione con un tipo di visualizzazione predefinito, creeremo prima una nuova presentazione. Ecco il codice per creare una presentazione:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Apertura del file di presentazione
Presentation presentation = new Presentation();
```

In questo codice creiamo un nuovo `Presentation` oggetto che rappresenta la nostra presentazione PowerPoint.

## Passaggio 2: impostazione del tipo di visualizzazione

Successivamente, imposteremo il tipo di visualizzazione per la nostra presentazione. I tipi di visualizzazione definiscono come viene visualizzata la presentazione all'apertura. In questo esempio, la imposteremo su "Visualizzazione Schema diapositiva". Ecco il codice:

```java
// Impostazione del tipo di visualizzazione
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

Nel codice sopra, utilizziamo il `setLastView` metodo del `ViewProperties` classe per impostare il tipo di visualizzazione su `SlideMasterView`Puoi scegliere altri tipi di visualizzazione in base alle tue esigenze.

## Passaggio 3: salvataggio della presentazione

Ora che abbiamo creato la nostra presentazione e impostato il tipo di visualizzazione, è il momento di salvarla. La salveremo in formato PPTX. Ecco il codice:

```java
// Salvataggio della presentazione
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

In questo codice utilizziamo il `save` metodo del `Presentation` classe per salvare la presentazione con il nome file e il formato specificati.

## Codice sorgente completo per salvare come tipo di visualizzazione predefinito in Java Slides

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
// Apertura del file di presentazione
Presentation presentation = new Presentation();
try
{
	// Impostazione del tipo di visualizzazione
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Salvataggio della presentazione
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusione

In questo tutorial, abbiamo imparato come salvare una presentazione con un tipo di visualizzazione predefinito in Java utilizzando Aspose.Slides per Java. Seguendo il codice e i passaggi forniti, puoi facilmente impostare il tipo di visualizzazione delle tue presentazioni e salvarle nel formato desiderato.

## Domande frequenti

### Come faccio a cambiare il tipo di visualizzazione in un valore diverso da "Visualizzazione schema diapositiva"?

Per cambiare il tipo di visualizzazione in qualcosa di diverso da "Visualizzazione schema diapositiva", è sufficiente sostituire `ViewType.SlideMasterView` con il tipo di visualizzazione desiderato, ad esempio `ViewType.NOmalView` or `ViewType.SlideSorterView`, nel codice in cui impostiamo il tipo di vista.

### Posso impostare le proprietà di visualizzazione per singole diapositive nella presentazione?

Sì, puoi impostare le proprietà di visualizzazione per singole diapositive utilizzando Aspose.Slides per Java. Puoi accedere e modificare le proprietà di ogni diapositiva separatamente scorrendo le diapositive nella presentazione.

### In quali altri formati posso salvare la mia presentazione?

Aspose.Slides per Java supporta vari formati di output, tra cui PPTX, PDF, TIFF, HTML e altri. È possibile specificare il formato desiderato al momento del salvataggio della presentazione utilizzando l'opzione appropriata. `SaveFormat` valore enum.

### Aspose.Slides per Java è adatto all'elaborazione batch di presentazioni?

Sì, Aspose.Slides per Java è ideale per l'elaborazione in batch. È possibile automatizzare l'elaborazione di più presentazioni, applicare modifiche e salvarle in blocco utilizzando codice Java.

### Dove posso trovare maggiori informazioni e documentazione su Aspose.Slides per Java?

Per una documentazione completa e riferimenti relativi ad Aspose.Slides per Java, visitare il sito web della documentazione: [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}