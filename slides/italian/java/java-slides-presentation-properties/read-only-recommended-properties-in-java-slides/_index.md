---
title: Proprietà consigliate di sola lettura nelle diapositive Java
linktitle: Proprietà consigliate di sola lettura nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come abilitare le proprietà consigliate di sola lettura nelle presentazioni Java PowerPoint utilizzando Aspose.Slides per Java. Segui la nostra guida passo passo con esempi di codice sorgente per una maggiore sicurezza della presentazione.
weight: 17
url: /it/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'abilitazione delle proprietà consigliate di sola lettura nelle diapositive Java

In questo tutorial, esploreremo come abilitare le proprietà consigliate di sola lettura per le presentazioni di PowerPoint utilizzando Aspose.Slides per Java. Le proprietà consigliate di sola lettura possono essere utili quando si desidera incoraggiare gli utenti a visualizzare una presentazione senza apportare modifiche. Queste proprietà suggeriscono che la presentazione deve essere aperta in modalità di sola lettura. Ti forniremo una guida passo passo insieme al codice sorgente Java per raggiungere questo obiettivo.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java impostata nel tuo progetto. Puoi scaricarlo da[Aspose.Slides per il sito Web Java](https://products.aspose.com/slides/java/).

## Passaggio 1: crea una nuova presentazione PowerPoint

Inizieremo creando una nuova presentazione di PowerPoint utilizzando Aspose.Slides per Java. Se hai già una presentazione, puoi saltare questo passaggio.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Nel codice sopra, abbiamo definito il percorso per il file PowerPoint di output e creato un nuovo oggetto di presentazione.

## Passaggio 2: attiva la proprietà consigliata di sola lettura

Ora abilitiamo la proprietà consigliata di sola lettura per la presentazione.

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

 In questo frammento di codice utilizziamo il file`getProtectionManager().setReadOnlyRecommended(true)` metodo su cui impostare la proprietà consigliata di sola lettura`true`. Ciò garantisce che quando qualcuno apre la presentazione, gli verrà richiesto di aprirla in modalità di sola lettura.

## Passaggio 3: salva la presentazione

Infine, salviamo la presentazione con la proprietà Consigliata di sola lettura abilitata.

## Codice sorgente completo per le proprietà consigliate di sola lettura nelle diapositive Java

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

In questo tutorial, hai imparato come abilitare la proprietà consigliata di sola lettura per una presentazione di PowerPoint utilizzando Aspose.Slides per Java. Questa funzionalità può essere utile quando desideri limitare la modifica e incoraggiare gli spettatori a utilizzare la presentazione in modalità di sola lettura. Puoi migliorare ulteriormente la sicurezza impostando una password per la presentazione.

## Domande frequenti

### Come disabilito la proprietà consigliata di sola lettura?

Per disabilitare la proprietà consigliata di sola lettura, utilizzare semplicemente il seguente codice:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Posso impostare una password per una presentazione consigliata di sola lettura?

Sì, puoi impostare una password per una presentazione consigliata di sola lettura utilizzando Aspose.Slides per Java. Puoi usare il`setPassword` metodo per impostare una password per la presentazione. Se è impostata una password, gli utenti dovranno inserirla per aprire la presentazione, anche in modalità di sola lettura.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Ricordarsi di sostituire`"YourPassword"` con la password desiderata.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
