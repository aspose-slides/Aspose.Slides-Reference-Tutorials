---
"date": "2025-04-23"
"description": "Scopri come migliorare le tue presentazioni PowerPoint con grafici dinamici utilizzando Aspose.Slides per Python. Segui questa guida passo passo per creare, gestire e formattare grafici a colonne raggruppate in modo efficace."
"title": "Crea e formatta grafici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/create-charts-presentation-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea e formatta grafici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python

## Introduzione

Nell'attuale mondo basato sui dati, integrare grafici visivamente accattivanti nelle presentazioni è fondamentale per una comunicazione efficace. Che siate analisti di dati, project manager o professionisti del settore, i grafici dinamici possono migliorare significativamente il vostro messaggio. Questo tutorial vi guiderà nella creazione e formattazione di grafici a colonne raggruppate utilizzando Aspose.Slides per Python, consentendovi di valorizzare le vostre diapositive di PowerPoint senza sforzo.

**Cosa imparerai:**
- Come installare e configurare Aspose.Slides per Python
- Crea una nuova presentazione e aggiungi un grafico a colonne raggruppate
- Gestisci serie di dati e categorie all'interno del grafico
- Popola e formatta i dati delle serie per una migliore visualizzazione

Pronti a migliorare le vostre presentazioni? Scopriamo come sfruttare Aspose.Slides per creare grafici accattivanti.

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- **Python installato:** Si consiglia la versione 3.6 o superiore.
- **Pacchetto Aspose.Slides per Python:** Installa questo pacchetto usando pip.
- **Conoscenza di base della programmazione Python:** Sarà utile avere familiarità con la sintassi Python e con la gestione dei file.

## Impostazione di Aspose.Slides per Python

Per iniziare, è necessario installare la libreria Aspose.Slides. Questo potente strumento semplifica la creazione e la modifica di presentazioni PowerPoint in Python.

### Installazione

Eseguire il seguente comando per installare il pacchetto:

```bash
pip install aspose.slides
```

### Acquisizione della licenza

Aspose offre una licenza di prova gratuita che consente di esplorare tutte le sue funzionalità senza limitazioni. Segui questi passaggi per ottenerla:

