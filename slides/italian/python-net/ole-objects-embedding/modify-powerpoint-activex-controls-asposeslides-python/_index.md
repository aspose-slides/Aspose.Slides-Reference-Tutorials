---
"date": "2025-04-22"
"description": "Scopri come modificare il testo delle caselle di testo, le didascalie dei pulsanti e le immagini in PowerPoint utilizzando Aspose.Slides con Python. Arricchisci le tue presentazioni con elementi interattivi."
"title": "Master Aspose.Slides per Python&#58; modifica facilmente i controlli ActiveX di PowerPoint"
"url": "/it/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare Aspose.Slides per Python: Modifica dei controlli ActiveX di PowerPoint

Nell'attuale panorama digitale dinamico, personalizzare le presentazioni di Microsoft PowerPoint è essenziale per creare contenuti coinvolgenti. Che si tratti di sviluppare moduli di formazione interattivi o di migliorare le presentazioni aziendali con funzionalità di input utente, la modifica dei controlli ActiveX di PowerPoint può migliorare significativamente la funzionalità della presentazione. Questo tutorial illustra l'utilizzo di Aspose.Slides per Python per modificare il testo e le didascalie dei pulsanti di TextBox, sostituire immagini, riposizionare o rimuovere controlli ActiveX dalle diapositive.

## Cosa imparerai
- Come modificare il testo delle caselle di testo e le didascalie dei pulsanti nelle presentazioni di PowerPoint.
- Tecniche per la sostituzione delle immagini nei controlli ActiveX.
- Metodi per riposizionare o rimuovere efficacemente i controlli ActiveX.
- Applicazioni pratiche di queste funzionalità in scenari reali.

Prima di approfondire Aspose.Slides per Python, rivediamo i prerequisiti.

## Prerequisiti
Per seguire questo tutorial, assicurati di avere:
- **Pitone**: Versione 3.6 o superiore installata sul sistema.
- **Aspose.Slides per Python tramite .NET**: Può essere installato tramite pip.
- Una conoscenza di base della programmazione Python e familiarità con la struttura di PowerPoint.

### Requisiti di configurazione dell'ambiente
1. **Installa Aspose.Slides**:
   Utilizzare il seguente comando per installare Aspose.Slides per Python tramite .NET:

   ```bash
   pip install aspose.slides
   ```

2. **Acquisizione della licenza**: 
   Inizia ottenendo un [licenza di prova gratuita](https://releases.aspose.com/slides/python-net/) oppure richiedi una licenza temporanea per esplorare tutte le funzionalità senza limitazioni.

3. **Inizializzazione di base**:
   Importa i moduli necessari e carica il documento PowerPoint come mostrato di seguito:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Il tuo codice andrà qui.
   ```

## Guida all'implementazione
### Funzionalità: modifica il testo della casella di testo e sostituisci l'immagine
#### Panoramica
Questa funzionalità consente di aggiornare il testo all'interno di un controllo ActiveX TextBox e di sostituire l'immagine associata, utile per personalizzare presentazioni o aggiornare dinamicamente i contenuti.

##### Guida passo passo
1. **Carica la presentazione**:
   Per prima cosa carica la presentazione PowerPoint contenente i controlli ActiveX.

   ```python
def change_textbox_and_image():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") come presentazione:
        slide = presentazione.slides[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Crea immagine sostitutiva**:
   Genera un'immagine per sostituire il contenuto originale durante l'attivazione di ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Crea un'immagine con dimensioni specificate
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Aggiungi linee di confine per un aspetto raffinato
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funzionalità: cambia la didascalia del pulsante e sostituisci l'immagine
#### Panoramica
Aggiorna le didascalie dei pulsanti nei controlli ActiveX della presentazione, offrendo possibilità di interazione dinamica all'utente.

##### Guida passo passo
1. **Carica la presentazione**:
   Come prima, iniziamo caricando il file PowerPoint.

   ```python
def change_button_caption_and_image():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") come presentazione:
        slide = presentazione.slides[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Crea immagine sostitutiva**:
   Genera un'immagine per la sostituzione visiva.

   ```python
            # Crea una bitmap per le dimensioni del pulsante
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Aggiungi linee di confine per l'estetica
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funzionalità: sposta i controlli ActiveX verso il basso e salva la presentazione
#### Panoramica
Scopri come riposizionare i controlli ActiveX all'interno di una diapositiva, migliorando la flessibilità del layout.

##### Guida passo passo
1. **Carica la presentazione**:
   Apri il documento PowerPoint per modificarlo.

   ```python
definizione sposta_controlli_attivi_x_e_salva():
    con slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") come presentazione:
        slide = presentazione.slides[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Conclusione:**
Seguendo questa guida, puoi modificare efficacemente i controlli ActiveX di PowerPoint utilizzando Aspose.Slides per Python. Questo migliorerà l'interattività e la personalizzazione delle tue presentazioni, rendendole più coinvolgenti per il tuo pubblico.

## Consigli per le parole chiave
- "Modifica i controlli ActiveX di PowerPoint"
- "Aspose.Slides per Python"
- "Modifica il testo della casella di testo in PowerPoint"
- "Sostituisci le immagini nei controlli ActiveX"

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}