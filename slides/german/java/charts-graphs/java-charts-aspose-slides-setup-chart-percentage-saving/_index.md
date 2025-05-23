---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides Diagramme mit Prozentbeschriftungen in Java-Präsentationen erstellen, anpassen und speichern. Verbessern Sie noch heute Ihre Präsentationsfähigkeiten!"
"title": "Erstellen und Anpassen von Diagrammen in Java-Präsentationen mit Aspose.Slides"
"url": "/de/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen und Anpassen von Diagrammen in Java-Präsentationen mit Aspose.Slides

## Einführung
Das Erstellen überzeugender Präsentationen erfordert oft mehr als nur Text; es erfordert dynamische Diagramme, die Informationen effektiv vermitteln. Wenn Sie Ihre Java-basierten Präsentationen mit Aspose.Slides um anspruchsvolle Diagrammfunktionen erweitern möchten, ist dieses Tutorial genau das Richtige für Sie. Wir führen Sie durch die Erstellung einer Präsentation, das Hinzufügen und Konfigurieren von Diagrammen, das Berechnen von Summen, das Anzeigen von Prozentangaben und das Speichern Ihrer Arbeit – alles in nur wenigen einfachen Schritten.

**Was Sie lernen werden:**
- So erstellen und passen Sie Präsentationen mit Diagrammen mit Aspose.Slides für Java an
- Berechnen von Kategoriesummen in Diagrammen
- Anzeigen von Daten als Prozentbeschriftungen in Diagrammen
- Speichern von Präsentationen mit erweiterten Diagrammfunktionen

Lassen Sie uns einen Blick auf die Voraussetzungen werfen, die Sie benötigen, bevor Sie beginnen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Java Development Kit (JDK)**: Version 8 oder höher.
- **IDE**: Wie IntelliJ IDEA, Eclipse oder jede Java-unterstützte IDE.
- **Aspose.Slides für die Java-Bibliothek**: Dies ist für die Handhabung von Präsentationsfunktionen von entscheidender Bedeutung.

### Erforderliche Bibliotheken und Versionen
Sie benötigen Aspose.Slides für Java. So binden Sie es in Ihr Projekt ein:

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

Alternativ können Sie die neueste Version direkt herunterladen von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

### Umgebungs-Setup
Stellen Sie sicher, dass Ihre Entwicklungsumgebung für die Verwendung von JDK 8 oder höher konfiguriert ist und dass Ihre IDE für die Verwaltung von Abhängigkeiten mit Maven oder Gradle eingerichtet ist.

**Lizenzerwerb:**
- **Kostenlose Testversion**: Greifen Sie zu Testzwecken auf grundlegende Funktionen zu.
- **Temporäre Lizenz**: Testen Sie erweiterte Funktionen ohne Evaluierungseinschränkungen.
- **Kaufen**: Für eine langfristige kommerzielle Nutzung sollten Sie den Erwerb einer Lizenz in Erwägung ziehen.

## Einrichten von Aspose.Slides für Java
Richten Sie zunächst die Bibliothek Aspose.Slides in Ihrem Java-Projekt ein. So initialisieren und konfigurieren Sie sie:

1. Fügen Sie die Abhängigkeit wie oben gezeigt über Maven oder Gradle hinzu.
2. Importieren Sie die erforderlichen Aspose.Slides-Pakete:
   ```java
   import com.aspose.slides.*;
   ```

3. Initialisieren Sie ein neues `Presentation` Beispiel:
   ```java
   Presentation presentation = new Presentation();
   ```

Mit diesem Setup können Sie mit der programmgesteuerten Erstellung von Präsentationen beginnen.

## Implementierungshandbuch

### Erstellen und Anpassen von Diagrammen in Ihrer Präsentation

#### Überblick
Zum Erstellen eines Diagramms müssen Sie Ihre Präsentation initialisieren, auf Folien zugreifen und ein Diagramm mit bestimmten Attributen wie Typ, Position und Größe hinzufügen.

