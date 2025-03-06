---
title: Impostazione dell'asse di posizione nelle diapositive Java
linktitle: Impostazione dell'asse di posizione nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Migliora i tuoi grafici con Aspose.Slides per Java. Scopri come impostare l'asse di posizione nelle diapositive Java, creare presentazioni straordinarie e personalizzare facilmente i layout dei grafici.
weight: 16
url: /it/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'impostazione dell'asse di posizione in Aspose.Slides per Java

In questo tutorial impareremo come impostare l'asse di posizione in un grafico utilizzando Aspose.Slides per Java. Il posizionamento dell'asse può essere utile quando desideri personalizzare l'aspetto e il layout del grafico. Creeremo un istogramma a colonne raggruppate e regoleremo la posizione dell'asse orizzontale tra le categorie.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria da[Qui](https://releases.aspose.com/slides/java/).

## Passaggio 1: creazione di una presentazione

Innanzitutto, creiamo una nuova presentazione con cui lavorare:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo della directory dei documenti.

## Passaggio 2: aggiunta di un grafico

Successivamente, aggiungeremo un istogramma a colonne raggruppate alla diapositiva. Specifichiamo il tipo di grafico, la posizione (coordinate x, y) e le dimensioni (larghezza e altezza) del grafico:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Qui abbiamo aggiunto un istogramma in cluster nella posizione (50, 50) con una larghezza di 450 e un'altezza di 300. Puoi regolare questi valori secondo necessità.

## Passaggio 3: impostazione dell'asse di posizione

Per impostare l'asse di posizione tra le categorie, è possibile utilizzare il seguente codice:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Questo codice imposta l'asse orizzontale da visualizzare tra le categorie, il che può essere utile per alcuni layout di grafici.

## Passaggio 4: salvataggio della presentazione

Infine salviamo la presentazione con il grafico:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Sostituire`"AsposeClusteredColumnChart.pptx"` con il nome file desiderato.

Questo è tutto! Hai creato con successo un istogramma in cluster e impostato l'asse di posizione tra le categorie utilizzando Aspose.Slides per Java.

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

In questo tutorial, abbiamo esplorato come impostare l'asse di posizione in un grafico utilizzando Aspose.Slides per Java. Seguendo i passaggi descritti in questa guida, hai imparato come creare un istogramma in cluster e personalizzarne l'aspetto posizionando l'asse orizzontale tra le categorie. Aspose.Slides per Java offre potenti funzionalità per lavorare con grafici e presentazioni, rendendolo uno strumento prezioso per gli sviluppatori Java.

## Domande frequenti

### Come posso personalizzare ulteriormente il grafico?

Puoi personalizzare vari aspetti del grafico, tra cui serie di dati, titolo del grafico, legende e altro. Fare riferimento al[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/) per istruzioni dettagliate ed esempi.

### Posso cambiare il tipo di grafico?

 Sì, puoi cambiare il tipo di grafico modificando il file`ChartType` parametro quando si aggiunge il grafico. Aspose.Slides per Java supporta vari tipi di grafici come grafici a barre, grafici a linee e altro.

### Dove posso trovare altri esempi e documentazione?

 Puoi trovare la documentazione completa e altri esempi su[Aspose.Slides per la documentazione Java](https://reference.aspose.com/slides/java/) pagina.

Ricordati di eliminare l'oggetto di presentazione quando hai finito per liberare le risorse di sistema:

```java
if (pres != null) pres.dispose();
```

Per questo tutorial è tutto. Hai imparato come impostare l'asse di posizione in un grafico utilizzando Aspose.Slides per Java.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
