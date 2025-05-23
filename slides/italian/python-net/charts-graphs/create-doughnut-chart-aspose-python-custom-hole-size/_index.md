---
"date": "2025-04-22"
"description": "Scopri come creare e personalizzare grafici a ciambella in PowerPoint utilizzando Aspose.Slides per Python. Questo tutorial illustra come impostare le dimensioni dei fori, salvare le presentazioni e le best practice."
"title": "Come creare un grafico a ciambella in PowerPoint con dimensioni dei fori personalizzate utilizzando Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare un grafico a ciambella in PowerPoint con dimensioni dei fori personalizzate utilizzando Aspose.Slides per Python

## Introduzione
Creare grafici visivamente accattivanti in PowerPoint può rendere i dati più accattivanti e facili da comprendere. Una sfida comune è la mancanza di opzioni di personalizzazione quando si generano questi grafici a livello di codice. Questo tutorial risolve questo problema mostrando come creare un grafico a ciambella con una dimensione del foro personalizzata utilizzando Aspose.Slides per Python.

**Parole chiave:** Aspose.Slides Python, grafico a ciambella, dimensione del foro personalizzata

### Cosa imparerai:
- Configurazione e utilizzo di Aspose.Slides per Python
- Creare un grafico a ciambella in PowerPoint
- Personalizzazione della dimensione del foro del grafico a ciambella
- Procedure consigliate per il salvataggio e l'esportazione delle presentazioni

## Prerequisiti
Prima di iniziare, assicurati di avere:
- **Python 3.x** installato sul tuo sistema.
- Conoscenza di base dei concetti di programmazione Python.
- IL `aspose.slides` libreria (le istruzioni per l'installazione sono riportate di seguito).

## Impostazione di Aspose.Slides per Python
Per iniziare, installa Aspose.Slides per Python utilizzando pip:

```bash
pip install aspose.slides
```

### Acquisizione della licenza
Aspose offre una prova gratuita che consente di esplorare le sue funzionalità senza limitazioni sul numero di documenti o sul tempo di utilizzo:
- **Prova gratuita:** Inizia con una licenza temporanea per testare tutte le funzionalità.
- **Licenza temporanea:** Disponibile per scopi di valutazione.
- **Acquistare:** Per un utilizzo a lungo termine, si consiglia di acquistare una licenza.

Dopo l'installazione e la configurazione, puoi iniziare a creare presentazioni a livello di codice. Ecco come inizializzare Aspose.Slides:

```python
import aspose.slides as slides

# Inizializzare un oggetto di presentazione
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # Il tuo codice va qui
```

## Guida all'implementazione
In questa sezione vengono descritti i passaggi necessari per creare e personalizzare un grafico a ciambella in PowerPoint utilizzando Aspose.Slides.

### Passaggio 1: accesso e modifica di una diapositiva
Per iniziare, accedi alla prima diapositiva della tua presentazione. È qui che aggiungerai il tuo grafico a ciambella personalizzato.

```python
# Accedi alla prima diapositiva
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### Passaggio 2: aggiunta di un grafico ad anello
È possibile aggiungere un grafico a ciambella a qualsiasi diapositiva specificandone posizione e dimensioni. Qui, lo posizioneremo alle coordinate (50, 50) con dimensioni di 400x400.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # Aggiungi un grafico a ciambella
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### Passaggio 3: personalizzazione della dimensione del foro
Regolare la dimensione del foro del grafico a ciambella è semplice. Impostala al 90% per un effetto più pronunciato.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # Imposta la dimensione personalizzata del foro
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### Passaggio 4: salvataggio della presentazione
Infine, salva la presentazione nella posizione desiderata con il nome file scelto.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # Salva la presentazione
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## Applicazioni pratiche
La creazione di grafici a ciambella personalizzati può essere utile in diversi scenari, tra cui:
- **Rapporti aziendali:** Evidenziare gli indicatori chiave delle prestazioni con segmenti visivamente distinti.
- **Contenuti educativi:** Illustrare dati statistici a studenti o colleghi.
- **Materiali di marketing:** Presentazione di analisi dei prodotti o dati demografici dei clienti.

È possibile integrare i grafici con altri sistemi esportandoli come immagini o incorporandoli in applicazioni web utilizzando l'API completa di Aspose.

## Considerazioni sulle prestazioni
Quando lavori con Aspose.Slides, tieni a mente questi suggerimenti per ottenere prestazioni ottimali:
- Riduci al minimo l'utilizzo delle risorse caricando solo le diapositive necessarie.
- Gestisci la memoria in modo efficace chiudendo subito le presentazioni dopo averle utilizzate.
- Utilizzare l'elaborazione batch per generare più grafici contemporaneamente.

Seguendo le best practice puoi garantire che la tua applicazione funzioni in modo fluido ed efficiente.

## Conclusione
Seguendo questa guida, hai imparato a creare un grafico a ciambella con una dimensione del foro personalizzata in PowerPoint utilizzando Aspose.Slides per Python. Questo non solo migliora l'aspetto visivo delle tue presentazioni, ma consente anche una maggiore flessibilità nella rappresentazione dei dati.

Per esplorare ulteriormente le capacità di Aspose.Slides, prova a sperimentare altri tipi di grafici e funzionalità di presentazione. Buona programmazione!

## Sezione FAQ
1. **Qual è la dimensione massima del foro che posso impostare per un grafico a ciambella?**
   - Per un grafico a cerchio completo è possibile impostarlo fino al 100%.
2. **Posso modificare grafici esistenti in un file PowerPoint utilizzando Aspose.Slides?**
   - Sì, puoi caricare e modificare le presentazioni esistenti.
3. **Come gestisco gli errori durante il salvataggio delle presentazioni?**
   - Assicurarsi che il percorso di output sia scrivibile e verificare la presenza di problemi di autorizzazione.
4. **Sono supportati altri tipi di grafici oltre ai grafici a ciambella?**
   - Certamente, Aspose.Slides supporta un'ampia gamma di tipi di grafici.
5. **Aspose.Slides può essere utilizzato con le applicazioni web?**
   - Sì, la sua API può essere integrata nei sistemi backend ed esposta tramite servizi web.

## Risorse
- [Documentazione](https://reference.aspose.com/slides/python-net/)
- [Scaricamento](https://releases.aspose.com/slides/python-net/)
- [Acquistare](https://purchase.aspose.com/buy)
- [Prova gratuita](https://releases.aspose.com/slides/python-net/)
- [Licenza temporanea](https://purchase.aspose.com/temporary-license/)
- [Forum di supporto](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}