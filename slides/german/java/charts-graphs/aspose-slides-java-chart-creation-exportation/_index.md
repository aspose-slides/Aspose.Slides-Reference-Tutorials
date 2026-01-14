---
date: '2026-01-14'
description: Erfahren Sie, wie Sie Diagramme mit Aspose.Slides für Java nach Excel
  exportieren und Folien mit Kreisdiagrammen zu Präsentationen hinzufügen. Schritt‑für‑Schritt‑Anleitung
  mit Code.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Diagramm nach Excel exportieren mit Aspose.Slides Java
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramm nach Excel exportieren mit Aspose.Slides für Java

**Meistern Sie Techniken zur Datenvisualisierung mit Aspose.Slides für Java**

In der heutigen datengetriebenen Landschaft ermöglicht es, **Diagramme nach Excel zu exportieren** direkt aus Ihrer Java‑Anwendung, statische PowerPoint‑Visualisierungen in wiederverwendbare, analysierbare Datensätze zu verwandeln. Egal, ob Sie Berichte erstellen, Analyse‑Pipelines speisen oder einfach Geschäfts‑Benutzern erlauben möchten, Diagrammdaten in Excel zu bearbeiten – Aspose.Slides macht das unkompliziert. Dieses Tutorial führt Sie durch das Erstellen eines Diagramms, das Hinzufügen einer Tortendiagramm‑Folie und das Exportieren der Diagrammdaten in eine Excel‑Arbeitsmappe.

**Was Sie lernen werden:**
- Präsentationsdateien mühelos laden und manipulieren
- **Tortendiagramm‑Folie hinzufügen** und weitere Diagrammtypen zu Ihren Folien
- **Diagramm nach Excel exportieren** (Excel aus Diagramm generieren) für nachgelagerte Analysen
- Einen Pfad zu einer externen Arbeitsmappe festlegen, um **Diagramm in Präsentation einzubetten** und die Daten synchron zu halten

Los geht's!

## Schnelle Antworten
- **Was ist der Hauptzweck?** Diagrammdaten von einer PowerPoint‑Folie in eine Excel‑Datei exportieren.  
- **Welche Bibliotheksversion wird benötigt?** Aspose.Slides für Java 25.4 oder neuer.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für den Produktionseinsatz ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich eine Tortendiagramm‑Folie hinzufügen?** Ja – das Tutorial zeigt, wie ein Tortendiagramm hinzugefügt wird.  
- **Ist Java 16 das Minimum?** Ja, JDK 16 oder höher wird empfohlen.

## Wie exportiere ich Diagrammdaten nach Excel mit Aspose.Slides?
Das Exportieren von Diagrammdaten nach Excel ist so einfach wie das Laden einer Präsentation, das Erstellen eines Diagramms und das Schreiben des Arbeitsmappen‑Streams des Diagramms in eine Datei. Die nachstehenden Schritte führen Sie durch den gesamten Vorgang, von der Projektkonfiguration bis zur abschließenden Überprüfung.

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java** Version 25.4 oder neuer

### Anforderungen an die Umgebung
- Java Development Kit (JDK) 16 oder höher
- Ein Code‑Editor oder eine IDE wie IntelliJ IDEA oder Eclipse

### Vorwissen
- Grundlegende Java‑Programmierkenntnisse
- Vertrautheit mit den Build‑Systemen Maven oder Gradle

## Einrichtung von Aspose.Slides für Java
Um Aspose.Slides zu verwenden, binden Sie es über Maven oder Gradle in Ihr Projekt ein.

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

