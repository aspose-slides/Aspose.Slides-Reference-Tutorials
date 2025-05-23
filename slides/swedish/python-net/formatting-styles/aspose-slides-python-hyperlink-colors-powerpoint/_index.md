---
"date": "2025-04-23"
"description": "Lär dig hur du anpassar hyperlänkfärger i PowerPoint-presentationer med Aspose.Slides för Python. Förbättra dina bilder effektivt med personliga länkstilar."
"title": "Hur man ställer in hyperlänkfärger i PowerPoint med hjälp av Aspose.Slides för Python"
"url": "/sv/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man ställer in hyperlänkfärger i PowerPoint med hjälp av Aspose.Slides för Python

## Introduktion

Att förbättra den visuella attraktionskraften i dina PowerPoint-presentationer genom att anpassa hyperlänkfärger är enkelt med Aspose.Slides för Python. Den här guiden guidar dig genom att ställa in hyperlänkar med specifika färger i dina bilder med Python.

**Vad du kommer att lära dig:**
- Så här ställer du in en hyperlänkfärg i textformer i PowerPoint.
- Steg för att skapa en visuellt tilltalande presentation.
- Viktiga funktioner i Aspose.Slides för Python som underlättar denna anpassning.

Låt oss gå in på vilka förkunskapskrav som krävs innan vi börjar.

## Förkunskapskrav

Innan du börjar, se till att din miljö är redo med följande:
- **Bibliotek och versioner:** Installera `aspose.slides` bibliotek. Se till att Python är installerat på din dator.
- **Krav för miljöinstallation:** Den här handledningen förutsätter en grundläggande installation av Python på Windows, Mac eller Linux.
- **Kunskapsförkunskapskrav:** Kunskap om Python-programmering är meriterande.

## Konfigurera Aspose.Slides för Python

För att börja använda Aspose.Slides för Python, installera paketet via pip:

```bash
pip install aspose.slides
```

**Steg för att förvärva licens:**
- **Gratis provperiod:** Ladda ner en testversion från [Asposes lanseringssida](https://releases.aspose.com/slides/python-net/).
- **Tillfällig licens:** Ansök om en tillfällig licens för [köpsida](https://purchase.aspose.com/temporary-license/) för utökad åtkomst.
- **Köpa:** För att låsa upp funktioner helt utan begränsningar, överväg att köpa en licens från [Asposes köpsida](https://purchase.aspose.com/buy).

**Grundläggande initialisering:**
När Aspose.Slides är installerat och licensierat, importera dem i ditt skript:

```python
import aspose.slides as slides
```

## Implementeringsguide

Det här avsnittet guidar dig genom att ställa in hyperlänkfärger i en PowerPoint-presentation.

### Ställ in hyperlänkfärgsfunktionen

#### Översikt

Anpassa färgen på hyperlänkar som är inbäddade i textformer med Aspose.Slides för Python. Detta förbättrar läsbarheten och det visuella tilltalet.

##### Steg 1: Skapa en ny presentation

Skapa en instans av en presentation:

```python
with slides.Presentation() as presentation:
    # Din kod här
```

##### Steg 2: Lägg till en form med text

Lägg till en rektangelform på den första bilden och infoga text som innehåller en hyperlänk.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Steg 3: Ange hyperlänkegenskaper

Tilldela hyperlänken och ange dess färg. `hyperlink_click` egenskapen anger vart länken ska navigera vid klick.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Ange färgkällan för hyperlänk till portionsformat och definiera fyllningstyp och färg.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Steg 4: Spara presentationen

Spara din presentation till en angiven katalog:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}