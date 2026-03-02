---
date: '2026-03-02'
description: Leer hoe je een boxplot in Java maakt, een diagram aan een dia toevoegt
  en een box‑whisker‑diagram in PowerPoint genereert met Aspose.Slides voor Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Maak een boxplot in Java met Aspose.Slides voor PowerPoint
url: /nl/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je box‑and‑whisker‑grafieken in PowerPoint met Aspose.Slides voor Java

In deze gids **maak je een box plot java** met Aspose.Slides en embed je de grafiek direct in een PowerPoint‑dia. Het creëren van visueel aantrekkelijke datapresentaties is cruciaal in de hedendaagse data‑gedreven wereld, en grafieken zijn onmisbare hulpmiddelen hiervoor. Als je box‑and‑whisker‑grafieken wilt genereren binnen PowerPoint met Java, biedt de Aspose.Slides‑bibliotheek een robuuste oplossing. Deze tutorial leidt je stap‑voor‑stap door het maken en configureren van deze grafieken met Aspose.Slides voor Java.

## Wat je zult leren

- Het opzetten van je omgeving voor Aspose.Slides voor Java  
- Stappen om **grafiek toe te voegen aan dia** en een box‑whisker‑grafiek te genereren in PowerPoint met Java  
- Best practices voor het optimaliseren van prestaties bij het werken met Aspose.Slides  
- Praktische toepassingen van box‑and‑whisker‑grafieken  

## Snelle antwoorden
- **Welke bibliotheek maakt een box plot in Java?** Aspose.Slides voor Java.  
- **Welk grafiektype wordt gebruikt?** `ChartType.BoxAndWhisker`.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik meerdere series toevoegen?** Ja – herhaal het series‑creatieblok voor elke dataset.  
- **In welk formaat is het uiteindelijke bestand?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Voorvereisten

Om deze tutorial te volgen, zorg dat je het volgende hebt:

- **Java Development Kit (JDK)**: JDK 8 of hoger moet geïnstalleerd zijn.  
- **Aspose.Slides voor Java Library**: Essentieel voor het verwerken van PowerPoint‑presentaties in Java.  
- **IDE**: Een Integrated Development Environment zoals IntelliJ IDEA of Eclipse om je code te schrijven en uit te voeren.  

## Aspose.Slides voor Java installeren

Om Aspose.Slides te gebruiken, voeg je het toe als dependency. Je kunt dit beheren via Maven, Gradle of door direct te downloaden.

### Maven

