---
"date": "2025-04-17"
"description": "Leer hoe u grafieken met percentagelabels in Java-presentaties kunt maken, aanpassen en opslaan met Aspose.Slides. Verbeter uw presentatievaardigheden vandaag nog!"
"title": "Grafieken maken en aanpassen in Java-presentaties met Aspose.Slides"
"url": "/nl/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Grafieken maken en aanpassen in Java-presentaties met Aspose.Slides

## Invoering
Het maken van boeiende presentaties omvat vaak meer dan alleen tekst; het vereist dynamische grafieken die informatie effectief overbrengen. Als je je Java-presentaties wilt verbeteren met geavanceerde grafiekfuncties in Aspose.Slides, dan is deze tutorial iets voor jou. We begeleiden je bij het maken van een presentatie, het toevoegen en configureren van grafieken, het berekenen van totalen, het weergeven van percentagelabels en het opslaan van je werk – allemaal in slechts een paar eenvoudige stappen.

**Wat je leert:**
- Presentaties met grafieken maken en aanpassen met Aspose.Slides voor Java
- Categorietotalen berekenen in grafieken
- Gegevens weergeven als percentagelabels in grafieken
- Presentaties opslaan met verbeterde grafiekfuncties

Laten we eens kijken naar de vereisten die je moet hebben voordat je begint.

## Vereisten
Om deze tutorial te kunnen volgen, hebt u het volgende nodig:

- **Java-ontwikkelingskit (JDK)**: Versie 8 of hoger.
- **IDE**: Zoals IntelliJ IDEA, Eclipse of een andere door Java ondersteunde IDE.
- **Aspose.Slides voor Java-bibliotheek**:Dit is cruciaal voor het verwerken van presentatiefuncties.

### Vereiste bibliotheken en versies
Je hebt Aspose.Slides voor Java nodig. Zo neem je het op in je project:

**Kenner:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

U kunt de nieuwste versie ook rechtstreeks downloaden van [Aspose.Slides voor Java-releases](https://releases.aspose.com/slides/java/).

### Omgevingsinstelling
Zorg ervoor dat uw ontwikkelomgeving is geconfigureerd voor het gebruik van JDK 8 of hoger en dat uw IDE is ingesteld voor het beheren van afhankelijkheden met behulp van Maven of Gradle.

**Licentieverwerving:**
- **Gratis proefperiode**: Toegang tot basisfuncties voor testdoeleinden.
- **Tijdelijke licentie**: Test geavanceerde functies zonder evaluatiebeperkingen.
- **Aankoop**: Voor commercieel gebruik op de lange termijn kunt u overwegen een licentie aan te schaffen.

## Aspose.Slides instellen voor Java
Begin met het installeren van de Aspose.Slides-bibliotheek in je Java-project. Zo initialiseer en configureer je deze:

1. Voeg de afhankelijkheid toe via Maven of Gradle zoals hierboven weergegeven.
2. Importeer de benodigde Aspose.Slides-pakketten:
   ```java
   import com.aspose.slides.*;
   ```

3. Initialiseer een nieuwe `Presentation` aanleg:
   ```java
   Presentation presentation = new Presentation();
   ```

Met deze instelling kunt u programmatisch presentaties bouwen.

## Implementatiegids

### Maak en pas grafieken aan in uw presentatie

#### Overzicht
Om een grafiek te maken, moet u uw presentatie initialiseren, dia's openen en een grafiek met specifieke kenmerken toevoegen, zoals type, positie en grootte.

**Stappen:**
1. **Presentatie-instantie maken**: Begin met het maken van een exemplaar van de `Presentation` klas.
2. **Toegangsdia**: Haal de eerste dia op met behulp van `get_Item(0)`.
3. **Grafiek toevoegen**: Gebruik `addChart()` om een gestapeld kolomdiagram toe te voegen op opgegeven coördinaten met gedefinieerde afmetingen.

```java
// Functie: een presentatie met grafiek maken
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Totalen voor categorieën berekenen

#### Overzicht
Bij het berekenen van categorietotalen worden alle reeksen in het diagram doorlopen om de waarden per categorie op te tellen.

**Stappen:**
1. **Initialiseer Array**: Maak een array om totale waarden in op te slaan.
2. **Herhaal categorieën en series**: Gebruik geneste lussen om totalen voor elke categorie uit alle reeksen te verzamelen.

```java
// Functie: Totalen berekenen voor categorieën in een grafiek
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Gegevens weergeven als percentagelabels in een grafiek

#### Overzicht
Deze functie richt zich op het configureren van gegevenslabels om waarden als percentages weer te geven, wat zorgt voor een duidelijke visualisatie.

**Stappen:**
1. **Serielabels configureren**: Stel labeleigenschappen in, zoals lettergrootte en zichtbaarheid van legendasleutels.
2. **Percentages berekenen**: Bereken het percentage voor elk gegevenspunt op basis van de totale categorie-waarde.
3. **Labeltekst instellen**: Formatteer labels om percentages met twee decimalen weer te geven.

```java
// Functie: Gegevens weergeven als percentagelabels op een grafiek
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Presentatie met grafiek opslaan

#### Overzicht
Sla ten slotte uw presentatie op in het opgegeven pad in PPTX-formaat.

**Stappen:**
1. **Opslaan Methode**: Gebruik de `save()` methode op de `Presentation` aanleg.
2. **Afvoer van hulpbronnen**: Zorg ervoor dat bronnen worden vrijgegeven na het opslaan.

```java
// Functie: Presentatie opslaan met grafiek
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Praktische toepassingen

1. **Financiële verslaggeving**: Gebruik diagrammen om de omzetgroeipercentages van verschillende afdelingen weer te geven.
2. **Verkoopgegevensanalyse**: Visualiseer verkoopgegevens per regio met percentagelabels voor duidelijker inzicht.
3. **Educatieve presentaties**: Verbeter academische presentaties met visuele statistieken.
4. **Marketingcampagnes**: Geef prestatiegegevens van de campagne weer als aantrekkelijke beelden.
5. **Zakelijke strategievergaderingen**:Gebruik diagrammen om complexe gegevens over te brengen in strategische planningsdiscussies.

## Prestatieoverwegingen
- **Geheugenbeheer**: Afvoeren `Presentation` objecten zo snel mogelijk verwijderen om bronnen vrij te maken.
- **Optimaliseer het laden van grafieken**: Laad indien mogelijk alleen essentiële grafiekelementen in het geheugen.
- **Batchverwerking**:Wanneer u meerdere presentaties verwerkt, kunt u overwegen deze in batches te verwerken. Zo beheert u het resourceverbruik effectief.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}