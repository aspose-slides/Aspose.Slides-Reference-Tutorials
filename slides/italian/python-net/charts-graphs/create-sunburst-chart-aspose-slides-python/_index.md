---
"date": "2025-04-23"
"description": "Scopri come creare grafici a raggiera dinamici e visivamente accattivanti utilizzando Aspose.Slides per Python. Segui questa guida passo passo per migliorare le tue presentazioni di dati."
"title": "Come creare grafici a raggiera in Python usando Aspose.Slides"
"url": "/it/python-net/charts-graphs/create-sunburst-chart-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare grafici a raggiera in Python usando Aspose.Slides

## Introduzione
Creare grafici a raggiera visivamente accattivanti è essenziale per una visualizzazione efficace dei dati, soprattutto quando si presentano dati gerarchici. Questo tutorial vi guiderà nell'utilizzo della potente libreria Aspose.Slides con Python per creare grafici a raggiera dinamici adatti a report aziendali e set di dati complessi.

Nell'attuale mondo incentrato sui dati, strumenti come Aspose.Slides semplificano l'integrazione di funzionalità avanzate di creazione di grafici nelle tue applicazioni. Segui questa guida dalla configurazione all'implementazione, per garantire che anche i principianti possano creare grafici a raggiera accattivanti senza sforzo.

**Cosa imparerai:**
- Come configurare Aspose.Slides per Python
- Passaggi per inizializzare una presentazione e aggiungere un grafico a raggiera
- Configurazione di categorie e serie di dati
- Ottimizzazione del grafico sunburst per le prestazioni

Cominciamo con i prerequisiti necessari prima di cominciare!

## Prerequisiti
Prima di iniziare, assicurati di avere quanto segue:
- **Ambiente Python:** Python 3.x installato sul tuo sistema.
- **Libreria Aspose.Slides:** Installa Aspose.Slides per Python tramite pip. Si presuppone la familiarità con i concetti base della programmazione Python.

## Impostazione di Aspose.Slides per Python
Per creare grafici a raggiera, assicurati innanzitutto di aver installato Aspose.Slides nel tuo ambiente:

```bash
pip install aspose.slides
```

