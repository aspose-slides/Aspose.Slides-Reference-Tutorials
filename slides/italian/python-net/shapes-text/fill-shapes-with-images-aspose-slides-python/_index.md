---
"date": "2025-04-23"
"description": "Scopri come riempire le forme con immagini nelle presentazioni di PowerPoint usando Aspose.Slides per Python. Migliora le tue diapositive con questo tutorial passo passo."
"title": "Come riempire le forme con le immagini in PowerPoint usando Aspose.Slides per Python&#58; una guida passo passo"
"url": "/it/python-net/shapes-text/fill-shapes-with-images-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come riempire le forme con le immagini in PowerPoint usando Aspose.Slides per Python

## Introduzione
Creare presentazioni PowerPoint visivamente accattivanti è fondamentale, che tu sia un professionista o un docente che desidera catturare l'attenzione del pubblico. Un modo per migliorare le tue diapositive utilizzando Aspose.Slides per Python è riempire le forme con immagini. Questa funzionalità ti consente di aggiungere design unici e creativi che possono far risaltare i tuoi contenuti.

Che tu sia alle prime armi con la programmazione di presentazioni o che tu stia cercando modi per automatizzare attività ripetitive, questa guida ti mostrerà come riempire le forme con immagini in modo efficace utilizzando Aspose.Slides per Python.

**Cosa imparerai:**
- Come configurare l'ambiente per lavorare con Aspose.Slides
- Il processo di riempimento delle forme con immagini in una presentazione di PowerPoint
- Suggerimenti per ottimizzare le prestazioni e risolvere i problemi più comuni

Analizziamo ora i prerequisiti richiesti prima di iniziare!

## Prerequisiti
Prima di iniziare, assicurati di avere:

### Librerie e dipendenze richieste:
- **Aspose.Slides per Python**: Installa tramite pip per abilitare la manipolazione delle presentazioni PowerPoint.
- **Python 3.6 o superiore**: assicurati che il tuo ambiente supporti le funzionalità Python più recenti.

### Requisiti di configurazione dell'ambiente:
- Un'installazione funzionante di Python
- Accesso a un terminale o prompt dei comandi per l'installazione dei pacchetti

### Prerequisiti di conoscenza:
- Conoscenza di base della programmazione Python
- Familiarità con la gestione di file e directory in Python

Una volta soddisfatti questi prerequisiti, siamo pronti a configurare Aspose.Slides per Python.

## Impostazione di Aspose.Slides per Python
Per iniziare, è necessario installare la libreria Aspose.Slides. Questo potente strumento consente di creare e manipolare facilmente le presentazioni PowerPoint a livello di codice.

### Installazione Pip:
Esegui il seguente comando nel terminale o nel prompt dei comandi:

```bash
pip install aspose.slides
```

Verrà scaricata e installata l'ultima versione di Aspose.Slides per Python da PyPI.

### Fasi di acquisizione della licenza:
- **Prova gratuita**: Utilizzo [Prova gratuita di Aspose](https://releases.aspose.com/slides/python-net/) per valutare le caratteristiche senza alcun costo.
- **Licenza temporanea**: Ottieni una licenza temporanea visitando [Licenza temporanea](https://purchase.aspose.com/temporary-license/).
- **Acquistare**: Per un utilizzo a lungo termine, è possibile acquistare una licenza presso [Pagina di acquisto Aspose](https://purchase.aspose.com/buy).

### Inizializzazione e configurazione di base:
Una volta installato, inizializza Aspose.Slides nel tuo script Python per iniziare a lavorare con le presentazioni:

```python
import aspose.slides as slides

# Inizializza la classe di presentazione per leggere o creare nuove presentazioni
pres = slides.Presentation()
```

Dopo aver configurato la libreria, passiamo all'implementazione di funzionalità specifiche.

## Guida all'implementazione
Suddivideremo l'implementazione in due sezioni chiave: riempimento di forme con immagini e salvataggio di una presentazione PowerPoint. 

### Riempire le forme con le immagini
Questa funzionalità consente di migliorare le diapositive utilizzando immagini come riempimento per varie forme, aggiungendo un tocco professionale o coerenza tematica alle presentazioni.

#### Passaggio 1: importa Aspose.Slides
Iniziamo importando il modulo necessario:

```python
import aspose.slides as slides
```

#### Passaggio 2: definire i percorsi delle immagini
Specificare i percorsi per le directory di input e di output:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

Sostituire `"YOUR_DOCUMENT_DIRECTORY/"` con il percorso della directory di origine dell'immagine e `"YOUR_OUTPUT_DIRECTORY/"` dove vuoi salvare la presentazione finale.

#### Passaggio 3: creare un'istanza di presentazione
Istanziare il `Presentation` classe, che rappresenta un file PowerPoint:

```python
with slides.Presentation() as pres:
    slide = pres.slides[0]
```

Qui accediamo alla prima diapositiva della presentazione. Puoi modificare o aggiungere nuove diapositive in base alle tue esigenze.

#### Passaggio 4: aggiungere e configurare le forme
Aggiungi una forma automatica alla diapositiva e configurane il tipo di riempimento:

```python
shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 75, 150)
shape.fill_format.fill_type = slides.FillType.PICTURE
```

Questo codice aggiunge una forma rettangolare alle coordinate specificate con dimensioni di larghezza 75 e altezza 150.

#### Passaggio 5: imposta la modalità di riempimento dell'immagine
Definisci come l'immagine riempirà la forma:

```python
shape.fill_format.picture_fill_format.picture_fill_mode = slides.PictureFillMode.TILE
```

Utilizzo `TILE` La modalità affianca l'immagine sull'intera area della forma, creando un effetto pattern senza soluzione di continuità.

#### Passaggio 6: carica e assegna l'immagine
Carica un'immagine e aggiungila alla presentazione:

```python
img = slides.Images.from_file(data_dir + "image2.jpg")
imgx = pres.images.add_image(img)
shape.fill_format.picture_fill_format.picture.image = imgx
```

Questo passaggio prevede il caricamento `image2.jpg` dalla tua directory, aggiungendolo alla raccolta di immagini e assegnandolo come riempimento per la forma.

#### Passaggio 7: salva la presentazione
Infine, salva la presentazione con le forme riempite:

```python
pres.save(out_dir + "shapes_filltype_picture_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}