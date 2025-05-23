---
"date": "2025-04-22"
"description": "Scopri come creare e personalizzare grafici a torta nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python, migliorando le tue competenze di visualizzazione dei dati."
"title": "Come creare un grafico a torta in PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a torta in PowerPoint utilizzando Aspose.Slides per Python

Creare grafici visivamente accattivanti come il grafico a torta può migliorare significativamente le tue presentazioni PowerPoint, rendendo più comprensibili anche le informazioni più complesse. Questo tutorial ti guiderà nella creazione di un grafico a torta utilizzando Aspose.Slides per Python.

## Cosa imparerai

- Impostazione di Aspose.Slides per Python
- Passaggi per creare una presentazione PowerPoint con un grafico a torta
- Configurazione delle etichette dati e delle opzioni dei gruppi di serie per una migliore leggibilità
- Applicazioni pratiche del grafico a torta nelle presentazioni

Passiamo ora alla configurazione dell'ambiente e all'implementazione di queste funzionalità.

### Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

- **Python installato**: Si consiglia Python 3.6 o versione successiva.
- **Aspose.Slides per Python**: Installa usando pip:
  ```bash
  pip install aspose.slides
  ```
- **Licenza**: Ottieni una licenza di prova gratuita da Aspose per esplorare tutte le funzionalità senza limitazioni.

#### Prerequisiti di conoscenza

Una conoscenza di base della programmazione Python e la comprensione delle presentazioni PowerPoint saranno utili. Se sei alle prime armi, valuta la possibilità di esplorare prima le risorse introduttive.

### Impostazione di Aspose.Slides per Python

Per iniziare a usare Aspose.Slides per Python, segui questi semplici passaggi:

1. **Installazione**: Utilizzare pip per installare la libreria:
   ```bash
   pip install aspose.slides
   ```

2. **Acquisizione della licenza**: 
   - Visita [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per acquistare una licenza o ottenere una prova gratuita temporanea.
   - Applica la tua licenza utilizzando il seguente frammento di codice nel tuo progetto:
     ```python
     import aspose.slides as slides

     # Carica il file di licenza
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Inizializzazione di base**:
   Per iniziare, importare Aspose.Slides e avviare un oggetto di presentazione.

### Guida all'implementazione

#### Funzionalità 1: creare una presentazione con un grafico

Questa funzionalità illustrerà come creare una presentazione PowerPoint e aggiungere un grafico a torta alla prima diapositiva.

##### Aggiungere il grafico

Inizia creando una nuova presentazione e aggiungendo un grafico a torta nella posizione (50, 50) della prima diapositiva:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Aggiungi un grafico a torta con dimensioni specificate
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Configurazione delle etichette dati

Per migliorare la leggibilità, configura le etichette dei dati in modo che visualizzino i valori:

```python
# Abilita la visualizzazione del valore nelle etichette dati per una maggiore chiarezza
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Impostazione delle opzioni di Pie of Pie

Configura proprietà specifiche per il grafico a torta, come la dimensione della seconda torta e la posizione di divisione:

```python
# Imposta la dimensione della seconda torta e le proprietà di suddivisione
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Salvataggio della presentazione

Infine, salva la presentazione nella directory desiderata:

```python
# Salva la presentazione con il grafico
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Applicazioni pratiche

Il grafico a torta è versatile e può essere utilizzato in vari scenari:

1. **Rapporti aziendali**: Visualizza la distribuzione dei dati tra diversi reparti o prodotti.
2. **Progetti accademici**: Presentare i risultati dell'indagine evidenziando i temi principali insieme a risultati meno significativi.
3. **Analisi finanziaria**Confrontare le spese primarie con i costi secondari in un report di budget.

### Considerazioni sulle prestazioni

Per prestazioni ottimali quando si utilizza Aspose.Slides:

- Se possibile, ridurre al minimo il numero di diapositive e grafici per ridurre l'utilizzo di memoria.
- Elimina regolarmente le risorse o i riferimenti inutilizzati nel tuo codice.
- Utilizza la garbage collection integrata di Python (`gc` modulo) per gestire efficacemente la memoria.

### Conclusione

Hai imparato a creare una presentazione PowerPoint con un grafico a torta utilizzando Aspose.Slides per Python. Questa competenza può migliorare notevolmente l'impatto visivo e l'efficacia delle tue presentazioni. Valuta la possibilità di esplorare altre funzionalità di Aspose.Slides, come l'aggiunta di animazioni o l'integrazione di elementi multimediali.

### Prossimi passi

- Prova i diversi tipi di grafici disponibili in Aspose.Slides.
- Integrare questa funzionalità in un flusso di lavoro di automazione delle presentazioni più ampio.

### Sezione FAQ

**D: Posso personalizzare i colori del grafico a torta?**
A: Sì, puoi personalizzare i colori del grafico utilizzando `fill_format` proprietà per ogni segmento.

**D: Come posso gestire set di dati di grandi dimensioni con Aspose.Slides?**
A: Ottimizza l'input dei dati e valuta la possibilità di suddividerli in blocchi più piccoli per mantenere le prestazioni.

**D: Esiste un modo per automatizzare l'aggiunta di più grafici in una sola volta?**
A: Sì, esegui un ciclo attraverso i tuoi set di dati e usa il `add_chart` metodo all'interno di un singolo contesto di presentazione.

### Risorse

- **Documentazione**: Esplora le guide dettagliate su [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/python-net/).
- **Scaricamento**: Ottieni l'ultima versione da [Comunicati stampa](https://releases.aspose.com/slides/python-net/).
- **Acquisto e prova gratuita**: Accedi alle opzioni di licenza su [Acquisto Aspose](https://purchase.aspose.com/buy) o prova un [Prova gratuita](https://releases.aspose.com/slides/python-net/).
- **Supporto**: Partecipa alla discussione su [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}