1. Visita [Prova gratuita di Aspose](https://releases.aspose.com/slides/python-net/) per scaricare il pacchetto di prova.
2. In alternativa, richiedi una licenza temporanea tramite [Pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

Una volta ottenuto il file di licenza, inizializzalo nello script Python:

```python
from aspose.slides import License

# Imposta la licenza di Aspose.Slides
license = License()
license.set_license("path/to/your/license/file.lic")
```

## Guida all'implementazione

Suddivideremo il processo in tre funzionalità principali: creazione di grafici, gestione di serie di dati e categorie e compilazione e formattazione di serie di dati.

### Funzionalità 1: creazione e aggiunta di un grafico a una presentazione

#### Panoramica

Questa funzionalità si concentra sull'aggiunta di un grafico a colonne raggruppate alla presentazione utilizzando Aspose.Slides per Python.

#### Implementazione passo dopo passo

```python
import aspose.slides as slides

def create_and_add_chart():
    with slides.Presentation() as pres:
        # Aggiungere un grafico a colonne raggruppate nella posizione (100, 100) con larghezza 400 e altezza 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        # Salva la presentazione in un file nella directory di output.
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_creation_out.pptx", slides.export.SaveFormat.PPTX)

create_and_add_chart()
```

**Spiegazione:**
- **Posizione e dimensione del grafico:** IL `add_chart` Il metodo viene utilizzato con parametri che specificano il tipo di grafico, la posizione (x,y), la larghezza e l'altezza.
- **Salvataggio della presentazione:** La presentazione viene salvata in una directory specificata.

### Funzionalità 2: Gestione di serie di dati e categorie di grafici

#### Panoramica

In questa sezione viene illustrato come gestire in modo efficace le serie di dati e le categorie all'interno del grafico.

#### Implementazione passo dopo passo

```python
import aspose.slides as slides

def manage_chart_data_series_and_categories():
    with slides.Presentation() as pres:
        # Aggiungere un grafico a colonne raggruppate nella posizione (100, 100) con larghezza 400 e altezza 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Cancella le serie e le categorie esistenti prima di aggiungerne di nuove.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Aggiunta di una nuova serie denominata "Serie 1" al grafico.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Aggiunta di tre categorie ai dati del grafico.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Salva la presentazione in un file nella directory di output.
        pres.save("YOUR_OUTPUT_DIRECTORY/chart_series_categories_out.pptx", slides.export.SaveFormat.PPTX)

manage_chart_data_series_and_categories()
```

**Spiegazione:**
- **Cancellazione dei dati esistenti:** Prima di aggiungere nuove serie e categorie, quelle esistenti vengono cancellate per evitare la duplicazione dei dati.
- **Aggiunta di serie e categorie:** Nuove serie e categorie vengono aggiunte utilizzando `chart_data_workbook` oggetto.

### Funzionalità 3: Popolamento dei dati della serie e formattazione del grafico

#### Panoramica

In questa funzionalità, popoleremo il tuo grafico con punti dati e applicheremo la formattazione per migliorarne l'aspetto visivo.

#### Implementazione passo dopo passo

```python
import aspose.slides as slides
import aspose.pydrawing as drawing

def populate_and_format_series_data():
    with slides.Presentation() as pres:
        # Aggiungere un grafico a colonne raggruppate nella posizione (100, 100) con larghezza 400 e altezza 300.
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 100, 100, 400, 300
        )
        
        workbook = chart.chart_data.chart_data_workbook
        
        # Cancella le serie e le categorie esistenti prima di aggiungerne di nuove.
        chart.chart_data.series.clear()
        chart.chart_data.categories.clear()
        
        # Aggiunta di una nuova serie denominata "Serie 1" al grafico.
        chart.chart_data.series.add(
            workbook.get_cell(0, 0, 1, "Series 1"), chart.type
        )
        
        # Aggiunta di tre categorie ai dati del grafico.
        chart.chart_data.categories.add(workbook.get_cell(0, 1, 0, "Category 1"))
        chart.chart_data.categories.add(workbook.get_cell(0, 2, 0, "Category 2"))
        chart.chart_data.categories.add(workbook.get_cell(0, 3, 0, "Category 3"))
        
        # Prendiamo la prima serie di grafici e la riempiamo con i punti dati.
        series = chart.chart_data.series[0]
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 1, 1, -20)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 2, 1, 50)
        )
        series.data_points.add_data_point_for_bar_series(
            workbook.get_cell(0, 3, 1, -30)
        )
        
        # Imposta il colore per i valori negativi in serie.
        invert_color = drawing.Color.red
        series.invert_if_negative = True
        series.format.fill.fill_type = slides.FillType.SOLID
        series.format.fill.solid_fill_color.color = series.get_automatic_series_color()
        series.inverted_solid_fill_color.color = invert_color
        
        # Salva la presentazione in un file nella directory di output.
        pres.save("YOUR_OUTPUT_DIRECTORY/populate_format_series_out.pptx", slides.export.SaveFormat.PPTX)

populate_and_format_series_data()
```

**Spiegazione:**
- **Aggiunta di punti dati:** I punti dati vengono aggiunti utilizzando `add_data_point_for_bar_series`.
- **Formattazione dei valori negativi:** Le opzioni di formattazione dei grafici, come l'inversione dei colori per i valori negativi, migliorano la leggibilità dei dati.

## Applicazioni pratiche

L'utilizzo di Aspose.Slides per aggiungere e formattare grafici nelle presentazioni ha numerose applicazioni:

1. **Rapporti aziendali:** Arricchisci i report trimestrali con elementi visivi dinamici che trasmettono in modo chiaro i parametri chiave.
2. **Materiale didattico:** Crea contenuti didattici coinvolgenti rappresentando visivamente informazioni complesse.
3. **Presentazioni del progetto:** Utilizzare grafici per illustrare in modo efficace i progressi e i risultati del progetto.

Seguendo questa guida, puoi sfruttare Aspose.Slides per Python per creare presentazioni d'impatto che si distinguono.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}