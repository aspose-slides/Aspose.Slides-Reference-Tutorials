---
"description": "Scopri come abilitare le proprietà consigliate di sola lettura nelle presentazioni PowerPoint Java utilizzando Aspose.Slides per Java. Segui la nostra guida dettagliata con esempi di codice sorgente per una maggiore sicurezza delle presentazioni."
"linktitle": "Proprietà consigliate di sola lettura in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Proprietà consigliate di sola lettura in Java Slides"
"url": "/it/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Proprietà consigliate di sola lettura in Java Slides


## Introduzione all'abilitazione delle proprietà consigliate di sola lettura in Java Slides

In questo tutorial, esploreremo come abilitare le proprietà "Sola lettura consigliata" per le presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Le proprietà "Sola lettura consigliata" possono essere utili quando si desidera incoraggiare gli utenti a visualizzare una presentazione senza apportare modifiche. Queste proprietà suggeriscono di aprire la presentazione in modalità di sola lettura. Forniremo una guida dettagliata e il codice sorgente Java per ottenere questo risultato.

## Prerequisiti

Prima di iniziare, assicurati di aver configurato la libreria Aspose.Slides per Java nel tuo progetto. Puoi scaricarla da [Sito web Aspose.Slides per Java](https://products.aspose.com/slides/java/).

## Passaggio 1: creare una nuova presentazione PowerPoint

Inizieremo creando una nuova presentazione PowerPoint utilizzando Aspose.Slides per Java. Se hai già una presentazione, puoi saltare questo passaggio.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Nel codice sopra abbiamo definito il percorso per il file PowerPoint di output e creato un nuovo oggetto presentazione.

## Passaggio 2: abilitare la proprietà consigliata di sola lettura

Ora abilitiamo la proprietà Sola lettura consigliata per la presentazione.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

In questo frammento di codice, utilizziamo il `getProtectionManager().setReadOnlyRecommended(true)` metodo per impostare la proprietà Consigliata di sola lettura su `true`In questo modo si garantisce che quando qualcuno apre la presentazione, gli verrà chiesto di aprirla in modalità di sola lettura.

## Passaggio 3: salva la presentazione

Infine, salviamo la presentazione con la proprietà Sola lettura consigliata abilitata.

## Codice sorgente completo per le proprietà consigliate di sola lettura in Java Slides

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come abilitare la proprietà "Sola lettura consigliata" per una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questa funzionalità può essere utile quando si desidera limitare le modifiche e incoraggiare gli utenti a utilizzare la presentazione in modalità di sola lettura. Puoi migliorare ulteriormente la sicurezza impostando una password per la presentazione.

## Domande frequenti

### Come posso disattivare la proprietà Sola lettura consigliata?

Per disattivare la proprietà Consigliata in sola lettura, è sufficiente utilizzare il seguente codice:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Posso impostare una password per una presentazione consigliata in sola lettura?

Sì, puoi impostare una password per una presentazione consigliata in sola lettura utilizzando Aspose.Slides per Java. Puoi utilizzare `setPassword` Metodo per impostare una password per la presentazione. Se viene impostata una password, gli utenti dovranno inserirla per aprire la presentazione, anche in modalità di sola lettura.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Ricordati di sostituire `"YourPassword"` con la password desiderata.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}