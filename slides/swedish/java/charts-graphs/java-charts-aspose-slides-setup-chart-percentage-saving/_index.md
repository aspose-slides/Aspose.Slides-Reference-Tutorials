---
"date": "2025-04-17"
"description": "Lär dig hur du skapar, anpassar och sparar diagram med procentetiketter i Java-presentationer med Aspose.Slides. Förbättra dina presentationsfärdigheter idag!"
"title": "Skapa och anpassa diagram i Java-presentationer med hjälp av Aspose.Slides"
"url": "/sv/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa och anpassa diagram i Java-presentationer med hjälp av Aspose.Slides

## Introduktion
Att skapa engagerande presentationer innebär ofta mer än bara text; det kräver dynamiska diagram som förmedlar information effektivt. Om du vill förbättra dina Java-baserade presentationer med sofistikerade diagramfunktioner med hjälp av Aspose.Slides, är den här handledningen för dig. Vi guidar dig genom att skapa en presentation, lägga till och konfigurera diagram, beräkna totaler, visa procentetiketter och spara ditt arbete – allt i bara några få enkla steg.

**Vad du kommer att lära dig:**
- Hur man skapar och anpassar presentationer med diagram med Aspose.Slides för Java
- Beräkna kategoritotaler i diagram
- Visa data som procentetiketter i diagram
- Spara presentationer med förbättrade diagramfunktioner

Låt oss gå igenom de förkunskapskrav du behöver innan du börjar.

## Förkunskapskrav
För att följa den här handledningen, se till att du har följande:

- **Java-utvecklingspaket (JDK)**Version 8 eller senare.
- **ID**Såsom IntelliJ IDEA, Eclipse eller någon Java-stödd IDE.
- **Aspose.Slides för Java-biblioteket**Detta är avgörande för att hantera presentationsfunktioner.

### Nödvändiga bibliotek och versioner
Du behöver Aspose.Slides för Java. Så här inkluderar du det i ditt projekt:

**Maven:**
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

Alternativt kan du ladda ner den senaste versionen direkt från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

### Miljöinställningar
Se till att din utvecklingsmiljö är konfigurerad för att använda JDK 8 eller senare och att din IDE är konfigurerad för att hantera beroenden med Maven eller Gradle.

**Licensförvärv:**
- **Gratis provperiod**Åtkomst till grundläggande funktioner för teständamål.
- **Tillfällig licens**Testa avancerade funktioner utan utvärderingsbegränsningar.
- **Köpa**För långsiktig kommersiell användning, överväg att köpa en licens.

## Konfigurera Aspose.Slides för Java
Börja med att konfigurera Aspose.Slides-biblioteket i ditt Java-projekt. Så här initierar och konfigurerar du det:

1. Lägg till beroendet via Maven eller Gradle som visas ovan.
2. Importera de nödvändiga Aspose.Slides-paketen:
   ```java
   import com.aspose.slides.*;
   ```

3. Initiera en ny `Presentation` exempel:
   ```java
   Presentation presentation = new Presentation();
   ```

Den här konfigurationen låter dig börja bygga presentationer programmatiskt.

## Implementeringsguide

### Skapa och anpassa diagram i din presentation

#### Översikt
Att skapa ett diagram innebär att du initierar din presentation, öppnar bilder och lägger till ett diagram med specifika attribut som typ, position och storlek.

**Steg:**
1. **Skapa presentationsinstans**Börja med att skapa en instans av `Presentation` klass.
2. **Åtkomstbild**Hämta den första bilden med hjälp av `get_Item(0)`.
3. **Lägg till diagram**Användning `addChart()` för att lägga till ett staplat kolumndiagram vid angivna koordinater med definierade dimensioner.

```java
// Funktion: Skapa en presentation med diagram
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

### Beräkna summor för kategorier

#### Översikt
Att beräkna kategoritotaler innebär att man itererar igenom varje serie i diagrammet för att summera värden per kategori.

**Steg:**
1. **Initiera array**Skapa en array för att innehålla totala värden.
2. **Iterera genom kategorier och serier**Använd kapslade loopar för att ackumulera totaler för varje kategori från alla serier.

```java
// Funktion: Beräkna totaler för kategorier i ett diagram
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

### Visa data som procentuella etiketter i ett diagram

#### Översikt
Den här funktionen fokuserar på att konfigurera dataetiketter för att visa värden som procentsatser, vilket ger tydlighet i visualiseringen.

**Steg:**
1. **Konfigurera serieetiketter**Konfigurera etikettegenskaper som teckenstorlek och synlighet för förklaringsnycklar.
2. **Beräkna procentandelar**Beräkna procentandel för varje datapunkt baserat på det totala kategorivärdet.
3. **Ange etiketttext**Formatera etiketter för att visa procentandelar med två decimaler.

```java
// Funktion: Visa data som procentuella etiketter i ett diagram
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

### Spara presentation med diagram

#### Översikt
Slutligen, spara din presentation till en angiven sökväg i PPTX-format.

**Steg:**
1. **Spara metod**Använd `save()` metod på `Presentation` exempel.
2. **Kassera resurser**Säkerställ att resurser frigörs efter att de har sparats.

```java
// Funktion: Spara presentation med diagram
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Praktiska tillämpningar

1. **Finansiell rapportering**Använd diagram för att visa intäktstillväxt i procent över olika avdelningar.
2. **Analys av försäljningsdata**Visualisera försäljningsdata per region med procentuella etiketter för tydligare insikter.
3. **Utbildningspresentationer**Förbättra akademiska presentationer med visuell statistik.
4. **Marknadsföringskampanjer**Visa kampanjresultatsstatistik som engagerande visuella element.
5. **Möten om affärsstrategi**Använd diagram för att förmedla komplex data i strategiska planeringsdiskussioner.

## Prestandaöverväganden
- **Minneshantering**Kassera `Presentation` objekten omedelbart för att frigöra resurser.
- **Optimera diagraminläsning**Ladda endast in viktiga diagramelement i minnet om möjligt.
- **Batchbearbetning**När du bearbetar flera presentationer, överväg att hantera dem i omgångar för att hantera resursförbrukningen effektivt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}