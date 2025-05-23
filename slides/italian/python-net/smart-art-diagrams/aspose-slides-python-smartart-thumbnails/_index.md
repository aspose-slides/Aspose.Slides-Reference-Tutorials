---
"date": "2025-04-23"
"description": "Scopri come automatizzare la creazione di elementi grafici SmartArt nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python, inclusa l'estrazione e il salvataggio efficiente delle miniature."
"title": "Come creare e recuperare miniature SmartArt utilizzando Aspose.Slides per Python"
"url": "/it/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e recuperare miniature SmartArt utilizzando Aspose.Slides per Python

## Introduzione

Creare presentazioni visivamente accattivanti è essenziale per catturare l'attenzione del pubblico. Un modo efficace per migliorare le presentazioni PowerPoint è integrare elementi grafici dinamici come SmartArt. Se cercate un metodo automatizzato per generare questi elementi visivi ed estrarne le miniature, questa guida su "Aspose.Slides Python" vi sarà di grande aiuto.

Utilizzando Aspose.Slides per Python, puoi creare facilmente grafiche SmartArt, accedere a nodi specifici all'interno dell'immagine, recuperare le miniature di tali nodi e salvarle per i tuoi progetti. Questo tutorial ti guiderà passo passo in dettaglio.

**Cosa imparerai:**
- Come installare e configurare Aspose.Slides per Python.
- Creazione di un elemento grafico SmartArt in una presentazione di PowerPoint.
- Accesso ai nodi all'interno di un elemento grafico SmartArt.
- Estrazione e salvataggio di una miniatura di un'immagine da un nodo specifico.

Prima di iniziare, analizziamo i prerequisiti.

## Prerequisiti

Prima di iniziare, assicurati di avere pronto quanto segue:

- **Librerie richieste:** Avrai bisogno di Aspose.Slides per Python. Assicurati che il tuo ambiente supporti Python 3.x.
- **Requisiti di configurazione dell'ambiente:** Un'installazione funzionante di Python e un IDE o un editor di testo adatto come VSCode o PyCharm.
- **Prerequisiti di conoscenza:** Conoscenza di base della programmazione Python, comprese le definizioni delle funzioni e le operazioni sui file.

## Impostazione di Aspose.Slides per Python

Innanzitutto, devi installare la libreria Aspose.Slides. Puoi farlo facilmente usando pip:

```bash
pip install aspose.slides
```

Una volta installato, ottieni una licenza se desideri esplorare tutte le funzionalità senza limitazioni. Puoi iniziare con una prova gratuita, richiedere una licenza temporanea o acquistarla per un utilizzo a lungo termine.

Per inizializzare Aspose.Slides nel tuo ambiente Python, importa la libreria all'inizio dello script:

```python
import aspose.slides as slides
```

## Guida all'implementazione

Analizziamo nel dettaglio i passaggi necessari per creare e recuperare una miniatura SmartArt.

### Passaggio 1: creare una nuova istanza di presentazione

Inizia creando un'istanza di una presentazione. Questo sarà il contenitore in cui aggiungerai la tua grafica SmartArt.

```python
with slides.Presentation() as pres:
```

Utilizzo `with` assicura che le risorse siano gestite correttamente, salvando e chiudendo automaticamente il file all'uscita.

### Passaggio 2: aggiungere SmartArt alla prima diapositiva

Ora aggiungeremo un elemento grafico SmartArt alla prima diapositiva. Ecco come fare:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

In questo modo viene aggiunto un layout di ciclo di base per la grafica SmartArt nella posizione (10, 10) con dimensioni di 400x300 pixel.

### Passaggio 3: accedere al secondo nodo

Accedi a nodi specifici all'interno del tuo SmartArt. In questo esempio, accediamo al secondo nodo:

```python
node = smart.nodes[1]
```

I nodi sono indicizzati a partire da zero; quindi, `nodes[1]` si riferisce al secondo nodo nell'elenco.

### Passaggio 4: recupera la miniatura dell'immagine

Per ottenere un'immagine in miniatura della forma all'interno del nodo selezionato:

```python
image = node.shapes[0].get_image()
```

In questo modo viene recuperata l'immagine della prima forma come miniatura dal nodo SmartArt specificato.

### Passaggio 5: salvare l'immagine recuperata

Infine, salva questa miniatura nella posizione desiderata in formato JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}