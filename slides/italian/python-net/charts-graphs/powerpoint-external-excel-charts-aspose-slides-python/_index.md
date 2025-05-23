---
"date": "2025-04-23"
"description": "Scopri come integrare grafici Excel dinamici nelle tue presentazioni PowerPoint utilizzando Aspose.Slides per Python. Crea facilmente diapositive basate sui dati per uso aziendale e didattico."
"title": "Crea presentazioni PowerPoint con grafici Excel esterni utilizzando Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/powerpoint-external-excel-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Crea PowerPoint con grafici Excel esterni utilizzando Aspose.Slides per Python

## Come integrare grafici Excel nelle presentazioni PowerPoint utilizzando Aspose.Slides per Python

### Introduzione
Creare presentazioni dinamiche è fondamentale per riunioni di lavoro, lezioni formative e progetti personali. Una sfida comune che gli sviluppatori devono affrontare è integrare perfettamente fonti di dati esterne, come file Excel, nelle presentazioni. Questo tutorial affronta questo problema mostrando come utilizzare **Aspose.Slides per Python** per creare presentazioni PowerPoint con grafici provenienti da una cartella di lavoro esterna.

Alla fine di questa guida imparerai:
- Come copiare file di cartelle di lavoro esterne utilizzando Python
- Come creare e configurare una presentazione in Aspose.Slides
- Come impostare grafici che estraggono i dati direttamente dalle cartelle di lavoro di Excel

Cominciamo subito ad analizzare i prerequisiti!

## Prerequisiti

### Librerie, versioni e dipendenze richieste
Per seguire questo tutorial, avrai bisogno di:
- **Pitone** installato sul tuo computer (versione 3.6 o successiva)
- IL `shutil` libreria per operazioni sui file (integrata in Python)
- **Aspose.Slides per Python**una potente libreria per creare e modificare presentazioni PowerPoint

### Requisiti di configurazione dell'ambiente
Assicurati di aver impostato le directory necessarie:
1. Una directory di origine contenente la cartella di lavoro di Excel (`charts_external_workbook.xlsx`)
2. Una directory di output in cui verranno salvati i file copiati e la presentazione generata

### Prerequisiti di conoscenza
È richiesta una conoscenza di base della programmazione Python, inclusa la gestione dei file e l'uso delle librerie.

