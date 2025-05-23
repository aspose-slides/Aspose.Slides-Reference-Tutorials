---
"date": "2025-04-22"
"description": "Lär dig hur du enkelt kan visa procentuella etiketter i diagram i PowerPoint-presentationer med Aspose.Slides för Python. Perfekt för att förbättra datavisualisering."
"title": "Så här visar du procentuella etiketter i diagram med Aspose.Slides för Python - En omfattande guide"
"url": "/sv/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man visar procentuella etiketter i diagram med Aspose.Slides för Python

## Introduktion

Att visualisera data effektivt är avgörande i presentationer och rapporter, särskilt när du vill framhäva proportioner eller fördelningar tydligt. Men tänk om du behöver dessa procentsatser visas direkt i dina diagram? Den här omfattande guiden guidar dig genom hur du använder **Aspose.Slides för Python** för att enkelt visa procentvärden som etiketter i ett diagram.

### Vad du kommer att lära dig:
- Hur man skapar och bäddar in diagram i PowerPoint-presentationer med Aspose.Slides för Python.
- Visar datapunkter som procentetiketter i dina diagram.
- Spara och hantera PowerPoint-presentationer effektivt.

Redo att börja lägga till insiktsfulla visuella element till din data? Låt oss först titta på vad du behöver innan vi går in i koden!

## Förkunskapskrav

Innan vi börjar, se till att du har följande:
- **Aspose.Slides för Python**Det här biblioteket är viktigt för att skapa och manipulera PowerPoint-presentationer programmatiskt.
- **Python-miljö**Grundläggande förståelse för Python-programmering och konfiguration av Python-miljöer.
- **PIP-pakethanterare**Används för att installera Aspose.Slides.

## Konfigurera Aspose.Slides för Python

För att börja använda Aspose.Slides måste du först installera det:

```bash
pip install aspose.slides
```

### Steg för att förvärva licens:
Du kan komma igång med en gratis provperiod eller skaffa en tillfällig licens för att utforska alla funktioner i Aspose.Slides. För längre tids användning kan du överväga att köpa en prenumeration.

#### Grundläggande initialisering och installation

När den är installerad initierar du din presentationsmiljö så här:

```python
import aspose.slides as slides

# Initiera ett presentationsobjekt
def create_presentation():
    with slides.Presentation() as presentation:
        # Din kod här
```

## Implementeringsguide

Nu när vi är klara, låt oss dyka ner i att visa procentsatser i diagram.

### Skapa diagrammet och lägga till data

#### Översikt
Vi skapar ett staplat kolumndiagram med procentetiketter för varje datapunkt, så att tittarna kan se de exakta proportionerna med en snabb blick.

##### Steg 1: Lägg till ett diagram i din bild

```python
# Få åtkomst till den första bilden i din presentation
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Lägg till ett staplat kolumndiagram
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Det här kodavsnittet lägger till ett enkelt diagram på den första bilden. `add_chart` Metoden anger diagramtypen samt dess position och storlek.

##### Steg 2: Beräkna totalvärden för kategorier

```python
def calculate_totals(chart):
    total_for_category = []
    # Summera värden över alla serier för varje kategori
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Denna loop beräknar summan av alla datapunkter i serien, vilket är avgörande för procentberäkningar.

#### Ställa in procentuella etiketter

##### Steg 3: Konfigurera seriedatapunkter

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Ange standardalternativ för etiketter för att dölja icke-väsentlig information
        series.labels.default_data_label_format.show_legend_key = False
        
        # Beräkna och ange procentuella etiketter
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Skapa en textdel med procentvärdet
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Rensa befintliga etiketter och lägg till en ny procentetikett
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Dölj andra dataetikettelement
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Detta segment bearbetar varje datapunkt för att beräkna dess procentandel av totalen och tilldelar den en etikett.

### Spara din presentation

```python
def save_presentation(presentation, output_directory):
    # Spara din presentation med ändringar
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}