---
"date": "2025-04-23"
"description": "Leer hoe u het maken van SmartArt-afbeeldingen in PowerPoint-presentaties kunt automatiseren met Aspose.Slides voor Python, inclusief het efficiënt extraheren en opslaan van miniaturen."
"title": "SmartArt-miniaturen maken en ophalen met Aspose.Slides voor Python"
"url": "/nl/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# SmartArt-miniaturen maken en ophalen met Aspose.Slides voor Python

## Invoering

Het maken van visueel aantrekkelijke presentaties is essentieel om de aandacht van je publiek te trekken. Een effectieve manier om diapresentaties te verbeteren, is door dynamische afbeeldingen zoals SmartArt in PowerPoint-presentaties te integreren. Als je op zoek bent naar een geautomatiseerde methode om deze afbeeldingen te genereren en er miniaturen uit te halen, is deze handleiding over "Aspose.Slides Python" onmisbaar.

Met Aspose.Slides voor Python kun je moeiteloos SmartArt-afbeeldingen maken, toegang krijgen tot specifieke knooppunten binnen de afbeelding, miniaturen van die knooppunten ophalen en deze afbeeldingen opslaan voor je projecten. Deze tutorial leidt je stap voor stap door elke stap.

**Wat je leert:**
- Hoe je Aspose.Slides voor Python installeert en instelt.
- Een SmartArt-afbeelding maken in een PowerPoint-presentatie.
- Toegang tot knooppunten in een SmartArt-afbeelding.
- Een miniatuurafbeelding uit een specifiek knooppunt extraheren en opslaan.

Laten we eerst de vereisten doornemen voordat we beginnen.

## Vereisten

Zorg ervoor dat u het volgende bij de hand hebt voordat u begint:

- **Vereiste bibliotheken:** Je hebt Aspose.Slides voor Python nodig. Zorg ervoor dat je omgeving Python 3.x ondersteunt.
- **Vereisten voor omgevingsinstelling:** Een werkende installatie van Python en een geschikte IDE of teksteditor zoals VSCode of PyCharm.
- **Kennisvereisten:** Basiskennis van Python-programmering, inclusief functiedefinities en bestandsbewerkingen.

## Aspose.Slides instellen voor Python

Allereerst moet je de Aspose.Slides-bibliotheek installeren. Dit kun je eenvoudig doen met pip:

```bash
pip install aspose.slides
```

Na de installatie kunt u een licentie aanschaffen als u alle functies onbeperkt wilt uitproberen. U kunt beginnen met een gratis proefperiode, een tijdelijke licentie aanvragen of een licentie kopen voor langdurig gebruik.

Om Aspose.Slides in uw Python-omgeving te initialiseren, importeert u de bibliotheek aan het begin van uw script:

```python
import aspose.slides as slides
```

## Implementatiegids

Laten we het proces voor het maken en ophalen van een SmartArt-miniatuur opsplitsen in duidelijke stappen.

### Stap 1: Een nieuw presentatie-exemplaar maken

Begin met het maken van een presentatie-exemplaar. Dit wordt de container waar je je SmartArt-afbeelding aan toevoegt.

```python
with slides.Presentation() as pres:
```

Gebruiken `with` Zorgt ervoor dat bronnen op de juiste manier worden beheerd, door het bestand bij het afsluiten automatisch op te slaan en te sluiten.

### Stap 2: SmartArt toevoegen aan de eerste dia

Vervolgens voegen we een SmartArt-afbeelding toe aan onze eerste dia. Zo doe je dat:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Hiermee wordt een basiscycluslay-out voor de SmartArt-afbeelding toegevoegd op positie (10, 10) met afmetingen van 400x300 pixels.

### Stap 3: Toegang tot het tweede knooppunt

Toegang tot specifieke knooppunten in uw SmartArt. In dit voorbeeld gebruiken we het tweede knooppunt:

```python
node = smart.nodes[1]
```

Knooppunten worden geïndexeerd vanaf nul; daarom, `nodes[1]` verwijst naar het tweede knooppunt in de lijst.

### Stap 4: De miniatuur van de afbeelding ophalen

Om een miniatuurafbeelding van de vorm binnen het geselecteerde knooppunt te verkrijgen:

```python
image = node.shapes[0].get_image()
```

Hiermee wordt de afbeelding van de eerste vorm als miniatuur opgehaald uit het opgegeven SmartArt-knooppunt.

### Stap 5: Sla de opgehaalde afbeelding op

Sla ten slotte deze miniatuur op de gewenste locatie op in JPEG-formaat:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}