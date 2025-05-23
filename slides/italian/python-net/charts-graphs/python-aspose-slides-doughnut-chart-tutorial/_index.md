---
"date": "2025-04-22"
"description": "Scopri come creare grafici a ciambella con Python e Aspose.Slides. Questa guida passo passo illustra la configurazione, la personalizzazione e le best practice per migliorare le tue presentazioni."
"title": "Come creare grafici ad anello in Python usando Aspose.Slides&#58; una guida passo passo"
"url": "/it/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici ad anello in Python usando Aspose.Slides: una guida passo passo

Nell'ambito della visualizzazione dei dati, presentare efficacemente le informazioni può avere un impatto significativo sulla comprensione e sul processo decisionale. Che si tratti di creare una presentazione aziendale o di analizzare set di dati complessi, i grafici sono strumenti essenziali. Tra i vari tipi di grafico, i grafici a ciambella offrono un modo accattivante per rappresentare dati proporzionali con un foro centrale intuitivo. Questa guida passo passo vi guiderà nella creazione di un grafico a ciambella in Python utilizzando Aspose.Slides, una potente libreria per la gestione delle presentazioni.

## Cosa imparerai
- Come configurare e utilizzare Aspose.Slides per Python
- Il processo di aggiunta di un grafico a ciambella alle diapositive della presentazione
- Personalizzazione di serie e categorie all'interno del grafico
- Regolazione di elementi visivi come etichette, colori ed effetti di esplosione
- Best practice per ottimizzare le prestazioni con Aspose.Slides

## Prerequisiti
Prima di iniziare, assicurati di avere:
- **Ambiente Python**: Python 3.x installato sul tuo computer.
- **Aspose.Slides per Python**: Installa questa libreria usando pip.
- **Nozioni di base sulla programmazione Python**: Sarà utile avere familiarità con i cicli e la programmazione orientata agli oggetti.

## Impostazione di Aspose.Slides per Python
Per iniziare, installa la libreria Aspose.Slides tramite pip:

```bash
pip install aspose.slides
```

### Acquisizione della licenza
Aspose offre una prova gratuita per testare le funzionalità senza limitazioni per un periodo di tempo limitato. Per ottenerla:
1. Visita il [Prova gratuita](https://releases.aspose.com/slides/python-net/) pagina.
2. Segui le istruzioni per scaricare e applicare la tua licenza temporanea.

Per un utilizzo continuato, si consiglia di acquistare un abbonamento da [Pagina di acquisto](https://purchase.aspose.com/buy).

### Inizializzazione di base
Dopo aver configurato Aspose.Slides, inizializzalo come segue:

```python
import aspose.slides as slides

# Creare un'istanza della classe Presentation.
with slides.Presentation() as pres:
    # Qui va inserito il codice per manipolare le presentazioni.

# Dopo aver apportato le modifiche, salvare la presentazione.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Guida all'implementazione
Una volta configurato Aspose.Slides, segui questi passaggi per aggiungere un grafico a ciambella alla tua presentazione, diapositiva per diapositiva.

### Creazione di una nuova presentazione e aggiunta di una diapositiva
Inizia creando un'istanza di `Presentation` classe:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Accedi o crea diapositive in questo contesto.
```

### Aggiungere un grafico a ciambella alla prima diapositiva
Accedi alla prima diapositiva e usa il `add_chart` metodo. Specificare il tipo di grafico come `DOUGHNUT`, insieme a posizione e dimensione:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Configurazione dei dati del grafico
Cancella i dati esistenti e configura le impostazioni come nascondere la legenda:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Aggiunta di serie e categorie
Aggiungi più serie e categorie per un grafico a ciambella. Ecco come creare 15 serie con proprietà specifiche:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Aggiungi categorie in modo simile:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Aggiungere punti dati per ogni serie.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Personalizza l'aspetto di ogni punto dati.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Configurare le impostazioni delle etichette per l'ultima serie.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Salvataggio della presentazione
Infine, salva la presentazione in una directory specificata:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Applicazioni pratiche
grafici ad anello sono versatili e possono essere utilizzati in vari scenari, ad esempio:
1. **Assegnazione del bilancio**: Mostra come i diversi dipartimenti utilizzano i fondi assegnati.
2. **Analisi della quota di mercato**:Confronto delle quote di mercato di prodotti o aziende concorrenti.
3. **Risultati del sondaggio**: Visualizzazione delle risposte alle domande del sondaggio sulle preferenze o sui livelli di soddisfazione.

## Considerazioni sulle prestazioni
Per garantire prestazioni ottimali durante l'utilizzo di Aspose.Slides:
- Ridurre al minimo l'utilizzo della memoria smaltire correttamente gli oggetti dopo l'uso.
- Caricare le presentazioni in memoria solo quando necessario e chiuderle il prima possibile.
- Se si lavora con un gran numero di grafici, si può prendere in considerazione l'elaborazione in batch delle diapositive.

## Conclusione
Seguendo questa guida, hai imparato a creare grafici a ciambella dinamici utilizzando Aspose.Slides per Python. Queste visualizzazioni possono migliorare le tue presentazioni rendendo i dati più comprensibili e coinvolgenti. Continua a esplorare le funzionalità della libreria per personalizzare e ottimizzare ulteriormente i tuoi grafici.

## Sezione FAQ
1. **Posso utilizzare Aspose.Slides senza acquistare una licenza?**
   - Sì, puoi iniziare con una licenza di prova gratuita a scopo di valutazione.
2. **Come posso cambiare i colori dei grafici in Aspose.Slides?**
   - Utilizzare il `fill_format` proprietà per impostare il colore desiderato per gli elementi del grafico.
3. **È possibile esportare i grafici come immagini?**
   - Sì, è possibile convertire le diapositive contenenti grafici in formati immagine utilizzando le funzionalità di rendering della libreria.
4. **Quali sono alcuni problemi comuni quando si aggiungono grafici?**
   - Prima di tentare di salvare o visualizzare il grafico, assicurarsi che tutti i punti dati e le categorie siano stati aggiunti correttamente.
5. **Posso integrare Aspose.Slides con altre librerie Python?**
   - Assolutamente! Puoi usarlo insieme a librerie come Pandas per migliorare le capacità di manipolazione dei dati.

## Risorse
- [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Scarica Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Acquista una licenza](https://purchase.aspose.com/buy)
- [Prova gratuita e licenza temporanea](https://releases.aspose.com/slides/python-net/)
- [Forum della comunità Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}