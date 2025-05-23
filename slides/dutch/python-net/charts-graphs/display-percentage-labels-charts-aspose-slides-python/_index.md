---
"date": "2025-04-22"
"description": "Leer hoe je moeiteloos percentagelabels in grafieken in PowerPoint-presentaties kunt weergeven met Aspose.Slides voor Python. Perfect voor het verbeteren van datavisualisatie."
"title": "Hoe u percentagelabels in grafieken kunt weergeven met Aspose.Slides voor Python&#58; een uitgebreide handleiding"
"url": "/nl/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe u percentagelabels in grafieken kunt weergeven met Aspose.Slides voor Python

## Invoering

Het effectief visualiseren van gegevens is cruciaal in presentaties en rapporten, vooral wanneer u verhoudingen of verdelingen duidelijk wilt weergeven. Maar wat als u die percentages direct in uw grafieken wilt weergeven? Deze uitgebreide handleiding begeleidt u bij het gebruik ervan. **Aspose.Slides voor Python** om moeiteloos percentagewaarden als labels in een grafiek weer te geven.

### Wat je leert:
- Hoe u diagrammen in PowerPoint-presentaties kunt maken en insluiten met Aspose.Slides voor Python.
- Gegevenspunten weergeven als percentagelabels in uw diagrammen.
- PowerPoint-presentaties efficiënt opslaan en beheren.

Klaar om inzichtelijke visuals aan je data toe te voegen? Laten we eerst eens kijken wat je nodig hebt voordat we de code induiken!

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:
- **Aspose.Slides voor Python**:Deze bibliotheek is essentieel voor het programmatisch maken en bewerken van PowerPoint-presentaties.
- **Python-omgeving**: Een basiskennis van Python-programmering en het instellen van de omgeving.
- **PIP-pakketbeheerder**: Wordt gebruikt om Aspose.Slides te installeren.

## Aspose.Slides instellen voor Python

Om Aspose.Slides te kunnen gebruiken, moet u het eerst installeren:

```bash
pip install aspose.slides
```

### Stappen voor het verkrijgen van een licentie:
kunt beginnen met een gratis proefperiode of een tijdelijke licentie aanschaffen om alle mogelijkheden van Aspose.Slides te ontdekken. Voor langdurig gebruik kunt u een abonnement overwegen.

#### Basisinitialisatie en -installatie

Nadat u het programma hebt geïnstalleerd, initialiseert u uw presentatieomgeving als volgt:

```python
import aspose.slides as slides

# Initialiseer een presentatieobject
def create_presentation():
    with slides.Presentation() as presentation:
        # Uw code hier
```

## Implementatiegids

Nu we alles hebben ingesteld, gaan we dieper in op het weergeven van percentages in grafieken.

### Het diagram maken en gegevens toevoegen

#### Overzicht
We maken een gestapeld kolomdiagram met percentagelabels voor elk gegevenspunt. Zo kunnen kijkers in één oogopslag de exacte verhoudingen zien.

##### Stap 1: Voeg een grafiek toe aan uw dia

```python
# Toegang tot de eerste dia in uw presentatie
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Voeg een gestapelde kolomgrafiek toe
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Met dit codefragment wordt een basisgrafiek aan de eerste dia toegevoegd. `add_chart` methode specificeert het type grafiek en de positie en grootte ervan.

##### Stap 2: Bereken totale waarden voor categorieën

```python
def calculate_totals(chart):
    total_for_category = []
    # Tel de waarden van alle reeksen voor elke categorie op
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Deze lus berekent het totaal van alle datapunten in de reeksen, wat cruciaal is voor percentageberekeningen.

#### Percentagelabels instellen

##### Stap 3: Configureer reeksgegevenspunten

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Stel standaardlabelopties in om niet-essentiële informatie te verbergen
        series.labels.default_data_label_format.show_legend_key = False
        
        # Percentagelabels berekenen en instellen
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Maak een tekstgedeelte met de percentagewaarde
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Bestaande labels wissen en een nieuw percentagelabel toevoegen
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Andere gegevenslabelelementen verbergen
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Dit segment verwerkt elk gegevenspunt om het percentage van het totaal te berekenen en wijst hier een label aan toe.

### Uw presentatie opslaan

```python
def save_presentation(presentation, output_directory):
    # Sla uw presentatie op met wijzigingen
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}