---
"date": "2025-04-23"
"description": "Scopri come creare e personalizzare la grafica SmartArt in PowerPoint utilizzando Aspose.Slides per Python, migliorando le tue presentazioni con organigrammi dinamici."
"title": "Come creare e personalizzare SmartArt in PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e personalizzare SmartArt in PowerPoint utilizzando Aspose.Slides per Python

## Introduzione

Le presentazioni sono uno strumento fondamentale per rappresentare visivamente le strutture organizzative o le sessioni di brainstorming. Con Aspose.Slides per Python, puoi creare e personalizzare facilmente la grafica SmartArt. Questo tutorial ti guiderà nell'aggiunta di un organigramma SmartArt alle tue diapositive di PowerPoint.

**Cosa imparerai:**
- Aggiungere un elemento grafico SmartArt in PowerPoint utilizzando Aspose.Slides per Python.
- Personalizzazione del layout del nodo SmartArt.
- Salvataggio ed esportazione efficiente delle presentazioni.

Cominciamo a configurare il tuo ambiente!

## Prerequisiti

Prima di iniziare a creare elementi grafici SmartArt, assicurati di disporre dei seguenti prerequisiti:

### Librerie richieste
- **Aspose.Slides per Python**: Installare questa libreria tramite pip se non lo si è già fatto.

### Requisiti di configurazione dell'ambiente
- Un'installazione funzionante di Python (consigliata la versione 3.x).
- Conoscenza di base della programmazione Python.
- La familiarità con Microsoft PowerPoint è utile ma non necessaria.

## Impostazione di Aspose.Slides per Python

Per iniziare, configura la libreria Aspose.Slides nel tuo ambiente Python:

**Installazione Pip:**
```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza
Aspose offre diverse opzioni di licenza:
- **Prova gratuita**: Scarica una licenza temporanea per valutare tutte le funzionalità.
- **Licenza temporanea**: Ottieni una licenza temporanea gratuita per un utilizzo a breve termine.
- **Acquistare**: Valuta l'acquisto di un abbonamento per progetti a lungo termine.

### Inizializzazione e configurazione di base

Una volta installato, inizializza lo script Python con Aspose.Slides in questo modo:

```python
import aspose.slides as slides

# Inizializza la classe Presentation con slides.Presentation() come presentation:
    # Il tuo codice per aggiungere SmartArt andrà qui
```

## Guida all'implementazione

Analizziamo ora il processo di aggiunta e personalizzazione di SmartArt in PowerPoint utilizzando Aspose.Slides per Python.

### Aggiunta di un elemento grafico SmartArt

#### Panoramica
Crea una nuova diapositiva e aggiungici un grafico SmartArt di tipo organigramma:

```python
import aspose.slides as slides

# Crea un'istanza di presentazione con slides.Presentation() come presentazione:
    # Aggiungi SmartArt con le dimensioni specificate nella posizione (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parametri e scopo del metodo
- **x, y**: Posizione dell'elemento grafico SmartArt sulla diapositiva.
- **larghezza, altezza**: Dimensioni per una corretta visibilità.
- **tipo_disposizione**: specifica il tipo di layout SmartArt, in questo caso un organigramma.

### Personalizzazione del layout dell'organigramma

#### Panoramica
Personalizza il primo nodo nella nostra grafica SmartArt impostandone il layout su LEFT_HANGING:

```python
# Imposta il primo nodo sul layout appeso a sinistra
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Spiegazione delle opzioni di configurazione chiave
- **Tipo di layout dell'organigramma**Determina il modo in cui vengono visualizzati i nodi, migliorandone la leggibilità e l'aspetto estetico.

### Salvataggio della presentazione

Infine, salva la presentazione in una directory specificata:

```python
# Salva la presentazione con SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}