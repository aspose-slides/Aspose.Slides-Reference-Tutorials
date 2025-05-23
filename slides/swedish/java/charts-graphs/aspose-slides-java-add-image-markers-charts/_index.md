---
"date": "2025-04-17"
"description": "Lär dig hur du förbättrar dina diagram i Aspose.Slides för Java genom att lägga till anpassade bildmarkörer. Öka engagemanget med visuellt distinkta presentationer."
"title": "Behärska Aspose.Slides Java &#5; Lägga till bildmarkörer i diagram"
"url": "/sv/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Bemästra Aspose.Slides Java: Lägga till bildmarkörer i diagram

## Introduktion
Att skapa visuellt tilltalande presentationer är nyckeln till effektiv kommunikation, och diagram är ett kraftfullt verktyg för att förmedla komplex data koncist. Standarddiagrammarkörer kan ibland vara otillräckliga för att få dina data att sticka ut. Med Aspose.Slides för Java kan du förbättra dina diagram genom att lägga till anpassade bilder som markörer, vilket gör dem mer engagerande och informativa.

I den här handledningen utforskar vi hur du integrerar bildmarkörer i dina diagram med hjälp av Aspose.Slides-biblioteket i Java. Genom att behärska dessa tekniker kommer du att kunna skapa presentationer som fångar uppmärksamhet med sina unika visuella element.

**Vad du kommer att lära dig:**
- Hur man konfigurerar Aspose.Slides för Java
- Skapa en grundläggande presentation och ett diagram
- Lägga till bildmarkörer i diagrammets datapunkter
- Konfigurera markörinställningar för optimal visualisering

Redo att förbättra dina diagram? Låt oss gå igenom förkunskapskraven innan vi sätter igång!

### Förkunskapskrav
För att följa den här handledningen behöver du:
1. **Aspose.Slides för Java-biblioteket**Hämta den via Maven- eller Gradle-beroenden eller genom att ladda ner direkt från Aspose.
2. **Java-utvecklingsmiljö**Se till att JDK 16 är installerat på din dator.
3. **Grundläggande Java-programmeringskunskaper**Bekantskap med Javas syntax och koncept är meriterande.

## Konfigurera Aspose.Slides för Java
Innan vi dyker ner i kod, låt oss konfigurera vår utvecklingsmiljö med de nödvändiga biblioteken.

### Maven-installation
Lägg till följande beroende till din `pom.xml` fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle-installation
Inkludera detta i din `build.gradle` fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternativt kan du ladda ner den senaste versionen från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

#### Steg för att förvärva licens
- **Gratis provperiod**Börja med en tillfällig licens för att utforska Aspose.Slides funktioner.
- **Tillfällig licens**Få tillgång till avancerade funktioner genom att skaffa en tillfällig licens.
- **Köpa**För långvarig användning, överväg att köpa en fullständig licens.

### Grundläggande initialisering och installation
Initiera `Presentation` objekt för att börja skapa bilder:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Din kod för att lägga till bilder och diagram placeras här.
    }
}
```

## Implementeringsguide
Nu ska vi gå igenom processen för att lägga till bildmarkörer i din diagramserie.

### Skapa en ny presentation med ett diagram
Först behöver vi en bild där vi kan lägga till vårt diagram:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initiera presentationsobjektet
        Presentation presentation = new Presentation();

        // Hämta den första bilden från samlingen
        ISlide slide = presentation.getSlides().get_Item(0);

        // Lägg till ett standardlinjediagram med markörer på bilden
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Åtkomst till och konfigurera diagramdata
Nästa steg är att komma åt databladet i vårt diagram för att hantera serier:

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Rensa befintliga serier och lägg till en ny
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Lägg till bildmarkörer till diagramdatapunkter
Nu till den spännande delen – att lägga till bilder som markörer:

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Ladda och lägg till bilder som markörer
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Lägg till datapunkter med bilder som markörer
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Konfigurera diagramseriemarkör och spara presentation
Slutligen, låt oss justera markörstorleken för bättre synlighet och spara vår presentation:

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Ladda och lägg till bilder som markörer (exempel med platshållarbanor)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Slutsats
Genom att följa den här guiden har du lärt dig hur du förbättrar dina diagram i Aspose.Slides för Java genom att lägga till anpassade bildmarkörer. Den här metoden kan avsevärt öka engagemanget och tydligheten i dina presentationer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}