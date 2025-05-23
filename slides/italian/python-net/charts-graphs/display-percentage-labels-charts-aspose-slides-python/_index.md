---
"date": "2025-04-22"
"description": "Scopri come visualizzare facilmente le etichette percentuali sui grafici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python. Perfetto per migliorare la visualizzazione dei dati."
"title": "Come visualizzare le etichette percentuali sui grafici utilizzando Aspose.Slides per Python&#58; una guida completa"
"url": "/it/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come visualizzare le etichette percentuali sui grafici utilizzando Aspose.Slides per Python

## Introduzione

Visualizzare i dati in modo efficace è fondamentale nelle presentazioni e nei report, soprattutto quando si desidera evidenziare chiaramente proporzioni o distribuzioni. Ma cosa succede se si desidera visualizzare queste percentuali direttamente sui grafici? Questa guida completa vi guiderà nell'utilizzo di **Aspose.Slides per Python** per visualizzare senza sforzo i valori percentuali come etichette su un grafico.

### Cosa imparerai:
- Come creare e incorporare grafici nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python.
- Visualizzare i punti dati come etichette percentuali sui grafici.
- Salvataggio e gestione efficiente delle presentazioni PowerPoint.

Pronti ad aggiungere elementi visivi approfonditi ai vostri dati? Diamo un'occhiata a ciò di cui avete bisogno prima di immergervi nel codice!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:
- **Aspose.Slides per Python**:Questa libreria è essenziale per creare e manipolare le presentazioni di PowerPoint a livello di programmazione.
- **Ambiente Python**: Una conoscenza di base della programmazione Python e della configurazione dell'ambiente.
- **Gestore pacchetti PIP**: Utilizzato per installare Aspose.Slides.

## Impostazione di Aspose.Slides per Python

Per iniziare a utilizzare Aspose.Slides, devi prima installarlo:

```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza:
Puoi iniziare con una prova gratuita o ottenere una licenza temporanea per esplorare tutte le funzionalità di Aspose.Slides. Per un utilizzo prolungato, valuta l'acquisto di un abbonamento.

#### Inizializzazione e configurazione di base

Una volta installato, inizializzerai il tuo ambiente di presentazione come segue:

```python
import aspose.slides as slides

# Inizializza un oggetto Presentazione
def create_presentation():
    with slides.Presentation() as presentation:
        # Il tuo codice qui
```

## Guida all'implementazione

Ora che abbiamo impostato tutto, passiamo alla visualizzazione delle percentuali sui grafici.

### Creazione del grafico e aggiunta dei dati

#### Panoramica
Creeremo un grafico a colonne sovrapposte con etichette percentuali per ogni punto dati, consentendo agli osservatori di vedere le proporzioni esatte a colpo d'occhio.

##### Passaggio 1: aggiungere un grafico alla diapositiva

```python
# Accedi alla prima diapositiva della tua presentazione
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Aggiungere un grafico a colonne impilate
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Questo frammento di codice aggiunge un grafico di base alla prima diapositiva. `add_chart` Il metodo specifica il tipo di grafico, la sua posizione e dimensione.

##### Passaggio 2: calcolare i valori totali per le categorie

```python
def calculate_totals(chart):
    total_for_category = []
    # Sommare i valori di tutte le serie per ogni categoria
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Questo ciclo calcola il totale di tutti i punti dati delle serie, il che è fondamentale per i calcoli percentuali.

#### Impostazione delle etichette percentuali

##### Passaggio 3: configurare i punti dati della serie

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Imposta le opzioni predefinite delle etichette per nascondere le informazioni non essenziali
        series.labels.default_data_label_format.show_legend_key = False
        
        # Calcola e imposta le etichette percentuali
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Crea una porzione di testo con il valore percentuale
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Cancella le etichette esistenti e aggiungi una nuova etichetta percentuale
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Nascondi altri elementi dell'etichetta dati
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Questo segmento elabora ogni punto dati per calcolare la sua percentuale sul totale e gli assegna un'etichetta.

### Salvataggio della presentazione

```python
def save_presentation(presentation, output_directory):
    # Salva la presentazione con le modifiche
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}