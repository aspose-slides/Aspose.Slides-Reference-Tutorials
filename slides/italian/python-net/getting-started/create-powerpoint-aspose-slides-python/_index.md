---
"date": "2025-04-23"
"description": "Scopri come automatizzare le presentazioni PowerPoint con Aspose.Slides per Python. Questa guida illustra la configurazione, la creazione di diapositive, l'aggiunta di forme e il salvataggio della presentazione senza sforzo."
"title": "Crea presentazioni PowerPoint usando Aspose.Slides per Python - Una guida completa"
"url": "/it/python-net/getting-started/create-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e salvare una presentazione PowerPoint utilizzando Aspose.Slides per Python

## Introduzione

Stai cercando di automatizzare la creazione di presentazioni PowerPoint usando Python? Che tu stia generando report, presentazioni o qualsiasi altro materiale di presentazione tramite codice, padroneggiare questa attività può farti risparmiare molto tempo. Questo tutorial ti guiderà nella creazione di una nuova presentazione PowerPoint con Aspose.Slides per Python, nell'aggiunta di una forma automatica (come una linea) e nel salvataggio senza sforzo.

**Cosa imparerai:**
- Come configurare l'ambiente per l'utilizzo di Aspose.Slides.
- Il processo di creazione di una presentazione PowerPoint in Python.
- Aggiungere forme alle diapositive tramite programmazione.
- Salvataggio semplice delle presentazioni.

Cominciamo subito ad analizzare i prerequisiti, così sarai pronto a iniziare a programmare!

## Prerequisiti

Prima di iniziare, assicurati di avere quanto segue:

1. **Librerie richieste**: Avrai bisogno di `aspose.slides` libreria per questo tutorial.
2. **Versione Python**: Si consiglia Python 3.x (assicurare la compatibilità con Aspose.Slides).
3. **Configurazione dell'ambiente**:
   - Installa Python e, se lo desideri, configura un ambiente virtuale.

4. **Prerequisiti di conoscenza**:
   - Conoscenza di base della programmazione Python.
   - Familiarità con la gestione dei file in Python.

Ora che la configurazione è pronta, procediamo all'installazione di Aspose.Slides per Python.

## Impostazione di Aspose.Slides per Python

### Installazione

Puoi installare facilmente Aspose.Slides tramite pip:

```bash
pip install aspose.slides
```

### Fasi di acquisizione della licenza

Aspose.Slides offre una prova gratuita, licenze temporanee e opzioni di acquisto:
- **Prova gratuita**: Per testare le capacità della libreria senza limitazioni.
- **Licenza temporanea**: Ottienilo per scopi di valutazione sul tuo computer locale.
- **Acquistare**: Per uso commerciale a lungo termine.

Visita [Acquisto Aspose](https://purchase.aspose.com/buy) per esplorare queste opzioni. Dopo aver ottenuto una licenza, puoi configurarla nel tuo codice:

```python
import aspose.slides as slides

# Applica la licenza (supponendo che tu abbia il file .lic)
license = slides.License()
license.set_license("path_to_your_licence_file.lic")
```

## Guida all'implementazione

Ora vediamo come creare e salvare una presentazione.

### Crea una nuova presentazione

Lo scopo di questo tutorial è dimostrare come creare una presentazione PowerPoint partendo da zero utilizzando Python.

#### Panoramica

Inizieremo inizializzando il `Presentation` oggetto che rappresenta il nostro file di presentazione.

```python
import aspose.slides as slides

# Crea un'istanza di un oggetto Presentation che rappresenta un file di presentazione con slides.Presentation() come presentazione:
    # Ottieni la prima diapositiva (diapositiva predefinita aggiunta da Aspose.Slides)
slide = presentation.slides[0]

    # Aggiungi una forma automatica di tipo linea alla diapositiva
slide.shapes.add_auto_shape(slides.ShapeType.LINE, 50, 150, 300, 0)

    # Salva la presentazione in formato PPTX
presentation.save("YOUR_OUTPUT_DIRECTORY/create_new_presentation_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}