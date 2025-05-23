---
"date": "2025-04-23"
"description": "Scopri come regolare l'angolo di rotazione dei titoli dei grafici nelle presentazioni utilizzando Aspose.Slides per Python, migliorando la leggibilità e l'estetica."
"title": "Come impostare la rotazione del titolo sull'asse verticale di un grafico in Aspose.Slides per Python"
"url": "/it/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come impostare la rotazione del titolo sull'asse verticale di un grafico in Aspose.Slides per Python

## Introduzione

Nelle presentazioni di dati, migliorare la leggibilità dei grafici è fondamentale. Regolare l'angolo di rotazione del titolo sull'asse verticale del grafico utilizzando Aspose.Slides per Python può far sì che i titoli si adattino perfettamente o risaltino nelle diapositive. Questo tutorial vi guiderà nell'impostazione di questo angolo di rotazione per migliorarne sia la funzionalità che l'aspetto visivo.

**Cosa imparerai:**
- Come installare e configurare Aspose.Slides per Python.
- Passaggi per aggiungere e personalizzare grafici nelle diapositive.
- Tecniche per impostare l'angolo di rotazione dei titoli dei grafici.
- Applicazioni pratiche di queste funzionalità nella visualizzazione dei dati.

Cominciamo esaminando i prerequisiti prima di passare all'implementazione.

## Prerequisiti

Prima di iniziare, assicurati di avere:
- **Ambiente Python**: Installa Python 3.x da [python.org](https://www.python.org/).
- **Libreria Aspose.Slides**: Installa tramite pip per manipolare efficacemente le presentazioni.
- **Conoscenza di base della programmazione Python**: La familiarità con la sintassi Python e con le operazioni sui file ti aiuterà a seguire il procedimento.

## Impostazione di Aspose.Slides per Python

Per utilizzare Aspose.Slides, installalo usando pip. Apri il terminale o il prompt dei comandi ed esegui:

```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza

Aspose offre diverse opzioni di licenza:
- **Prova gratuita**: Scarica una versione di prova da [Pagina di rilascio di Aspose](https://releases.aspose.com/slides/python-net/).
- **Licenza temporanea**: Ottieni una licenza temporanea per le funzionalità estese tramite [portale di acquisto](https://purchase.aspose.com/temporary-license/).
- **Acquistare**: Considera l'acquisto se ritieni lo strumento indispensabile, disponibile presso [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy).

#### Inizializzazione e configurazione di base

Ecco come inizializzare Aspose.Slides nel tuo script Python:

```python
import aspose.slides as slides

# Creare un oggetto di presentazione
def main():
    with slides.Presentation() as pres:
        # Il tuo codice andrà qui
        pass

if __name__ == "__main__":
    main()
```

## Guida all'implementazione

### Aggiunta e personalizzazione di grafici

#### Panoramica

In questa sezione aggiungeremo un grafico a colonne raggruppate alla diapositiva e lo personalizzeremo impostando l'angolo di rotazione del titolo dell'asse verticale.

#### Passaggi:

##### Passaggio 1: aggiungere un grafico a colonne raggruppate

Inizia aggiungendo un grafico con coordinate specifiche e dimensioni definite:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Aggiungere un grafico a colonne raggruppate alla diapositiva 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Passaggio 2: configurare il titolo dell'asse verticale

Abilita e imposta l'angolo di rotazione per il titolo dell'asse verticale:

```python
def configure_chart(chart):
    # Abilita il titolo dell'asse verticale
    chart.axes.vertical_axis.has_title = True
    
    # Imposta l'angolo di rotazione a 90 gradi
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Passaggio 3: salva la presentazione

Infine, salva la presentazione con le modifiche:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Salva la presentazione
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}