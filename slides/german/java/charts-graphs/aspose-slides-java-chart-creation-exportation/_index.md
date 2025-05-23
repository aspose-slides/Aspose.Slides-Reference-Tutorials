---
"date": "2025-04-17"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides in Java Diagramme erstellen und exportieren. Lernen Sie Datenvisualisierungstechniken mit Schritt-für-Schritt-Anleitungen und Codebeispielen."
"title": "Aspose.Slides Java&#58; Erstellen und Exportieren von Diagrammen zur Datenvisualisierung"
"url": "/de/java/charts-graphs/aspose-slides-java-chart-creation-exportation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen und Exportieren von Diagrammen mit Aspose.Slides Java

**Beherrschen Sie Datenvisualisierungstechniken mit Aspose.Slides für Java**

In der heutigen datengetriebenen Welt ist eine effektive Datenvisualisierung unerlässlich, um fundierte Entscheidungen zu treffen. Die Integration von Diagrammfunktionen in Ihre Java-Anwendungen kann Rohdaten in überzeugende visuelle Geschichten verwandeln. Dieses Tutorial führt Sie durch das Erstellen und Exportieren von Diagrammen mit Aspose.Slides für Java und stellt sicher, dass Ihre Präsentationen sowohl informativ als auch visuell ansprechend sind.

**Was Sie lernen werden:**
- Müheloses Laden und Bearbeiten von Präsentationsdateien
- Fügen Sie Ihren Folien verschiedene Diagrammtypen hinzu
- Nahtloser Export von Diagrammdaten in externe Arbeitsmappen
- Festlegen eines externen Arbeitsmappenpfads für eine effiziente Datenverwaltung

Lass uns anfangen!

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgende Einrichtung bereit haben:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java** Version 25.4 oder höher

### Anforderungen für die Umgebungseinrichtung
- Java Development Kit (JDK) 16 oder höher
- Ein Code-Editor oder eine IDE wie IntelliJ IDEA oder Eclipse

### Voraussetzungen
- Grundlegende Kenntnisse der Java-Programmierung
- Vertrautheit mit Maven- oder Gradle-Build-Systemen

## Einrichten von Aspose.Slides für Java
Um Aspose.Slides verwenden zu können, müssen Sie es in Ihr Projekt einbinden. So geht's:

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativ können Sie [Laden Sie die neueste Version direkt herunter](https://releases.aspose.com/slides/java/).

### Schritte zum Lizenzerwerb
Aspose.Slides bietet eine kostenlose Testlizenz an, um alle Funktionen zu testen. Sie können auch eine temporäre Lizenz beantragen oder eine Lizenz für eine erweiterte Nutzung erwerben. Folgen Sie diesen Schritten:
1. Besuchen Sie die [Aspose-Kaufseite](https://purchase.aspose.com/buy) um Ihre Lizenz zu erhalten.
2. Laden Sie eine kostenlose Testversion herunter von [Veröffentlichungen](https://releases.aspose.com/slides/java/).
3. Beantragen Sie eine vorläufige Lizenz [Hier](https://purchase.aspose.com/temporary-license/).

Sobald Sie die Lizenzdatei haben, initialisieren Sie sie in Ihrer Java-Anwendung:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementierungshandbuch
### Funktion 1: Präsentation laden
Das Laden einer Präsentation ist der erste Schritt jeder Manipulationsaufgabe.

#### Überblick
Diese Funktion zeigt, wie eine vorhandene PowerPoint-Datei mit Aspose.Slides für Java geladen wird.

#### Schrittweise Implementierung
**Diagramm zur Folie hinzufügen**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Laden einer vorhandenen Präsentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Bereinigen von Ressourcen
        if (pres != null) pres.dispose();
    }
}
```
**Erläuterung:**
- `Presentation` wird mit dem Pfad zu Ihrem `.pptx` Datei.
- Entsorgen Sie immer `Presentation` Einwände gegen kostenlose Ressourcen.

### Funktion 2: Diagramm zur Folie hinzufügen
Durch das Hinzufügen eines Diagramms kann die Datenpräsentation erheblich verbessert werden.

#### Überblick
Diese Funktion zeigt, wie Sie der ersten Folie einer Präsentation ein Kreisdiagramm hinzufügen.

#### Schrittweise Implementierung
**Diagramm zur Folie hinzufügen**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Fügen Sie ein Kreisdiagramm an Position (50, 50) mit Breite 400 und Höhe 600 hinzu
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Erläuterung:**
- `addChart` Die Methode wird verwendet, um ein Kreisdiagramm einzufügen.
- Zu den Parametern gehören der Diagrammtyp und seine Position/Größe auf der Folie.

### Funktion 3: Diagrammdaten in externe Arbeitsmappe exportieren
Durch das Exportieren der Daten sind weitere Analysen außerhalb von PowerPoint möglich.

#### Überblick
Diese Funktion demonstriert das Exportieren von Diagrammdaten aus einer Präsentation in eine externe Excel-Arbeitsmappe.

#### Schrittweise Implementierung
**Daten exportieren**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Legen Sie den Pfad zu Ihrem Dokumentverzeichnis und Ausgabeverzeichnis fest
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Greifen Sie auf das Diagramm der ersten Folie zu
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Definieren Sie den Pfad für die externe Arbeitsmappe
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Exportieren Sie Diagrammdaten in einen Excel-Stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Erläuterung:**
- `readWorkbookStream` extrahiert die Diagrammdaten.
- Die Daten werden in eine Excel-Datei geschrieben mit `FileOutputStream`.

### Funktion 4: Externe Arbeitsmappe für Diagrammdaten festlegen
Durch die Verknüpfung von Diagrammen mit externen Arbeitsmappen kann die Datenverwaltung optimiert werden.

#### Überblick
Diese Funktion demonstriert das Einrichten eines externen Arbeitsmappenpfads zum Speichern von Diagrammdaten.

#### Schrittweise Implementierung
**Festlegen des externen Arbeitsmappenpfads**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Legen Sie den Pfad zu Ihrem Dokumentverzeichnis fest
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Greifen Sie auf das Diagramm der ersten Folie zu
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Definieren und Festlegen des Pfads für die externe Arbeitsmappe
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Erläuterung:**
- `setExternalWorkbook` verknüpft das Diagramm mit einer Excel-Datei und ermöglicht so dynamische Datenaktualisierungen.

## Praktische Anwendungen
Aspose.Slides bietet vielseitige Lösungen für verschiedene Szenarien:

1. **Geschäftsberichte:** Erstellen Sie detaillierte Berichte mit Diagrammen direkt aus Java-Anwendungen.
2. **Akademische Präsentationen:** Erweitern Sie Bildungsinhalte mit interaktiven Diagrammen.
3. **Finanzanalyse:** Exportieren Sie Finanzdaten zur eingehenden Analyse nach Excel.
4. **Marketinganalyse:** Visualisieren Sie die Kampagnenleistung mithilfe dynamischer Diagramme.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}