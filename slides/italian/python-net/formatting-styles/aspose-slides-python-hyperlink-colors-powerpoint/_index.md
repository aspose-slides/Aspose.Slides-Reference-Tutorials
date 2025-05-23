---
"date": "2025-04-23"
"description": "Scopri come personalizzare i colori dei collegamenti ipertestuali nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python. Migliora le tue diapositive con stili di collegamento personalizzati in modo efficiente."
"title": "Come impostare i colori dei collegamenti ipertestuali in PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare i colori dei collegamenti ipertestuali in PowerPoint utilizzando Aspose.Slides per Python

## Introduzione

Migliorare l'aspetto visivo delle presentazioni PowerPoint personalizzando i colori dei collegamenti ipertestuali è semplice con Aspose.Slides per Python. Questa guida ti guiderà nell'impostazione di collegamenti ipertestuali con colori specifici nelle tue diapositive utilizzando Python.

**Cosa imparerai:**
- Come impostare un colore per i collegamenti ipertestuali all'interno di forme di testo in PowerPoint.
- Fasi della creazione di una presentazione visivamente accattivante.
- Funzionalità principali di Aspose.Slides per Python che facilitano questa personalizzazione.

Analizziamo ora i prerequisiti necessari prima di iniziare.

## Prerequisiti

Prima di iniziare, assicurati che l'ambiente sia pronto con quanto segue:
- **Librerie e versioni:** Installare `aspose.slides` libreria. Assicurati che Python sia installato sul tuo computer.
- **Requisiti di configurazione dell'ambiente:** Questo tutorial presuppone una configurazione di base di Python su Windows, Mac o Linux.
- **Prerequisiti di conoscenza:** Sarà utile avere familiarità con la programmazione Python.

## Impostazione di Aspose.Slides per Python

Per iniziare a utilizzare Aspose.Slides per Python, installa il pacchetto tramite pip:

```bash
pip install aspose.slides
```

**Fasi di acquisizione della licenza:**
- **Prova gratuita:** Scarica una versione di prova da [Pagina di rilascio di Aspose](https://releases.aspose.com/slides/python-net/).
- **Licenza temporanea:** Richiedi una licenza temporanea su [pagina di acquisto](https://purchase.aspose.com/temporary-license/) per un accesso esteso.
- **Acquistare:** Per sbloccare completamente le funzionalità senza limitazioni, prendi in considerazione l'acquisto di una licenza da [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

**Inizializzazione di base:**
Una volta installato e ottenuto il titolo, importa Aspose.Slides nel tuo script:

```python
import aspose.slides as slides
```

## Guida all'implementazione

Questa sezione illustra come impostare i colori dei collegamenti ipertestuali in una presentazione di PowerPoint.

### Imposta la funzione Colore collegamento ipertestuale

#### Panoramica

Personalizza il colore dei collegamenti ipertestuali incorporati nelle forme di testo utilizzando Aspose.Slides per Python. Questo migliora la leggibilità e l'aspetto visivo.

##### Passaggio 1: creare una nuova presentazione

Crea un'istanza di una presentazione:

```python
with slides.Presentation() as presentation:
    # Il tuo codice qui
```

##### Passaggio 2: aggiungere una forma con testo

Aggiungere una forma rettangolare alla prima diapositiva e inserire del testo che includa un collegamento ipertestuale.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Passaggio 3: impostare le proprietà del collegamento ipertestuale

Assegna il collegamento ipertestuale e impostane il colore. `hyperlink_click` La proprietà specifica dove deve essere indirizzato il collegamento quando si fa clic.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Imposta la sorgente colore per il collegamento ipertestuale sul formato porzione e definisci il tipo e il colore di riempimento.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Passaggio 4: salva la presentazione

Salva la presentazione in una directory specificata:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}