---
"date": "2025-04-23"
"description": "Lär dig hur du justerar rotationsvinkeln för diagramtitlar i presentationer med Aspose.Slides för Python, vilket förbättrar läsbarheten och estetiken."
"title": "Hur man ställer in ett diagrams vertikala axeltitelrotation i Aspose.Slides för Python"
"url": "/sv/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man ställer in ett diagrams vertikala axeltitelrotation i Aspose.Slides för Python

## Introduktion

I datapresentationer är det avgörande att förbättra diagrammets läsbarhet. Genom att justera rotationsvinkeln för diagrammets vertikala axeltitel med Aspose.Slides för Python kan titlar få plats snyggt eller sticka ut i dina bilder. Den här handledningen guidar dig genom att ställa in denna rotationsvinkel för att förbättra både funktionalitet och visuell attraktionskraft.

**Vad du kommer att lära dig:**
- Hur man installerar och konfigurerar Aspose.Slides för Python.
- Steg för att lägga till och anpassa diagram i dina bilder.
- Tekniker för att ställa in rotationsvinkeln för diagramtitlar.
- Verkliga tillämpningar för dessa funktioner inom datavisualisering.

Låt oss börja med att gå igenom förutsättningarna innan vi går vidare till implementeringen.

## Förkunskapskrav

Innan du börjar, se till att du har:
- **Python-miljö**Installera Python 3.x från [python.org](https://www.python.org/).
- **Aspose.Slides-biblioteket**Installera via pip för att manipulera presentationer effektivt.
- **Grundläggande kunskaper i Python-programmering**Bekantskap med Pythons syntax och filoperationer hjälper dig att följa med.

## Konfigurera Aspose.Slides för Python

För att använda Aspose.Slides, installera det med pip. Öppna din terminal eller kommandotolk och kör:

```bash
pip install aspose.slides
```

### Steg för att förvärva licens

Aspose erbjuder olika licensalternativ:
- **Gratis provperiod**Ladda ner en testversion från [Asposes lanseringssida](https://releases.aspose.com/slides/python-net/).
- **Tillfällig licens**Skaffa en tillfällig licens för utökade funktioner via [köpportal](https://purchase.aspose.com/temporary-license/).
- **Köpa**Överväg att köpa verktyget om du tycker det är oumbärligt, tillgängligt från [Aspose köpsida](https://purchase.aspose.com/buy).

#### Grundläggande initialisering och installation

Så här initierar du Aspose.Slides i ditt Python-skript:

```python
import aspose.slides as slides

# Skapa ett presentationsobjekt
def main():
    with slides.Presentation() as pres:
        # Din kod kommer att hamna här
        pass

if __name__ == "__main__":
    main()
```

## Implementeringsguide

### Lägga till och anpassa diagram

#### Översikt

I det här avsnittet lägger vi till ett klustrat stapeldiagram i din bild och anpassar det genom att ställa in rotationsvinkeln för dess vertikala axeltitel.

#### Steg:

##### Steg 1: Lägg till ett klustrat kolumndiagram

Börja med att lägga till ett diagram vid specifika koordinater med definierade dimensioner:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Lägg till ett klustrat stapeldiagram på bild 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Steg 2: Konfigurera den vertikala axelns titel

Aktivera och ställ in rotationsvinkeln för den vertikala axelns titel:

```python
def configure_chart(chart):
    # Aktivera den vertikala axelns titel
    chart.axes.vertical_axis.has_title = True
    
    # Ställ in rotationsvinkeln till 90 grader
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Steg 3: Spara din presentation

Slutligen, spara din presentation med ändringarna:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Spara presentationen
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}