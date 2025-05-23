---
"description": "Ottimizza le tue slide Java con Aspose.Slides per Java. Impara a impostare gli angoli di rotazione per gli elementi di testo. Guida passo passo con codice sorgente."
"linktitle": "Impostazione dell'angolo di rotazione in Java Slides"
"second_title": "API di elaborazione Java PowerPoint di Aspose.Slides"
"title": "Impostazione dell'angolo di rotazione in Java Slides"
"url": "/it/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Impostazione dell'angolo di rotazione in Java Slides


## Introduzione all'impostazione dell'angolo di rotazione in Java Slides

In questo tutorial, esploreremo come impostare l'angolo di rotazione del testo nel titolo di un asse di un grafico utilizzando la libreria Aspose.Slides per Java. Regolando l'angolo di rotazione, puoi personalizzare l'aspetto dei titoli degli assi del grafico per adattarli al meglio alle tue esigenze di presentazione.

## Prerequisiti

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Slides per Java nel tuo progetto Java. Puoi scaricare la libreria dal sito web di Aspose e seguire le istruzioni di installazione fornite nella relativa documentazione.

## Passaggio 1: creare una presentazione

Per prima cosa, devi creare una nuova presentazione o caricarne una esistente. In questo esempio, creeremo una nuova presentazione:

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungere un grafico alla diapositiva

Successivamente, aggiungeremo un grafico alla diapositiva. In questo esempio, aggiungeremo un grafico a colonne raggruppate:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Passaggio 3: imposta l'angolo di rotazione per il titolo dell'asse

Per impostare l'angolo di rotazione del titolo dell'asse, è necessario accedere al titolo dell'asse verticale del grafico e regolarne l'angolo di rotazione. Ecco come fare:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

In questo frammento di codice, impostiamo l'angolo di rotazione a 90 gradi, che ruoterà il testo verticalmente. Puoi regolare l'angolo al valore desiderato.

## Passaggio 4: salva la presentazione

Infine, salva la presentazione in un file PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Codice sorgente completo per impostare l'angolo di rotazione nelle diapositive Java

```java
// Percorso verso la directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusione

In questo tutorial, hai imparato come impostare l'angolo di rotazione del testo nel titolo di un asse di un grafico utilizzando Aspose.Slides per Java. Questa funzione ti consente di personalizzare l'aspetto dei tuoi grafici per creare presentazioni visivamente accattivanti. Sperimenta con diversi angoli di rotazione per ottenere l'aspetto desiderato per i tuoi grafici.

## Domande frequenti

### Come posso modificare l'angolo di rotazione di altri elementi di testo in una diapositiva?

È possibile modificare l'angolo di rotazione per altri elementi di testo, come forme o caselle di testo, utilizzando un approccio simile. Accedi al formato di testo dell'elemento e imposta l'angolo di rotazione in base alle tue esigenze.

### Posso ruotare il testo anche nel titolo sull'asse orizzontale?

Sì, puoi ruotare il testo nel titolo sull'asse orizzontale regolando l'angolo di rotazione. Imposta semplicemente l'angolo di rotazione al valore desiderato, ad esempio 90 gradi per il testo verticale o 0 gradi per il testo orizzontale.

### Quali altre opzioni di formattazione sono disponibili per i titoli dei grafici?

Aspose.Slides per Java offre diverse opzioni di formattazione per i titoli dei grafici, inclusi stili di carattere, colori e allineamento. Puoi consultare la documentazione per maggiori dettagli sulla personalizzazione dei titoli dei grafici.

### È possibile animare la rotazione del testo nel titolo di un asse di un grafico?

Sì, puoi aggiungere effetti di animazione agli elementi di testo, inclusi i titoli degli assi dei grafici, utilizzando Aspose.Slides per Java. Consulta la documentazione per informazioni sull'aggiunta di animazioni alle tue presentazioni.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}