---
"date": "2025-04-24"
"description": "Scopri come creare e gestire regole di fallback dei font con Aspose.Slides per Python per garantire che le tue presentazioni siano coerenti su sistemi diversi."
"title": "Padroneggiare il fallback dei font in Aspose.Slides per Python&#58; una guida completa"
"url": "/it/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Padroneggiare il fallback dei font in Aspose.Slides per Python: una guida completa

## Introduzione

I problemi di compatibilità dei font possono rappresentare una sfida quando si creano presentazioni, soprattutto se i caratteri Unicode non sono supportati dai font principali. **Aspose.Slides per Python** fornisce una soluzione solida attraverso regole di fallback dei font, garantendo l'attrattiva visiva e la leggibilità della presentazione su vari sistemi.

In questa guida, esploreremo come creare e gestire regole di fallback dei font utilizzando Aspose.Slides per Python. Imparerai:
- Configurazione dell'ambiente con Aspose.Slides
- Creazione di una raccolta di regole di fallback dei font
- Gestire queste regole aggiungendo o rimuovendo i font in base agli intervalli Unicode
- Applicazione delle regole alle presentazioni e rendering delle diapositive come immagini

Cominciamo preparando l'ambiente.

## Prerequisiti

Assicurati che il tuo ambiente sia pronto per questo compito. Ecco cosa ti servirà:
1. **Aspose.Slides per Python**:Questa libreria gestisce le regole di fallback dei font.
2. **Ambiente Python**: Assicurarsi che Python (versione 3.6 o successiva) sia installato.
3. **Conoscenza di base di Python**:La familiarità con la sintassi e i concetti di Python sarà utile quando approfondiremo i frammenti di codice.

## Impostazione di Aspose.Slides per Python

### Installazione

Per iniziare, installa la libreria Aspose.Slides utilizzando pip:

```bash
pip install aspose.slides
```

### Acquisizione della licenza

Aspose offre una licenza di prova gratuita per esplorare le sue funzionalità senza limitazioni. Ecco come ottenerla:
- Visita [Pagina di acquisto di Aspose](https://purchase.aspose.com/buy) per acquistare opzioni o accedere a una licenza temporanea.
- In alternativa, scarica una versione di prova gratuita da [Sezione Download](https://releases.aspose.com/slides/python-net/).

### Inizializzazione di base

Una volta installato, inizializza Aspose.Slides nel tuo script Python:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Guida all'implementazione

### Creazione e gestione delle regole di fallback dei font

#### Panoramica

Le regole di fallback dei font garantiscono che tutti i caratteri nella presentazione abbiano un font appropriato, mantenendo la leggibilità per le lingue con set di caratteri univoci.

#### Fasi di implementazione

**1. Creare una raccolta di regole di fallback dei font**

Inizia creando una raccolta per definire i font di fallback:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Aggiungi una regola di fallback del font**

Definisci una regola che specifichi l'intervallo Unicode e il font di fallback:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Parametri**: `0x400` è l'inizio dell'intervallo Unicode, `0x4FF` è la fine, e `"Times New Roman"` è il font di riserva.

**3. Gestire le regole esistenti**

Ripeti ogni regola per modificarla secondo necessità:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Rimuovere una regola**

Se necessario, rimuovi la prima regola dalla tua raccolta:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Applicazione delle regole di fallback dei font a una presentazione e rendering di un'immagine

#### Panoramica

Una volta impostate le regole di fallback per i font, applicatele alle presentazioni per garantire che il testo utilizzi i font di fallback specificati quando necessario.

#### Fasi di implementazione

**1. Inizializza il tuo ambiente**

Preparare le directory per l'input e l'output:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Applicare regole di fallback a una presentazione**

Carica il file della presentazione e applica le regole sui font:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}