Alternativ können Sie die neueste Version direkt [herunterladen](https://releases.aspose.com/slides/java/).

### Schritte zum Erwerb einer Lizenz
Aspose.Slides bietet eine kostenlose Testlizenz, um alle Funktionen zu erkunden. Sie können auch eine temporäre Lizenz beantragen oder eine Lizenz für den langfristigen Einsatz erwerben. Befolgen Sie diese Schritte:
1. Besuchen Sie die [Aspose‑Kaufseite](https://purchase.aspose.com/buy), um Ihre Lizenz zu erhalten.  
2. Für eine kostenlose Testversion laden Sie von [Releases](https://releases.aspose.com/slides/java/) herunter.  
3. Beantragen Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

Sobald Sie die Lizenzdatei haben, initialisieren Sie sie in Ihrer Java‑Anwendung:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementierungs‑Leitfaden

### Feature 1: Präsentation laden
Das Laden einer Präsentation ist der erste Schritt für jede Manipulation.

#### Überblick
Dieses Feature zeigt, wie man mit Aspose.Slides für Java eine vorhandene PowerPoint‑Datei lädt.

#### Schritt‑für‑Schritt‑Implementierung
**Präsentation laden**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```
**Erklärung:**  
- `Presentation` wird mit dem Pfad zu Ihrer `.pptx`‑Datei initialisiert.  
- Entsorgen Sie stets das `Presentation`‑Objekt, um native Ressourcen freizugeben.

### Feature 2: Tortendiagramm‑Folie hinzufügen
Das Hinzufügen eines Diagramms kann die Datenpräsentation erheblich verbessern, und viele Entwickler fragen, **wie man eine Diagramm‑Folie** in Java hinzufügt.

#### Überblick
Dieses Feature zeigt, wie man eine **Tortendiagramm‑Folie** (das klassische Szenario „Tortendiagramm‑Folie hinzufügen“) zur ersten Folie einer Präsentation hinzufügt.

#### Schritt‑für‑Schritt‑Implementierung
**Tortendiagramm hinzufügen**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Erklärung:**  
- `addChart` fügt ein Tortendiagramm ein.  
- Die Parameter bestimmen den Diagrammtyp sowie dessen Position/Größe auf der Folie.

### Feature 3: Excel aus Diagramm generieren
Das Exportieren der Diagrammdaten ermöglicht es Ihnen, **Excel aus dem Diagramm zu generieren** für tiefere Analysen.

#### Überblick
Dieses Feature demonstriert das Exportieren von Diagrammdaten aus einer Präsentation in eine externe Excel‑Arbeitsmappe.

#### Schritt‑für‑Schritt‑Implementierung
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
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
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
**Erklärung:**  
- `readWorkbookStream` extrahiert die Arbeitsmappen‑Daten des Diagramms.  
- Das Byte‑Array wird mit `FileOutputStream` in eine `.xlsx`‑Datei geschrieben.

### Feature 4: Diagramm in Präsentation mit externer Arbeitsmappe einbetten
Das Verknüpfen eines Diagramms mit einer externen Arbeitsmappe ermöglicht es Ihnen, **Diagramm in Präsentation einzubetten** und die Daten synchron zu halten.

#### Überblick
Dieses Feature zeigt, wie man einen Pfad zu einer externen Arbeitsmappe festlegt, sodass das Diagramm Daten direkt aus Excel lesen/schreiben kann.

#### Schritt‑für‑Schritt‑Implementierung
**Externen Arbeitsmappen‑Pfad festlegen**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Erklärung:**  
- `setExternalWorkbook` verknüpft das Diagramm mit einer Excel‑Datei und ermöglicht dynamische Aktualisierungen, ohne die Folie neu zu erstellen.

## Praktische Anwendungsfälle
Aspose.Slides bietet vielseitige Lösungen für verschiedene Szenarien:

1. **Geschäftsberichte:** Erstellen Sie detaillierte Berichte mit Diagrammen direkt aus Java‑Anwendungen.  
2. **Akademische Präsentationen:** Verbessern Sie Vorlesungen mit interaktiven Tortendiagramm‑Folien.  
3. **Finanzanalyse:** **Diagramm nach Excel exportieren** für tiefgehende Finanzmodellierung.  
4. **Marketing‑Analyse:** Visualisieren Sie Kampagnen‑Performance und **Excel aus Diagramm generieren** für das Analyse‑Team.

## Häufig gestellte Fragen

**Q: Kann ich diesen Ansatz mit anderen Diagrammtypen (z. B. Balken, Linie) verwenden?**  
A: Auf jeden Fall. Ersetzen Sie `ChartType.Pie` durch einen anderen `ChartType`‑Enum‑Wert.

**Q: Benötige ich eine separate Excel‑Bibliothek, um die exportierte Datei zu lesen?**  
A: Nein. Die exportierte `.xlsx`‑Datei ist eine Standard‑Excel‑Arbeitsmappe, die mit jeder Tabellenkalkulations‑Anwendung geöffnet werden kann.

**Q: Wie wirkt sich die externe Arbeitsmappe auf die Foliengröße aus?**  
A: Das Verknüpfen mit einer externen Arbeitsmappe erhöht die PPTX‑Dateigröße nicht wesentlich; das Diagramm verweist zur Laufzeit auf die Arbeitsmappe.

**Q: Ist es möglich, die Excel‑Daten zu aktualisieren und die Folie automatisch die Änderungen übernehmen zu lassen?**  
A: Ja. Nach dem Aufruf von `setExternalWorkbook werden alle in der Arbeitsmappe gespeicherten Änderungen beim nächsten Öffnen der Präsentation übernommen.

**Q: Was ist, wenn ich mehrere Diagramme aus derselben Präsentation exportieren muss?**  
A: Durchlaufen Sie die Diagrammsammlung jeder Folie, rufen Sie `readWorkbookStream()` für jedes Diagramm auf und schreiben Sie in separate Arbeitsmappen‑Dateien.

---

**Last Updated:** 2026-01-14  
**Tested With:** Aspose.Slides 25.4 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}