---
"date": "2025-04-23"
"description": "Leer hoe u SmartArt-afbeeldingen in PowerPoint kunt maken en aanpassen met Aspose.Slides voor Python. Zo kunt u uw presentaties verbeteren met dynamische organisatieschema's."
"title": "SmartArt maken en aanpassen in PowerPoint met Aspose.Slides voor Python"
"url": "/nl/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# SmartArt maken en aanpassen in PowerPoint met Aspose.Slides voor Python

## Invoering

Presentaties zijn een essentieel hulpmiddel voor het visueel weergeven van organisatiestructuren of brainstormsessies. Met Aspose.Slides voor Python kunt u moeiteloos SmartArt-afbeeldingen maken en aanpassen. Deze tutorial begeleidt u bij het toevoegen van een SmartArt-afbeelding in de vorm van een organigram aan uw PowerPoint-dia's.

**Wat je leert:**
- Een SmartArt-afbeelding toevoegen in PowerPoint met behulp van Aspose.Slides voor Python.
- De lay-out van uw SmartArt-knooppunt aanpassen.
- Presentaties efficiënt opslaan en exporteren.

Laten we beginnen met het instellen van uw omgeving!

## Vereisten

Voordat u SmartArt-afbeeldingen gaat maken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

### Vereiste bibliotheken
- **Aspose.Slides voor Python**: Installeer deze bibliotheek met behulp van pip, indien dit nog niet is gebeurd.

### Vereisten voor omgevingsinstellingen
- Een werkende installatie van Python (3.x aanbevolen).
- Basiskennis van Python-programmering.
- Kennis van Microsoft PowerPoint is nuttig, maar niet noodzakelijk.

## Aspose.Slides instellen voor Python

Om te beginnen moet u de Aspose.Slides-bibliotheek in uw Python-omgeving instellen:

**Pip-installatie:**
```bash
pip install aspose.slides
```

### Stappen voor het verkrijgen van een licentie
Aspose biedt verschillende licentieopties:
- **Gratis proefperiode**: Download een tijdelijke licentie om alle functies te evalueren.
- **Tijdelijke licentie**: Ontvang een gratis tijdelijke licentie voor kortdurend gebruik.
- **Aankoop**: Overweeg een abonnement aan te schaffen voor langetermijnprojecten.

### Basisinitialisatie en -installatie

Nadat u het hebt geïnstalleerd, initialiseert u uw Python-script met Aspose.Slides, zoals deze:

```python
import aspose.slides as slides

# Initialiseer de Presentation-klasse\met slides.Presentation() als presentatie:
    # Uw code om SmartArt toe te voegen komt hier
```

## Implementatiegids

Laten we nu eens kijken hoe u SmartArt in PowerPoint kunt toevoegen en aanpassen met behulp van Aspose.Slides voor Python.

### Een SmartArt-afbeelding toevoegen

#### Overzicht
Maak een nieuwe dia en voeg er een SmartArt-afbeelding van het type organigram aan toe:

```python
import aspose.slides as slides

# Maak een presentatie-exemplaar\met slides.Presentation() als presentatie:
    # SmartArt toevoegen met opgegeven afmetingen op positie (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parameters en methodedoel
- **x, y**: Positie van de SmartArt-afbeelding op de dia.
- **breedte, hoogte**: Afmetingen voor goed zicht.
- **lay-outtype**: Hiermee geeft u het type SmartArt-lay-out op, in dit geval een organigram.

### De lay-out van het organigram aanpassen

#### Overzicht
Pas het eerste knooppunt in onze SmartArt-afbeelding aan door de lay-out in te stellen op LEFT_HANGING:

```python
# Stel het eerste knooppunt in op een links hangende lay-out
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Uitleg van de belangrijkste configuratieopties
- **OrganisatieGrafiekLayoutType**Bepaalt hoe knooppunten worden weergegeven, waardoor de leesbaarheid en het esthetische aspect worden verbeterd.

### De presentatie opslaan

Sla ten slotte uw presentatie op in de opgegeven map:

```python
# Sla de presentatie op met SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}