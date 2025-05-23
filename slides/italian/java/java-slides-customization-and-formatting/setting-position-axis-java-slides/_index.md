---
"description": "Migliora i tuoi grafici con Aspose.Slides per Java. Scopri come impostare l'asse di posizione nelle diapositive Java, creare presentazioni straordinarie e personalizzare i layout dei grafici con facilità."
"linktitle": "Impostazione dell'asse di posizione in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Impostazione dell'asse di posizione in Java Slides"
"url": "/it/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione dell'asse di posizione in Java Slides


## Introduzione all'impostazione dell'asse di posizione in Aspose.Slides per Java

In questo tutorial impareremo come impostare l'asse di posizione in un grafico utilizzando Aspose.Slides per Java. Posizionare l'asse può essere utile per personalizzare l'aspetto e il layout del grafico. Creeremo un grafico a colonne raggruppate e regoleremo la posizione dell'asse orizzontale tra le categorie.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria da [Qui](https://releases.aspose.com/slides/java/).

## Fase 1: Creazione di una presentazione

Per prima cosa, creiamo una nuova presentazione con cui lavorare:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Assicurati di sostituire `"Your Document Directory"` con il percorso effettivo verso la directory dei documenti.

## Passaggio 2: aggiunta di un grafico

Successivamente, aggiungeremo un grafico a colonne raggruppate alla diapositiva. Specifichiamo il tipo di grafico, la posizione (coordinate x, y) e le dimensioni (larghezza e altezza) del grafico:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Qui abbiamo aggiunto un grafico a colonne raggruppate alla posizione (50, 50) con una larghezza di 450 e un'altezza di 300. Puoi modificare questi valori a seconda delle tue esigenze.

## Passaggio 3: impostazione dell'asse di posizione

Per impostare l'asse di posizione tra le categorie, puoi utilizzare il seguente codice:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Questo codice imposta l'asse orizzontale da visualizzare tra le categorie, il che può essere utile per alcuni layout di grafici.

## Passaggio 4: salvataggio della presentazione

Infine, salviamo la presentazione con il grafico:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Sostituire `"AsposeClusteredColumnChart.pptx"` con il nome file desiderato.

Ecco fatto! Hai creato con successo un istogramma a colonne raggruppate e impostato l'asse di posizione tra le categorie utilizzando Aspose.Slides per Java.

## Codice sorgente completo
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial abbiamo illustrato come impostare l'asse di posizione in un grafico utilizzando Aspose.Slides per Java. Seguendo i passaggi descritti in questa guida, hai imparato a creare un grafico a colonne raggruppate e a personalizzarne l'aspetto posizionando l'asse orizzontale tra le categorie. Aspose.Slides per Java offre potenti funzionalità per lavorare con grafici e presentazioni, rendendolo uno strumento prezioso per gli sviluppatori Java.

## Domande frequenti

### Come posso personalizzare ulteriormente il grafico?

È possibile personalizzare vari aspetti del grafico, tra cui serie di dati, titolo del grafico, legende e altro ancora. Fare riferimento a [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/) per istruzioni dettagliate ed esempi.

### Posso cambiare il tipo di grafico?

Sì, puoi cambiare il tipo di grafico modificando il `ChartType` parametro durante l'aggiunta del grafico. Aspose.Slides per Java supporta vari tipi di grafici, come grafici a barre, grafici a linee e altro ancora.

### Dove posso trovare altri esempi e documentazione?

Puoi trovare documentazione completa e altri esempi su [Documentazione di Aspose.Slides per Java](https://reference.aspose.com/slides/java/) pagina.

Ricordatevi di eliminare l'oggetto presentazione una volta terminato il suo utilizzo per liberare risorse di sistema:

```java
if (pres != null) pres.dispose();
```

Questo è tutto per questo tutorial. Hai imparato come impostare l'asse di posizione in un grafico usando Aspose.Slides per Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}