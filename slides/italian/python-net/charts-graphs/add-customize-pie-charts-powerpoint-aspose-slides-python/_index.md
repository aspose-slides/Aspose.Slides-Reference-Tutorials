---
"date": "2025-04-22"
"description": "Scopri come aggiungere e personalizzare grafici a torta nelle presentazioni di PowerPoint utilizzando Aspose.Slides per Python. Risparmia tempo e garantisci coerenza con questa guida passo passo."
"title": "Come aggiungere e personalizzare grafici a torta in PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/add-customize-pie-charts-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come aggiungere e personalizzare grafici a torta in PowerPoint utilizzando Aspose.Slides per Python

## Introduzione
Creare presentazioni visivamente accattivanti è fondamentale, soprattutto quando si devono trasmettere dati complessi in modo sintetico. Che si tratti di report finanziari o di indicatori di performance, i grafici a torta possono essere uno strumento efficace per illustrare le proporzioni a colpo d'occhio. Tuttavia, aggiungere manualmente questi grafici alle diapositive può richiedere molto tempo ed essere soggetto a incongruenze.

Con la libreria Python Aspose.Slides, automatizzare questo processo diventa semplice. Questo tutorial ti guiderà nell'utilizzo di Aspose.Slides per Python per aggiungere e personalizzare senza sforzo grafici a torta nelle presentazioni di PowerPoint. Seguendo le istruzioni, non solo risparmierai tempo, ma garantirai anche uniformità tra le tue diapositive.

**Cosa imparerai:**
- Come aggiungere un grafico a torta a una diapositiva
- Impostazione del titolo e centratura del testo su un grafico a torta
- Configurazione di serie di dati e categorie per approfondimenti dettagliati
- Abilitazione delle variazioni automatiche del colore per sezioni distinte

Vediamo come implementare queste funzionalità in modo efficace. Prima di iniziare, assicurati che il tuo ambiente sia configurato correttamente.

## Prerequisiti
Per seguire questo tutorial, avrai bisogno di:
- Python installato sul tuo computer (versione 3.x consigliata)
- La libreria Aspose.Slides per Python
- Conoscenza di base della programmazione Python e delle presentazioni PowerPoint

Assicurati di avere la configurazione necessaria per eseguire gli script Python. In caso contrario, valuta la possibilità di installare Python da [python.org](https://www.python.org/downloads/).

## Impostazione di Aspose.Slides per Python
Per iniziare a utilizzare Aspose.Slides nel tuo progetto, installalo tramite pip:

```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza
Aspose offre una prova gratuita della sua libreria. Puoi scaricare una licenza temporanea per esplorare tutte le funzionalità senza limitazioni. Per iniziare:
- Visita [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per le opzioni di acquisto.
- Ottieni una licenza temporanea tramite il [Pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).

### Inizializzazione di base
Ecco come puoi inizializzare Aspose.Slides nel tuo script Python:

```python
import aspose.slides as slides

# Inizializza la classe Presentazione per creare o aprire un file di presentazione
with slides.Presentation() as presentation:
    # Il tuo codice va qui
    pass
```

Con questa configurazione, sei pronto per iniziare ad aggiungere grafici a torta alle tue presentazioni.

## Guida all'implementazione

### Aggiungere un grafico a torta a una diapositiva
#### Panoramica
L'aggiunta di un grafico a torta di base comporta la creazione di una nuova forma di tipo `Chart` sulla diapositiva. Questa sezione ti guiderà attraverso i passaggi per aggiungere un grafico a torta predefinito.

#### Passi
1. **Accedi alla prima diapositiva**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Aggiungi forma grafico a torta**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

   - Parametri: `ChartType.PIE` specifica il tipo di grafico.
   - Le coordinate e le dimensioni definiscono la posizione e le dimensioni del grafico a torta.

3. **Salva presentazione**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_add_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Impostazione del titolo del grafico a torta e del testo centrale
#### Panoramica
Personalizzare il grafico a torta con un titolo ne migliora la leggibilità e fornisce contesto a chi lo visualizza.

#### Passi
1. **Accedi alla prima diapositiva**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Aggiungi grafico e imposta titolo**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   # Titolo dell'impostazione
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

3. **Salva presentazione**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_set_pie_chart_title_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Configurazione di serie di dati e categorie di grafici a torta
#### Panoramica
Per rendere informativo il tuo grafico a torta, devi inserirvi dati reali.

#### Passi
1. **Accedi alla prima diapositiva**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Configurare i dati**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   fact = chart.chart_data.chart_data_workbook
   
   # Cancella i dati esistenti
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()
   
   # Aggiungi categorie e serie con punti dati
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   
   # Aggiungi punti dati
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(0, 3, 1, 30))
   ```

3. **Salva presentazione**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_configure_pie_chart_data_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Abilitazione automatica dei colori delle sezioni del grafico a torta
#### Panoramica
Migliorare l'aspetto visivo variando automaticamente i colori delle sezioni può rendere il grafico più accattivante.

#### Passi
1. **Accedi alla prima diapositiva**
   
   ```python
   slide = presentation.slides[0]
   ```

2. **Abilita variazione colore**
   
   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   
   series = chart.chart_data.series[0]
   series.parent_series_group.is_color_varied = True
   ```

3. **Salva presentazione**
   
   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_enable_automatic_pie_slice_colors_out.pptx", slides.export.SaveFormat.PPTX)
   ```

## Applicazioni pratiche
1. **Rapporti aziendali**: Utilizzare grafici a torta per mostrare la distribuzione delle quote di mercato tra i concorrenti.
2. **Materiali didattici**: Illustrare le percentuali dei diversi argomenti trattati in un programma didattico.
3. **Analisi finanziaria**: Visualizza le categorie di spesa come proporzioni del budget totale.
4. **Approfondimenti di marketing**: Visualizza la segmentazione dei clienti in base a dati demografici o preferenze.

L'integrazione con strumenti di analisi dei dati come Pandas può automatizzare ulteriormente il processo, rendendo possibili aggiornamenti in tempo reale all'interno delle presentazioni.

## Considerazioni sulle prestazioni
Quando si lavora con Aspose.Slides e Python:
- Ottimizza il tuo codice per gestire la memoria in modo efficiente, soprattutto quando hai a che fare con set di dati di grandi dimensioni.
- Evitare operazioni ridondanti sugli oggetti di presentazione.
- Utilizzo `with` istruzioni per la gestione del contesto per garantire che le risorse vengano liberate in modo appropriato dopo l'uso.

## Conclusione
Ora hai una conoscenza approfondita di come creare e personalizzare grafici a torta in PowerPoint utilizzando Aspose.Slides per Python. Automatizzando queste attività, puoi migliorare significativamente la produttività, garantendo al contempo la coerenza delle tue presentazioni. 

Per approfondire ulteriormente, prova ad integrare fonti di dati dinamiche o ad automatizzare la generazione di intere serie di diapositive.

## Consigli per le parole chiave
- "Aspose.Slides per Python"
- "Grafico a torta di PowerPoint"
- "automatizzare i grafici di PowerPoint con Python"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}