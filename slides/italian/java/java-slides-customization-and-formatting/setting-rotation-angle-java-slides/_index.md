---
title: Impostazione dell'angolo di rotazione nelle diapositive Java
linktitle: Impostazione dell'angolo di rotazione nelle diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Ottimizza le tue diapositive Java con Aspose.Slides per Java. Impara a impostare gli angoli di rotazione per gli elementi di testo. Guida passo passo con il codice sorgente.
weight: 17
url: /it/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduzione all'impostazione dell'angolo di rotazione nelle diapositive Java

In questo tutorial, esploreremo come impostare l'angolo di rotazione per il testo nel titolo dell'asse di un grafico utilizzando la libreria Aspose.Slides per Java. Regolando l'angolo di rotazione, puoi personalizzare l'aspetto dei titoli degli assi del grafico per adattarli meglio alle tue esigenze di presentazione.

## Prerequisiti

Prima di iniziare, assicurati di avere la libreria Aspose.Slides per Java installata e configurata nel tuo progetto Java. È possibile scaricare la libreria dal sito Web Aspose e seguire le istruzioni di installazione fornite nella relativa documentazione.

## Passaggio 1: crea una presentazione

Innanzitutto, devi creare una nuova presentazione o caricarne una esistente. In questo esempio, creeremo una nuova presentazione:

```java
// Il percorso della directory dei documenti.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Passaggio 2: aggiungi un grafico alla diapositiva

Successivamente, aggiungeremo un grafico alla diapositiva. In questo esempio, stiamo aggiungendo un istogramma a colonne raggruppate:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Passaggio 3: impostare l'angolo di rotazione per il titolo dell'asse

Per impostare l'angolo di rotazione per il titolo dell'asse, dovrai accedere al titolo dell'asse verticale del grafico e regolarne l'angolo di rotazione. Ecco come puoi farlo:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

In questo frammento di codice impostiamo l'angolo di rotazione su 90 gradi, che ruoterà il testo verticalmente. È possibile regolare l'angolo sul valore desiderato.

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
// Il percorso della directory dei documenti.
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

In questo tutorial, hai imparato come impostare l'angolo di rotazione per il testo nel titolo di un asse del grafico utilizzando Aspose.Slides per Java. Questa funzione ti consente di personalizzare l'aspetto dei tuoi grafici per creare presentazioni visivamente accattivanti. Sperimenta diversi angoli di rotazione per ottenere l'aspetto desiderato per i tuoi grafici.

## Domande frequenti

### Come posso modificare l'angolo di rotazione per altri elementi di testo in una diapositiva?

Puoi modificare l'angolo di rotazione per altri elementi di testo, come forme o caselle di testo, utilizzando un approccio simile. Accedi al formato testo dell'elemento e imposta l'angolo di rotazione secondo necessità.

### Posso ruotare il testo anche nel titolo dell'asse orizzontale?

Sì, puoi ruotare il testo nel titolo dell'asse orizzontale regolando l'angolo di rotazione. Imposta semplicemente l'angolo di rotazione sul valore desiderato, ad esempio 90 gradi per il testo verticale o 0 gradi per il testo orizzontale.

### Quali altre opzioni di formattazione sono disponibili per i titoli dei grafici?

Aspose.Slides per Java fornisce varie opzioni di formattazione per i titoli dei grafici, inclusi stili di carattere, colori e allineamento. Puoi esplorare la documentazione per maggiori dettagli sulla personalizzazione dei titoli dei grafici.

### È possibile animare la rotazione del testo nel titolo dell'asse di un grafico?

Sì, puoi aggiungere effetti di animazione agli elementi di testo, inclusi i titoli degli assi del grafico, utilizzando Aspose.Slides per Java. Fare riferimento alla documentazione per informazioni sull'aggiunta di animazioni alle presentazioni.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