## Impostazione di Aspose.Slides per Python
Per iniziare a usare Aspose.Slides, è necessario installarlo tramite pip:
```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza
Aspose offre diverse opzioni di licenza, dalla prova gratuita alle licenze temporanee e complete. Puoi iniziare richiedendo un [licenza di prova gratuita](https://purchase.aspose.com/temporary-license/) per esplorarne le caratteristiche.

#### Inizializzazione e configurazione di base
Una volta installato, puoi importare Aspose.Slides nel tuo script:
```python
import aspose.slides as slides
```

Ciò prepara il terreno per integrare senza problemi fonti di dati esterne nelle presentazioni.

## Guida all'implementazione

### Funzionalità: Copia cartella di lavoro esterna
**Panoramica:**
Per prima cosa, mostreremo come copiare un file di cartella di lavoro esterno da una directory di origine a una directory di output di destinazione utilizzando Python `shutil` modulo. Ciò garantisce che la presentazione abbia accesso ai dati necessari.

#### Passaggio 1: importare le librerie richieste
```python
import shutil
```

#### Passaggio 2: definire i percorsi dei file e copiare la cartella di lavoro
```python
external_workbook_file_name = "charts_external_workbook.xlsx"
source_path = "YOUR_DOCUMENT_DIRECTORY/" + external_workbook_file_name
output_path = "YOUR_OUTPUT_DIRECTORY/" + external_workbook_file_name
shutil.copyfile(source_path, output_path)
```
Questo frammento copia `charts_external_workbook.xlsx` dalla directory dei documenti alla directory di output.

### Funzionalità: crea una presentazione e imposta una cartella di lavoro esterna per i dati del grafico
**Panoramica:**
Successivamente, creeremo una presentazione e imposteremo una cartella di lavoro esterna come origine dati per un grafico utilizzando Aspose.Slides. Questo consente di visualizzare i dati di Excel direttamente nelle diapositive di PowerPoint.

#### Passaggio 1: importa Aspose.Slides
```python
import aspose.slides as slides
```

#### Passaggio 2: definire la funzione di creazione della presentazione
```python
def create_presentation_with_external_chart():
    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.PIE, 50, 50, 400, 600, False)
        
        chart_data = chart.chart_data
        chart_data.set_external_workbook("YOUR_OUTPUT_DIRECTORY/charts_external_workbook.xlsx")
        
        series = chart_data.series.add(chart_data.chart_data_workbook.get_cell(0, "B1"), slides.charts.ChartType.PIE)
        
        # Aggiungere punti dati per la serie di torte da celle di cartelle di lavoro esterne
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B2"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B3"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B4"))

        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A2"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A3"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A4"))
        
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_set_external_workbook_out.pptx", slides.export.SaveFormat.PPTX)
```

#### Spiegazione:
- **Crea una presentazione**Iniziamo aprendo un nuovo oggetto di presentazione.
- **Aggiungi grafico**: Un grafico a torta viene aggiunto alla prima diapositiva in base alle coordinate e alle dimensioni specificate.
- **Imposta cartella di lavoro esterna**: Il percorso della cartella di lavoro è impostato in modo che Aspose.Slides sappia da dove estrarre i dati.
- **Aggiungi serie e punti dati**:Configuriamo le serie con celle specifiche dalla cartella di lavoro esterna, abilitando gli aggiornamenti dinamici.

#### Suggerimenti per la risoluzione dei problemi:
- Assicurati che i percorsi dei file siano corretti; in caso contrario, verranno visualizzati errori di file non trovato.
- Verifica che i riferimenti alle celle nel file Excel corrispondano a quelli utilizzati nel codice per evitare problemi di disallineamento dei dati.

## Applicazioni pratiche
Ecco alcune applicazioni pratiche dell'integrazione di Aspose.Slides con cartelle di lavoro esterne:
1. **Rapporti finanziari**: Aggiorna automaticamente i grafici nelle presentazioni trimestrali in base ai fogli di calcolo finanziari più recenti.
2. **Presentazioni basate sui dati**: Integra perfettamente l'analisi in tempo reale nelle proposte di vendita o negli aggiornamenti dei progetti.
3. **Materiali didattici**:Gli insegnanti possono utilizzare i dati aggiornati sulle prestazioni degli studenti per creare report personalizzati.
4. **Sistemi di reporting automatizzati**: Implementare sistemi automatizzati che generano e distribuiscono presentazioni basate sui nuovi dati immessi.

## Considerazioni sulle prestazioni
### Ottimizzazione delle prestazioni
- Per tempi di accesso più rapidi, utilizza percorsi di file efficienti e assicurati che la tua cartella di lavoro non sia eccessivamente grande.
- Limitare il numero di diapositive con fonti dati esterne per ridurre i tempi di elaborazione.

### Linee guida per l'utilizzo delle risorse
- Monitorare regolarmente l'utilizzo della memoria, soprattutto quando si gestiscono grandi set di dati o più presentazioni contemporaneamente.

### Migliori pratiche per la gestione della memoria
- Eliminare correttamente gli oggetti utilizzando i gestori di contesto (`with` istruzioni) per liberare risorse subito dopo l'uso.

## Conclusione
Integrando Aspose.Slides per Python nel tuo flusso di lavoro, puoi creare presentazioni PowerPoint dinamiche e basate sui dati senza sforzo. Questo tutorial ha trattato gli elementi essenziali per copiare cartelle di lavoro esterne e configurare grafici con origini dati in tempo reale. Per migliorare ulteriormente le tue competenze, valuta la possibilità di esplorare le funzionalità aggiuntive offerte da Aspose.Slides, come le transizioni delle diapositive o gli effetti di animazione.

Pronti a fare un ulteriore passo avanti? Provate a implementare queste tecniche nel vostro prossimo progetto!

## Sezione FAQ
1. **Come faccio a installare Aspose.Slides per Python?**
   - Utilizzare il comando pip: `pip install aspose.slides`.
2. **Posso utilizzare Aspose.Slides con altre origini dati oltre a Excel?**
   - Sì, Aspose.Slides supporta vari formati di dati, anche se questo tutorial si concentra sulle cartelle di lavoro di Excel.
3. **Cosa succede se il mio grafico non viene visualizzato correttamente nella presentazione?**
   - Ricontrolla i riferimenti alle celle e assicurati che la cartella di lavoro esterna sia accessibile in fase di esecuzione.
4. **Come posso ottenere una licenza temporanea per Aspose.Slides?**
   - Visita [Pagina delle licenze di Aspose](https://purchase.aspose.com/temporary-license/) per richiedere una licenza temporanea.
5. **Esistono limitazioni all'utilizzo delle funzionalità di prova gratuite di Aspose.Slides?**
   - La versione di prova gratuita potrebbe presentare alcune restrizioni d'uso, come ad esempio l'aggiunta di filigrane nei file esportati.

## Risorse
- [Documentazione di Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Scarica Aspose.Slides per Python](https://releases.aspose.com/slides/python-net/)
- [Acquista una licenza](https://purchase.aspose.com/slides)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}