### Acquisizione della licenza
Aspose offre una licenza di prova gratuita per esplorare tutte le funzionalità delle sue librerie. Acquista questa licenza temporanea da [Pagina della licenza temporanea di Aspose](https://purchase.aspose.com/temporary-license/)Per un utilizzo a lungo termine, si consiglia di acquistare un abbonamento dalla pagina degli acquisti.

Una volta installato, inizializza la configurazione di Aspose.Slides in Python come segue:

```python
import aspose.slides as slides

def init_aspose():
    # Inizializza un oggetto di presentazione per ulteriori operazioni
    with slides.Presentation() as pres:
        print("Aspose.Slides is ready to use!")
```

## Guida all'implementazione
### Creazione del grafico Sunburst
Analizziamo nel dettaglio i passaggi necessari per creare e configurare un grafico a raggiera utilizzando Aspose.Slides.

#### Passaggio 1: inizializzare un oggetto di presentazione
Per iniziare, crea un nuovo oggetto di presentazione che funga da contenitore per le diapositive e i grafici:

```python
def create_sunburst_chart():
    with slides.Presentation() as pres:
        # In questo modo viene creato un gestore del contesto per gestire il ciclo di vita della presentazione.
```

#### Passaggio 2: aggiungere il grafico Sunburst
Aggiungi un grafico a raggiera alle coordinate specificate nella prima diapositiva. Regolane posizione e dimensioni a seconda delle tue esigenze:

```python
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.SUNBURST, 50, 50, 500, 400)
        
        # Parametri: tipo di grafico, posizione x, posizione y, larghezza, altezza
```

#### Passaggio 3: cancellare i dati esistenti
Prima di popolare il grafico con i dati, cancella tutte le categorie e le serie predefinite per ricominciare da capo:

```python
        chart.chart_data.categories.clear()
        chart.chart_data.series.clear()
        
        # Accedi alla cartella di lavoro per manipolare i dati del grafico
        wb = chart.chart_data.chart_data_workbook
        wb.clear(0)  # Cancella tutte le celle nella cartella di lavoro
```

#### Passaggio 4: configurare categorie e livelli di raggruppamento
Definisci categorie gerarchiche aggiungendo foglie, rami e steli. Utilizza i livelli di raggruppamento per organizzare visivamente i tuoi dati:

```python
        # Configurazione del ramo 1
        leaf = chart.chart_data.categories.add(wb.get_cell(0, "C1", "Leaf1"))
        leaf.grouping_levels.set_grouping_item(1, "Stem1")
        leaf.grouping_levels.set_grouping_item(2, "Branch1")

        # Aggiungere altre foglie sotto il ramo 1
        chart.chart_data.categories.add(wb.get_cell(0, "C2", "Leaf2"))
```

Continuare con questo schema per altri rami e foglie, se necessario.

#### Passaggio 5: aggiungere serie di dati
Crea una serie di dati e inserisci i valori. Questo passaggio collega le categorie ai punti dati corrispondenti:

```python
        series = chart.chart_data.series.add(slides.charts.ChartType.SUNBURST)
        series.labels.default_data_label_format.show_category_name = True
        
        # Aggiunta di punti dati alla serie
        series.data_points.add_data_point_for_sunburst_series(wb.get_cell(0, "D1", 4))
```

#### Passaggio 6: salva la presentazione
Infine, salva la presentazione con il grafico a raggiera appena creato:

```python
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_sunburst_chart_out.pptx", slides.export.SaveFormat.PPTX)
        
        # Assicurati di specificare un percorso di directory di output valido
```

### Suggerimenti per la risoluzione dei problemi
- **Mancata corrispondenza dei dati:** Se i tuoi punti dati non sono allineati con le categorie, ricontrolla le configurazioni delle categorie e delle serie.
- **Il grafico non viene visualizzato:** Verificare che la posizione e le dimensioni del grafico rientrino nei limiti della diapositiva.

## Applicazioni pratiche
I grafici a raggiera eccellono in vari scenari:
1. **Gerarchia organizzativa:** Visualizzare le strutture dipartimentali o le gerarchie di gestione dei progetti.
2. **Analisi della categoria di prodotto:** Mostra i dati di vendita per diverse categorie di prodotti.
3. **Rappresentazione dei dati geografici:** Visualizza la distribuzione della popolazione tra regioni e sottoregioni.

Questi casi d'uso dimostrano la flessibilità dei grafici sunburst nel rappresentare in modo intuitivo informazioni gerarchiche complesse.

## Considerazioni sulle prestazioni
Ottimizza le prestazioni del tuo grafico a raggiera:
- Riduzione dei punti dati non necessari per migliorare la chiarezza.
- Utilizzo di tecniche efficienti di gestione della memoria fornite da Aspose.Slides per Python.

Seguendo queste buone pratiche si garantisce un funzionamento fluido e un rendering reattivo dei grafici.

## Conclusione
Ora hai imparato a creare e configurare grafici a raggiera con Aspose.Slides in Python. Questa potente funzionalità può trasformare le tue presentazioni, rendendo i dati complessi più accessibili e coinvolgenti. Sperimenta ulteriormente integrando ulteriori funzionalità di Aspose.Slides per migliorare le tue applicazioni.

**Prossimi passi:** Esplora l'ampia [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/python-net/) per funzionalità più avanzate e opzioni di personalizzazione.

## Sezione FAQ
**D1: Come posso personalizzare i colori del mio grafico sunburst?**
A1: Usa il `fill_format` proprietà su ciascun punto dati per impostare colori personalizzati, migliorando l'aspetto visivo.

**D2: Posso esportare il grafico come immagine?**
R2: Sì, Aspose.Slides supporta l'esportazione di diapositive e grafici in vari formati come JPEG o PNG.

**D3: Cosa succede se il mio grafico non viene visualizzato correttamente in PowerPoint?**
A3: Assicurati che i valori delle serie di dati siano correttamente mappati alle categorie. Ricontrolla i livelli di raggruppamento per verificarne l'accuratezza.

**D4: È possibile animare il grafico a raggiera?**
A4: Sebbene Aspose.Slides supporti le animazioni, queste devono essere configurate manualmente dopo la creazione del grafico in PowerPoint.

**D5: Come posso gestire set di dati di grandi dimensioni con Aspose.Slides?**
A5: Ottimizza suddividendo i dati in blocchi gestibili e sfruttando l'efficiente gestione della memoria di Python.

## Risorse
- **Documentazione:** [Documentazione Python di Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- **Scaricamento:** [Ultime uscite](https://releases.aspose.com/slides/python-net/)
- **Acquistare:** [Acquista Aspose.Slides](https://purchase.aspose.com/buy)
- **Prova gratuita:** [Prova Aspose.Slides gratuitamente](https://releases.aspose.com/slides/python-net/)
- **Licenza temporanea:** [Richiedi una licenza temporanea](https://purchase.aspose.com/temporary-license/)
- **Supporto:** [Forum di supporto Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}