Voeg de volgende dependency toe in je `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

In je `build.gradle`, voeg toe:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct downloaden

Download anders de nieuwste versie vanaf [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Licentie‑acquisitie

- **Gratis proefversie**: Begin met een gratis proefversie om de functionaliteit te verkennen.  
- **Tijdelijke licentie**: Verkrijg een tijdelijke licentie voor evaluatiedoeleinden.  
- **Aankoop**: Voor volledige functionaliteit kun je overwegen een licentie aan te schaffen.

Om Aspose.Slides te initialiseren, zorg dat je de bibliotheek in je classpath hebt en stel eventuele licentie‑vereisten in zoals nodig.

## Implementatie‑gids

Laten we nu de stap‑voor‑stap code induiken. Elk blok wordt uitgelegd vóór de snippet zodat je precies weet wat het doet.

### Wat is een box plot en waarom gebruiken in Java?

Een box‑and‑whisker‑grafiek (vaak een *box plot* genoemd) visualiseert de gegevensverdeling — mediaan, kwartielen en uitschieters — in een compacte vorm. In Java kun je deze grafiek programmatisch genereren en direct in PowerPoint‑decks embedden, waardoor handmatige grafiekcreatie overbodig wordt.

### Waarom een grafiek toevoegen aan een dia met Aspose.Slides?

Aspose.Slides abstraheert de low‑level OpenXML‑details en biedt een vloeiende API om grafieken te maken, te stijlen en te exporteren. Dit betekent dat je rapportgeneratie kunt automatiseren, consistente branding kunt leveren en grafieken kunt integreren in grotere Java‑workflows.

### Stap 1: Maak of open een presentatie

Open eerst een bestaande PPTX of start een nieuwe:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Tip:** Als het bestand niet bestaat, maakt Aspose.Slides automatisch een nieuwe lege presentatie voor je.

### Stap 2: Voeg een box‑and‑whisker‑grafiek toe aan de dia

Plaats de grafiek waar je deze nodig hebt door de positie en grootte (in points) op te geven:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Stap 3: Wis bestaande gegevens

Voordat je nieuwe data invoert, verwijder je eventuele placeholder‑categorieën of series:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Stap 4: Configureer categorieën

Voeg de categorieën (X‑as‑labels) toe die onder elke box verschijnen:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Opmerking:** Pas de labeltekst aan zodat deze overeenkomt met je datadomein (bijv. “Q1”, “Product A”).

### Stap 5: Maak en pas de series aan

Maak nu een series, stel visuele opties in en voer de numerieke datapunten in:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Je kunt de `int[] data`‑array vervangen door waarden die uit een database, CSV‑bestand of een andere bron worden gelezen.

### Stap 6: Sla de presentatie op

Sla de wijzigingen op in een nieuw PPTX‑bestand:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Stap 7: Ruim bronnen op

Dispose altijd het `Presentation`‑object om native resources vrij te geven:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktische toepassingen

Box‑and‑whisker‑grafieken zijn van onschatbare waarde bij statistische analyse en datavisualisatie. Enkele scenario’s waarin ze uitblinken:

1. **Financiële analyse** – Visualiseer omzetverdeling over regio’s.  
2. **Kwaliteitscontrole** – Spot uitschieters in meetwaarden van de productie.  
3. **Academisch onderzoek** – Toon variabiliteit van experimentele resultaten.  
4. **Marktonderzoek** – Vergelijk productprestaties over demografische groepen.  

Het integreren van deze grafieken in PowerPoint‑decks stelt belanghebbenden in staat complexe data in één oogopslag te begrijpen.

## Prestatie‑overwegingen

Wanneer je met Aspose.Slides in Java werkt, houd dan rekening met de volgende tips:

- **Geheugenbeheer** – Dispose `Presentation`‑objecten direct na gebruik.  
- **Gegevensverwerking** – Laad alleen de data die je nodig hebt; vermijd het direct invoeren van enorme datasets in het grafiek‑werkboek.  
- **Lazy loading** – Als je veel dia’s genereert, overweeg dan om grafieken alleen te maken voor de dia’s die daadwerkelijk getoond worden.

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Grafiek verschijnt leeg** | Gegevenscellen niet correct gevuld | Controleer of `wb.getCell` naar de juiste rij/kolom verwijst en dat de waarde niet `null` is. |
| **Uitschieters worden niet getoond** | `setShowOutlierPoints` staat op `false` | Zorg dat `series.setShowOutlierPoints(true)` wordt aangeroepen. |
| **Geheugenlek** | Presentatie niet disposed | Plaats het gebruik altijd in try/finally en roep `dispose()` aan. |
| **Onjuiste kwartielen** | Standaard `Inclusive`‑methode gebruikt | Schakel over naar `Exclusive` via `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Veelgestelde vragen

**Q1: Wat is een box‑and‑whisker‑grafiek?**  
Een box‑and‑whisker‑grafiek, ook wel box plot genoemd, toont de verdeling van data op basis van vijf samenvattende statistieken: minimum, eerste kwartiel, mediaan, derde kwartiel en maximum, plus eventuele uitschieters.

**Q2: Kan ik het uiterlijk van de box‑and‑whisker‑grafiek aanpassen?**  
Ja. Met Aspose.Slides kun je kleuren, lijntypen, marker‑vormen wijzigen en zelfs datalabels toevoegen via de opmaak‑API van de grafiek.

**Q3: Is het mogelijk om meerdere series in één grafiek te verwerken?**  
Absoluut. Herhaal het series‑creatieblok voor elke dataset die je wilt visualiseren.

**Q4: Hoe los ik problemen op waarbij data niet correct wordt weergegeven?**  
Zorg ervoor dat de data correct naar de werkboekcellen wordt geschreven en dat zichtbaarheidseigenschappen zoals `setShowMeanLine` zijn ingeschakeld.

**Q5: Waar kan ik ondersteuning krijgen als ik tegen problemen aanloop?**  
Bezoek het [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) voor community‑ondersteuning, of raadpleeg de officiële documentatie.

**Q6: Ondersteunt Aspose.Slides andere grafiektype­n?**  
Ja, het ondersteunt lijn-, staaf-, taart-, spreidings-, radar‑ en vele andere grafiektype­n.

**Q7: Kan ik grafieken genereren in een headless server‑omgeving?**  
De bibliotheek werkt volledig in server‑side scenario’s; er is geen UI vereist.

## Resources

- **Documentatie**: Verken gedetailleerde API‑referenties op [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Toegang tot Aspose.Slides‑releases [hier](https://releases.aspose.com/slides/java/)  
- **Aankoop**: Koop een licentie om alle functies te ontgrendelen via [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Gratis proefversie & tijdelijke licentie**: Begin met een gratis proefversie of vraag een tijdelijke licentie aan [hier](https://releases.aspose.com/slides/java/)  

Door deze gids te volgen, kun je nu programmatiche box‑and‑whisker‑grafieken genereren in je Java‑applicaties en ze direct embedden in PowerPoint‑presentaties. Veel programmeerplezier!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-02  
**Getest met:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Auteur:** Aspose