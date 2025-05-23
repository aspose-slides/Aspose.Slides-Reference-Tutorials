---
"date": "2025-04-23"
"description": "Scopri come automatizzare la creazione e la formattazione di forme rettangolari in PowerPoint con Aspose.Slides per Python. Migliora le tue capacità di presentazione senza sforzo."
"title": "Automatizzare le forme rettangolari in PowerPoint utilizzando Aspose.Slides per Python"
"url": "/it/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Come creare e formattare una forma rettangolare in PowerPoint utilizzando Aspose.Slides per Python
## Introduzione
Ti è mai capitato di dover aggiungere rapidamente forme personalizzate alle tue presentazioni PowerPoint, ma di avere difficoltà con l'automazione? Se sei stanco di formattare manualmente i rettangoli diapositiva per diapositiva, questo tutorial è qui per aiutarti. Sfruttando "Aspose.Slides per Python", automatizzeremo l'aggiunta e la formattazione di una forma rettangolare in poche righe di codice. Al termine di questa guida, padroneggerai:
- Creazione di una forma rettangolare tramite programmazione
- Applicazione di opzioni di formattazione come colore e stile della linea
- Salvataggio semplice della presentazione
Scopriamo insieme come puoi trasformare il processo di creazione delle tue diapositive!
### Prerequisiti
Prima di iniziare a scrivere il codice, assicurati di avere pronto quanto segue:
- **Pitone** installato sul tuo computer (si consiglia la versione 3.6 o superiore)
- **Aspose.Slides per Python** libreria, che ci consente di manipolare le presentazioni di PowerPoint
- Conoscenza di base dei concetti di programmazione Python e familiarità con l'installazione di pacchetti tramite pip
## Impostazione di Aspose.Slides per Python
### Installazione
Per installare il pacchetto Aspose.Slides, apri il terminale o il prompt dei comandi ed esegui:
```bash
pip install aspose.slides
```
Questo comando recupera e installa l'ultima versione di Aspose.Slides per Python da PyPI.
### Acquisizione della licenza
Aspose.Slides è un prodotto commerciale, ma puoi iniziare a usarlo con una licenza di prova gratuita. Ecco come ottenerne una:
1. **Prova gratuita:** Visita [Prova gratuita di Aspose](https://releases.aspose.com/slides/python-net/) e iscriviti per una valutazione.
2. **Licenza temporanea:** Per test più approfonditi senza limitazioni, richiedi una licenza temporanea a [Pagina della licenza temporanea](https://purchase.aspose.com/temporary-license/).
3. **Acquistare:** Quando sei pronto per andare in diretta, acquista una licenza tramite [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy).
Una volta acquisita, segui la documentazione per applicare la licenza al tuo progetto.
### Inizializzazione di base
Ecco come inizializzare Aspose.Slides per Python:
```python
import aspose.slides as slides
\# Inizializza la classe Presentazione
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Questo frammento imposta una nuova presentazione e conferma che è pronta per essere modificata.
## Guida all'implementazione
### Creazione della forma rettangolare
#### Panoramica
In questa sezione ci concentreremo sull'aggiunta di una forma rettangolare a una diapositiva di PowerPoint utilizzando Aspose.Slides per Python.
#### Passaggi per creare la forma
1. **Apri o crea una presentazione:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Aggiungeremo qui il nostro rettangolo
   ```
2. **Accedi alla diapositiva:**
   Recuperiamo la prima diapositiva in cui vogliamo aggiungere la forma.
   ```python
   slide = pres.slides[0]
   ```
3. **Aggiungi forma rettangolare:**
   Utilizzare il `add_auto_shape` Metodo per creare un rettangolo sulla diapositiva.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Parametri: `ShapeType.RECTANGLE`, posizione x (50), posizione y (150), larghezza (150), altezza (50).
### Formattazione del rettangolo
#### Panoramica
Ora applicheremo la formattazione alla nostra forma rettangolare, incluso il colore di riempimento e lo stile della linea.
#### Passaggi per la formattazione
1. **Colore di riempimento:**
   Imposta un riempimento uniforme con un colore specifico per lo sfondo del rettangolo.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Stile della linea:**
   Personalizza la linea del rettangolo, inclusi colore e larghezza.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Salva presentazione:**
   Infine, salva la presentazione in un file.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}