**Schritte:**
1. **Präsentationsinstanz erstellen**: Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse.
2. **Zugangsrutsche**: Rufen Sie die erste Folie ab mit `get_Item(0)`.
3. **Diagramm hinzufügen**: Verwenden `addChart()` um an angegebenen Koordinaten ein gestapeltes Säulendiagramm mit definierten Abmessungen hinzuzufügen.

```java
// Funktion: Erstellen einer Präsentation mit Diagramm
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

### Berechnen von Summen für Kategorien

#### Überblick
Das Berechnen der Kategoriesummen umfasst das Durchlaufen jeder Reihe im Diagramm, um die Werte pro Kategorie zusammenzufassen.

**Schritte:**
1. **Array initialisieren**: Erstellen Sie ein Array zur Speicherung der Gesamtwerte.
2. **Durch Kategorien und Serien iterieren**: Verwenden Sie verschachtelte Schleifen, um Gesamtsummen für jede Kategorie aus allen Serien zu sammeln.

```java
// Funktion: Berechnen von Summen für Kategorien in einem Diagramm
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

### Anzeigen von Daten als Prozentbeschriftungen in einem Diagramm

#### Überblick
Bei dieser Funktion geht es darum, Datenbeschriftungen so zu konfigurieren, dass Werte als Prozentsätze angezeigt werden, was für mehr Übersichtlichkeit in der Visualisierung sorgt.

**Schritte:**
1. **Serienbeschriftungen konfigurieren**: Richten Sie Beschriftungseigenschaften wie Schriftgröße und Sichtbarkeit der Legendenschlüssel ein.
2. **Prozentsätze berechnen**: Berechnen Sie den Prozentsatz für jeden Datenpunkt basierend auf dem Gesamtkategoriewert.
3. **Beschriftungstext festlegen**: Formatieren Sie Beschriftungen, um Prozentsätze mit zwei Dezimalstellen anzuzeigen.

```java
// Funktion: Daten als Prozentbeschriftungen in einem Diagramm anzeigen
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

### Präsentation mit Diagramm speichern

#### Überblick
Speichern Sie Ihre Präsentation abschließend im PPTX-Format unter einem angegebenen Pfad.

**Schritte:**
1. **Save-Methode**: Verwenden Sie die `save()` Methode auf der `Presentation` Beispiel.
2. **Ressourcen entsorgen**: Stellen Sie sicher, dass die Ressourcen nach dem Speichern freigegeben werden.

```java
// Funktion: Präsentation mit Diagramm speichern
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Praktische Anwendungen

1. **Finanzberichterstattung**: Verwenden Sie Diagramme, um das Umsatzwachstum in Prozenten aller Abteilungen anzuzeigen.
2. **Verkaufsdatenanalyse**: Visualisieren Sie Verkaufsdaten nach Region mit Prozentbeschriftungen für klarere Einblicke.
3. **Lehrpräsentationen**: Verbessern Sie akademische Präsentationen mit visuellen Statistiken.
4. **Marketingkampagnen**: Zeigen Sie Leistungskennzahlen der Kampagne als ansprechende Grafiken an.
5. **Geschäftsstrategie-Meetings**: Verwenden Sie Diagramme, um komplexe Daten in strategischen Planungsdiskussionen zu vermitteln.

## Überlegungen zur Leistung
- **Speicherverwaltung**: Entsorgen `Presentation` Objekte umgehend, um Ressourcen freizugeben.
- **Optimieren des Diagrammladens**: Laden Sie nach Möglichkeit nur die unbedingt erforderlichen Diagrammelemente in den Speicher.
- **Stapelverarbeitung**: Wenn Sie mehrere Präsentationen verarbeiten, sollten Sie diese in Stapeln verarbeiten, um den Ressourcenverbrauch effektiv zu verwalten.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}