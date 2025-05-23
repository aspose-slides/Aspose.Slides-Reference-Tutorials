---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie Datumsformate für Kategorieachsen mit Aspose.Slides für Java anpassen. Optimieren Sie Ihre Diagramme mit einer individuellen Datenpräsentation – ideal für Jahresberichte und mehr."
"title": "So legen Sie ein benutzerdefiniertes Datumsformat auf der Kategorieachse in Aspose.Slides Java fest | Leitfaden zur Datenvisualisierung"
"url": "/de/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie ein benutzerdefiniertes Datumsformat auf der Kategorieachse in Aspose.Slides Java fest | Leitfaden zur Datenvisualisierung

In der heutigen datengetriebenen Welt ist die klare Darstellung von Informationen entscheidend für wirkungsvolle Entscheidungen. Beim Erstellen von Diagrammen mit Aspose.Slides für Java kann die Anpassung des Datumsformats auf der Kategorieachse sowohl die Verständlichkeit als auch die Präsentationsqualität erheblich verbessern. Diese Anleitung führt Sie durch die Einrichtung eines benutzerdefinierten Datumsformats in Aspose.Slides, um die visuelle Attraktivität und Datenübersicht Ihrer Folien zu verbessern.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für Java
- Implementieren benutzerdefinierter Datumsformate auf der Kategorieachse
- Konvertieren von Gregorianischen Kalenderdaten in das OLE-Automatisierungs-Datumsformat
- Praktische Anwendungen dieser Funktionen in realen Szenarien

Lassen Sie uns einen Blick darauf werfen, wie Sie dies ganz einfach erreichen können!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:

### Erforderliche Bibliotheken und Versionen:
- **Aspose.Slides für Java**: Sie benötigen Version 25.4 oder höher.

### Anforderungen für die Umgebungseinrichtung:
- Eine Entwicklungsumgebung, die Java-Code ausführen kann (z. B. IntelliJ IDEA, Eclipse oder NetBeans).
- Maven oder Gradle sind in Ihrem Projekt zur Verwaltung von Abhängigkeiten konfiguriert.

### Erforderliche Kenntnisse:
- Grundlegende Kenntnisse der Java-Programmierung.
- Vertrautheit mit der Verwendung von Diagrammkomponenten in Präsentationen.

## Einrichten von Aspose.Slides für Java

Um mit Aspose.Slides für Java zu arbeiten, binden Sie es als Abhängigkeit in Ihr Projekt ein. Nachfolgend finden Sie die Installationsanweisungen:

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

Alternativ können Sie [Laden Sie die neueste Version herunter](https://releases.aspose.com/slides/java/) direkt von der offiziellen Aspose-Site.

### Lizenzerwerb:
- **Kostenlose Testversion**: Beginnen Sie mit einer kostenlosen Testversion, um die Funktionen zu erkunden.
- **Temporäre Lizenz**: Fordern Sie eine temporäre Lizenz für erweiterte Tests an.
- **Kaufen**: Für eine langfristige Nutzung sollten Sie ein Abonnement erwerben. Besuchen Sie [Aspose Kauf](https://purchase.aspose.com/buy) für Details.

### Grundlegende Initialisierung:

So können Sie Aspose.Slides in Ihrem Projekt initialisieren:
```java
import com.aspose.slides.Presentation;
// Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt
Presentation pres = new Presentation();
```

Kommen wir nun zum Kern dieses Handbuchs!

## Implementierungshandbuch

### Festlegen des Datumsformats für die Kategorieachse

Mit dieser Funktion können Sie die Anzeige von Datumsangaben auf der Kategorieachse Ihres Diagramms anpassen. Nachfolgend finden Sie eine detaillierte Anleitung:

#### 1. Erstellen Sie eine neue Präsentation und ein neues Diagramm
Beginnen Sie mit der Erstellung einer Instanz von `Presentation` und Hinzufügen eines neuen Flächendiagramms.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Präsentation initialisieren
        Presentation pres = new Presentation();
        
        try {
            // Fügen Sie der ersten Folie an der angegebenen Position und in der angegebenen Größe ein Flächendiagramm hinzu
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Access-Diagrammdaten-Arbeitsmappe zum Bearbeiten von Diagrammdaten
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Löschen Sie alle vorhandenen Daten im Diagramm

            // Entfernen Sie alle bereits vorhandenen Kategorien und Serien
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Hinzufügen von Daten zur Kategorieachse mithilfe konvertierter OLE-Automatisierungsdaten
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Erstellen Sie eine neue Reihe und fügen Sie ihr Datenpunkte hinzu
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Stellen Sie den Kategorieachsentyp auf „Datum“ ein und konfigurieren Sie das Zahlenformat
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Formatieren Sie Datumsangaben nur als Jahr

            // Speichern Sie die Präsentation in einem angegebenen Verzeichnis
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Basisdatum für die OLE-Automatisierung-Konvertierung
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // In OLE-Automatisierungsdatum konvertieren
        return String.valueOf(oaDate);
    }
}
```

#### 2. Konvertierung des gregorianischen Kalenderdatums in das OLE-Automatisierungsdatumsformat

Aspose.Slides benötigt Daten im OLE-Automatisierungsformat, einem Standard-Excel-Datumsformat. So konvertieren Sie Ihre Java `GregorianCalendar` Termine:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15. Januar 2021
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Excel-Basisdatum für OLE-Automatisierung
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Tipps zur Fehlerbehebung:
- Stellen Sie sicher, dass das Basisdatum für die Konvertierung (`30 Dec 1899`) wird korrekt analysiert.
- Stellen Sie sicher, dass Ihre Java-Umgebung die erforderlichen Bibliotheken und Klassen unterstützt.
- Wenn Probleme auftreten, prüfen Sie, ob Updates oder Patches für Aspose.Slides verfügbar sind.

### Praktische Anwendungen

Das Anpassen von Datumsformaten kann insbesondere in folgenden Szenarien nützlich sein:
- **Jahresberichte:** Klare Anzeige jährlicher Datentrends.
- **Finanzdiagramme:** Geschäftsperioden korrekt darstellen.
- **Projektzeitpläne:** Hervorheben bestimmter Zeitrahmen oder Meilensteine.

Wenn Sie dieser Anleitung folgen, können Sie Ihre Präsentationen mit Aspose.Slides für Java mit präzisen und optisch ansprechenden Datumsformaten verbessern.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}