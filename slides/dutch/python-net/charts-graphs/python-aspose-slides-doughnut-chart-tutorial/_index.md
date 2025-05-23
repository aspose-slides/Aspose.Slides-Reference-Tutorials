---
"date": "2025-04-22"
"description": "Leer hoe je ringdiagrammen maakt met Python en Aspose.Slides. Deze stapsgewijze handleiding behandelt de installatie, aanpassing en best practices voor het verbeteren van je presentaties."
"title": "Hoe maak je donutdiagrammen in Python met Aspose.Slides? Een stapsgewijze handleiding"
"url": "/nl/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je donutdiagrammen in Python met Aspose.Slides: een stapsgewijze handleiding

Op het gebied van datavisualisatie kan het effectief presenteren van informatie een aanzienlijke impact hebben op het begrip en de besluitvorming. Of u nu een zakelijke presentatie maakt of complexe datasets analyseert, diagrammen zijn essentiële hulpmiddelen. Van de verschillende diagramtypen bieden ringdiagrammen een aantrekkelijke manier om proportionele gegevens weer te geven met een intuïtief middengat. Deze stapsgewijze handleiding begeleidt u bij het maken van een ringdiagram in Python met behulp van Aspose.Slides, een krachtige bibliotheek voor het bewerken van presentaties.

## Wat je zult leren
- Hoe Aspose.Slides voor Python in te stellen en te gebruiken
- Het proces van het toevoegen van een donutdiagram aan uw presentatieslides
- Het aanpassen van series en categorieën binnen de grafiek
- Het aanpassen van visuele elementen zoals labels, kleuren en explosie-effecten
- Aanbevolen procedures voor het optimaliseren van prestaties met Aspose.Slides

## Vereisten
Voordat u begint, zorg ervoor dat u het volgende heeft:
- **Python-omgeving**: Python 3.x op uw computer geïnstalleerd.
- **Aspose.Slides voor Python**: Installeer deze bibliotheek met behulp van pip.
- **Basiskennis van Python-programmering**: Kennis van lussen en objectgeoriënteerd programmeren is nuttig.

## Aspose.Slides instellen voor Python
Om te beginnen installeert u de Aspose.Slides-bibliotheek via pip:

```bash
pip install aspose.slides
```

### Licentieverwerving
Aspose biedt een gratis proefperiode aan om functies onbeperkt en voor een beperkte tijd te testen. Om deze te verkrijgen:
1. Bezoek de [Gratis proefperiode](https://releases.aspose.com/slides/python-net/) pagina.
2. Volg de instructies om uw tijdelijke licentie te downloaden en toe te passen.

Voor voortgezet gebruik kunt u overwegen een abonnement aan te schaffen bij de [Aankooppagina](https://purchase.aspose.com/buy).

### Basisinitialisatie
Nadat u Aspose.Slides hebt ingesteld, initialiseert u het als volgt:

```python
import aspose.slides as slides

# Maak een exemplaar van de Presentation-klasse.
with slides.Presentation() as pres:
    # Plaats hier uw code om presentaties te bewerken.

# Sla de presentatie op nadat u wijzigingen hebt aangebracht.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Implementatiegids
Nadat u Aspose.Slides hebt ingesteld, volgt u deze stappen om een ringdiagram dia voor dia aan uw presentatie toe te voegen.

### Een nieuwe presentatie maken en een dia toevoegen
Begin met het maken van een exemplaar van de `Presentation` klas:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Open of maak dia's binnen deze context.
```

### Een donutdiagram toevoegen aan de eerste dia
Ga naar de eerste dia en gebruik de `add_chart` methode. Geef het grafiektype op als `DOUGHNUT`, samen met positie en grootte:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Grafiekgegevens configureren
Bestaande gegevens wissen en instellingen configureren, zoals het verbergen van de legenda:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Series en categorieën toevoegen
Voeg meerdere reeksen en categorieën toe voor een ringdiagram. Zo maakt u 15 reeksen met specifieke eigenschappen:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Voeg categorieën op vergelijkbare wijze toe:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Voeg datapunten toe voor elke reeks.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Pas het uiterlijk van elk gegevenspunt aan.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Labelinstellingen configureren voor de laatste serie.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### De presentatie opslaan
Sla ten slotte uw presentatie op in de opgegeven map:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Praktische toepassingen
Donutdiagrammen zijn veelzijdig en kunnen in verschillende scenario's worden gebruikt, zoals:
1. **Budgettoewijzing**: Weergeven hoe verschillende afdelingen de aan hen toegewezen middelen gebruiken.
2. **Marktaandeelanalyse**:Het vergelijken van het marktaandeel van concurrerende producten of bedrijven.
3. **Enquêteresultaten**:Visualiseren van reacties op enquêtevragen over voorkeuren of tevredenheidsniveaus.

## Prestatieoverwegingen
Om optimale prestaties te garanderen bij het gebruik van Aspose.Slides:
- Minimaliseer het geheugengebruik door voorwerpen na gebruik op de juiste manier weg te gooien.
- Laad presentaties alleen in het geheugen als dat nodig is en sluit ze zo snel mogelijk.
- Als u met een groot aantal grafieken werkt, kunt u overwegen om dia's in batch te verwerken.

## Conclusie
Door deze handleiding te volgen, hebt u geleerd hoe u dynamische ringdiagrammen maakt met Aspose.Slides voor Python. Deze visualisaties kunnen uw presentaties verbeteren door gegevens begrijpelijker en aantrekkelijker te maken. Ontdek de functies van de bibliotheek verder om uw diagrammen verder aan te passen en te optimaliseren.

## FAQ-sectie
1. **Kan ik Aspose.Slides gebruiken zonder een licentie te kopen?**
   - Ja, u kunt beginnen met een gratis proeflicentie voor evaluatiedoeleinden.
2. **Hoe verander ik de kleuren van een diagram in Aspose.Slides?**
   - Gebruik de `fill_format` eigenschap om de gewenste kleur voor uw grafiekelementen in te stellen.
3. **Is het mogelijk om grafieken als afbeeldingen te exporteren?**
   - Ja, u kunt dia's met diagrammen omzetten in afbeeldingsformaten met behulp van de weergavemogelijkheden van de bibliotheek.
4. **Wat zijn enkele veelvoorkomende problemen bij het toevoegen van grafieken?**
   - Zorg ervoor dat alle datapunten en categorieën correct zijn toegevoegd voordat u de grafiek opslaat of weergeeft.
5. **Kan ik Aspose.Slides integreren met andere Python-bibliotheken?**
   - Absoluut! Je kunt het gebruiken in combinatie met bibliotheken zoals Pandas voor verbeterde mogelijkheden voor datamanipulatie.

## Bronnen
- [Aspose.Slides-documentatie](https://reference.aspose.com/slides/python-net/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Koop een licentie](https://purchase.aspose.com/buy)
- [Gratis proefversie en tijdelijke licentie](https://releases.aspose.com/slides/python-net/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}