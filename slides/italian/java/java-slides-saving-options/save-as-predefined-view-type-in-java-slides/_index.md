---
title: Salva come tipo di visualizzazione predefinito nelle diapositive Java
linktitle: Salva come tipo di visualizzazione predefinito nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come impostare tipi di visualizzazione predefiniti in Diapositive Java utilizzando Aspose.Slides per Java. Guida passo passo con esempi di codice e domande frequenti.
type: docs
weight: 10
url: /it/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Introduzione al salvataggio come tipo di visualizzazione predefinito nelle diapositive Java

In questa guida passo passo, esploreremo come salvare una presentazione con un tipo di visualizzazione predefinito utilizzando Aspose.Slides per Java. Ti forniremo il codice e le spiegazioni necessari per eseguire correttamente questa attività.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Conoscenza base della programmazione Java.
- Aspose.Slides per la libreria Java installata.
- Ambiente di sviluppo integrato (IDE) di tua scelta.

## Configurazione dell'ambiente

Per iniziare, segui questi passaggi per configurare il tuo ambiente di sviluppo:

1. Crea un nuovo progetto Java nel tuo IDE.
2. Aggiungi la libreria Aspose.Slides per Java al tuo progetto come dipendenza.

Ora che l'ambiente è configurato, procediamo con il codice.

## Passaggio 1: creazione di una presentazione

Per dimostrare il salvataggio di una presentazione con un tipo di visualizzazione predefinito, creeremo prima una nuova presentazione. Ecco il codice per creare una presentazione:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Apertura del file di presentazione
Presentation presentation = new Presentation();
```

 In questo codice creiamo un nuovo file`Presentation` oggetto, che rappresenta la nostra presentazione di PowerPoint.

## Passaggio 2: impostazione del tipo di visualizzazione

Successivamente, imposteremo il tipo di visualizzazione per la nostra presentazione. I tipi di visualizzazione definiscono il modo in cui viene visualizzata la presentazione una volta aperta. In questo esempio lo imposteremo su "Visualizzazione schema diapositiva". Ecco il codice:

```java
// Impostazione del tipo di vista
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Nel codice sopra, usiamo il file`setLastView` metodo del`ViewProperties` classe su cui impostare il tipo di visualizzazione`SlideMasterView`. Puoi scegliere altri tipi di visualizzazione secondo necessità.

## Passaggio 3: salvataggio della presentazione

Ora che abbiamo creato la nostra presentazione e impostato il tipo di visualizzazione, è il momento di salvare la presentazione. Lo salveremo in formato PPTX. Ecco il codice:

```java
// Salvataggio della presentazione
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 In questo codice utilizziamo il file`save` metodo del`Presentation` classe per salvare la presentazione con il nome file e il formato specificati.

## Codice sorgente completo per il salvataggio come tipo di visualizzazione predefinita nelle diapositive Java

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
// Apertura del file di presentazione
Presentation presentation = new Presentation();
try
{
	// Impostazione del tipo di vista
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

### Come posso modificare il tipo di visualizzazione in qualcosa di diverso da "Visualizzazione schema diapositiva"?

 Per modificare il tipo di visualizzazione in qualcosa di diverso da "Vista schema diapositiva", sostituisci semplicemente`ViewType.SlideMasterView` con il tipo di vista desiderato, ad esempio`ViewType.NormalView` O`ViewType.SlideSorterView`, nel codice in cui impostiamo il tipo di visualizzazione.

### Posso impostare le proprietà di visualizzazione per le singole diapositive nella presentazione?

Sì, puoi impostare le proprietà di visualizzazione per singole diapositive utilizzando Aspose.Slides per Java. Puoi accedere e manipolare le proprietà di ciascuna diapositiva separatamente scorrendo le diapositive nella presentazione.

### In quali altri formati posso salvare la mia presentazione?

Aspose.Slides per Java supporta vari formati di output, tra cui PPTX, PDF, TIFF, HTML e altri. Puoi specificare il formato desiderato quando salvi la presentazione utilizzando l'apposito formato`SaveFormat` valore enum.

### Aspose.Slides per Java è adatto per l'elaborazione batch di presentazioni?

Sì, Aspose.Slides per Java è adatto per attività di elaborazione batch. Puoi automatizzare l'elaborazione di più presentazioni, applicare modifiche e salvarle in blocco utilizzando il codice Java.

### Dove posso trovare ulteriori informazioni e documentazione per Aspose.Slides per Java?

 Per documentazione completa e riferimenti relativi ad Aspose.Slides per Java, visitare il sito Web della documentazione:[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/).