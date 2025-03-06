---
title: Aggiungi immagine da oggetto SVG da risorsa esterna in diapositive Java
linktitle: Aggiungi immagine da oggetto SVG da risorsa esterna in diapositive Java
second_title: Aspose.Slides API di elaborazione Java PowerPoint
description: Scopri come aggiungere immagini SVG basate su vettori da risorse esterne alle diapositive Java utilizzando Aspose.Slides. Crea presentazioni straordinarie con immagini di alta qualità.
weight: 12
url: /it/java/image-handling/add-image-from-svg-object-from-external-resource-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduzione all'aggiunta di immagini da oggetti SVG da risorse esterne nelle diapositive Java

In questo tutorial esploreremo come aggiungere un'immagine da un oggetto SVG (Scalable Vector Graphics) da una risorsa esterna alle diapositive Java utilizzando Aspose.Slides. Questa può essere una funzionalità preziosa quando desideri incorporare immagini basate su vettori nelle tue presentazioni, garantendo immagini di alta qualità. Immergiamoci nella guida passo passo.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- Ambiente di sviluppo Java
- Aspose.Slides per la libreria Java
- Un file immagine SVG (ad esempio, "image1.svg")

## Impostazione del progetto

Assicurati che il tuo ambiente di sviluppo Java sia configurato e pronto per questo progetto. Puoi utilizzare il tuo ambiente di sviluppo integrato (IDE) preferito per Java.

## Passaggio 1: aggiunta di Aspose.Slides al tuo progetto

 Per aggiungere Aspose.Slides al tuo progetto, puoi utilizzare Maven o scaricare la libreria manualmente. Fare riferimento alla documentazione all'indirizzo[Aspose.Slides per riferimenti API Java](https://reference.aspose.com/slides/java/) per istruzioni dettagliate su come includerlo nel tuo progetto.

## Passaggio 2: crea una presentazione

Iniziamo creando una presentazione utilizzando Aspose.Slides:

```java
String dataDir = "Your Document Directory";
String outPptxPath = dataDir + "presentation_external.pptx";
Presentation p = new Presentation();
```

 Assicurati di sostituire`"Your Document Directory"` con il percorso effettivo della directory del progetto.

## Passaggio 3: caricamento dell'immagine SVG

Dobbiamo caricare l'immagine SVG da una risorsa esterna. Ecco come puoi farlo:

```java
String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
```

 In questo codice leggiamo il contenuto SVG dal file "image1.svg" e creiamo un file`ISvgImage` oggetto.

## Passaggio 4: aggiunta dell'immagine SVG alla diapositiva

Ora aggiungiamo l'immagine SVG a una diapositiva:

```java
IPPImage ppImage = p.getImages().addImage(svgImage);
p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
```

Aggiungiamo l'immagine SVG come cornice alla prima diapositiva della presentazione.

## Passaggio 5: salvataggio della presentazione

Infine, salva la presentazione:

```java
p.save(outPptxPath, SaveFormat.Pptx);
```

Questo codice salva la presentazione come "presentation_external.pptx" nella directory specificata.

## Codice sorgente completo per aggiungere immagine da oggetto SVG da risorsa esterna in diapositive Java

```java
        // Il percorso della directory dei documenti.
        String dataDir = "Your Document Directory";
        String outPptxPath = dataDir + "presentation_external.pptx";
        Presentation p = new Presentation();
        try
        {
            String svgContent = new String(Files.readAllBytes(Paths.get(dataDir + "image1.svg")));
            ISvgImage svgImage = new SvgImage(svgContent, new ExternalResourceResolver(), dataDir);
            IPPImage ppImage = p.getImages().addImage(svgImage);
            p.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 0, 0, ppImage.getWidth(), ppImage.getHeight(), ppImage);
            p.save(outPptxPath, SaveFormat.Pptx);
        }
        finally
        {
            if (p != null) p.dispose();
        }
```

## Conclusione

In questo tutorial, abbiamo imparato come aggiungere un'immagine da un oggetto SVG da una risorsa esterna alle diapositive Java utilizzando Aspose.Slides. Questa funzionalità ti consente di includere immagini vettoriali di alta qualità nelle tue presentazioni, migliorandone l'attrattiva visiva.

## Domande frequenti

### Come posso personalizzare la posizione dell'immagine SVG aggiunta sulla diapositiva?

 Puoi regolare la posizione dell'immagine SVG modificando le coordinate nel file`addPictureFrame` metodo. I parametri`(0, 0)` rappresentano le coordinate X e Y dell'angolo superiore sinistro della cornice dell'immagine.

### Posso utilizzare questo approccio per aggiungere più immagini SVG a una singola diapositiva?

Sì, puoi aggiungere più immagini SVG a una singola diapositiva ripetendo il processo per ciascuna immagine e regolando di conseguenza la loro posizione.

### Quali formati sono supportati per le risorse SVG esterne?

Aspose.Slides per Java supporta vari formati SVG, ma è consigliabile assicurarsi che i file SVG siano compatibili con la libreria per ottenere i migliori risultati.

### Aspose.Slides per Java è compatibile con le ultime versioni di Java?

Sì, Aspose.Slides per Java è compatibile con le ultime versioni Java. Assicurati di utilizzare una versione compatibile della libreria per il tuo ambiente Java.

### Posso applicare animazioni alle immagini SVG aggiunte alle diapositive?

Sì, puoi applicare animazioni alle immagini SVG nelle tue diapositive utilizzando Aspose.Slides per creare presentazioni dinamiche.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
