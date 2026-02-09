---
date: '2026-02-09'
description: Erlernen Sie, wie Sie Diagramme erstellen und Diagramme mit Aspose.Slides
  für Java nach Excel exportieren. Beherrschen Sie Datenvisualisierung, Business‑Report‑Folien
  und die Erstellung von Arbeitsmappen.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Wie man ein Diagramm mit Aspose.Slides Java erstellt
url: /de/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Wie man ein Diagramm mit Aspose.Slides für Java erstellt

**Meistern Sie Datenvisualisierungstechniken mit Aspose.Slides für Java**

Im heutigen datengetriebenen Umfeld ist *wie man ein Diagramm* programmgesteuert erstellt eine Fähigkeit, die rohe Zahlen in überzeugende visuelle Geschichten verwandeln kann. Ob Sie eine Business‑Report‑Präsentation oder ein interaktives Analyse‑Dashboard bauen – Aspose.Slides für Java gibt Ihnen die Möglichkeit, Diagramme direkt aus Ihrem Code zu erzeugen, anzupassen und zu exportieren. In diesem Tutorial lernen Sie, wie Sie Diagramm‑Objekte erstellen, Diagrammdaten nach Excel exportieren und Diagramme mit externen Arbeitsmappen verknüpfen, um ein nahtloses Datenmanagement zu ermöglichen.

## Schnellantworten
- **Welche Bibliothek wird benötigt?** Aspose.Slides für Java (v25.4+).  
- **Kann ich Diagrammdaten nach Excel exportieren?** Ja – verwenden Sie `readWorkbookStream()` und schreiben die Bytes in eine *.xlsx*-Datei.  
- **Welche Java‑Version ist erforderlich?** JDK 16 oder höher.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testlizenz reicht für die Evaluierung; für die Produktion ist eine permanente Lizenz erforderlich.  
- **Welcher Diagrammtyp wird demonstriert?** Ein Kreis‑Diagramm, aber derselbe Ansatz funktioniert für Balken‑, Linien‑ und andere Diagrammtypen.

## Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine reine Java‑API, die Entwicklern das Erstellen, Bearbeiten und Konvertieren von PowerPoint‑Präsentationen ohne Microsoft Office ermöglicht. Sie unterstützt die gesamte Palette an Diagrammtypen, Datenbindung und Export‑Funktionen und ist damit ideal für **data visualization java**‑Projekte.

## Warum Aspose.Slides zum Erstellen von Diagrammen und zum Export nach Excel verwenden?
- **Keine Office‑Installation** – funktioniert auf jedem Server oder in jeder Cloud‑Umgebung.  
- **Umfangreiche Diagrammbibliothek** – Dutzende von Diagrammtypen und vollständige Stil‑Kontrolle.  
- **Direkter Excel‑Export** – erzeugt eine externe Arbeitsmappe für nachgelagerte Analysen.  
- **Performance‑orientiert** – geringer Speicherverbrauch und schnelle Verarbeitung großer Präsentationen.

## Voraussetzungen
Bevor wir starten, stellen Sie sicher, dass Sie Folgendes haben:

### Erforderliche Bibliotheken und Versionen
- **Aspose.Slides für Java** Version 25.4 oder neuer

### Anforderungen an die Umgebung
- Java Development Kit (JDK) 16 oder höher  
- Eine IDE wie IntelliJ IDEA oder Eclipse (oder ein beliebiger Texteditor Ihrer Wahl)

### Wissensvoraussetzungen
- Grundlegende Java‑Programmierkenntnisse  
- Vertrautheit mit den Build‑Tools Maven oder Gradle

## Aspose.Slides für Java einrichten
Fügen Sie die Bibliothek Ihrem Projekt mit Ihrem bevorzugten Build‑System hinzu.

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
Aspose.Slides bietet eine kostenlose Testlizenz, um die vollen Funktionen zu erkunden. Sie können auch eine temporäre Lizenz beantragen oder eine Lizenz für den erweiterten Gebrauch erwerben. Folgen Sie diesen Schritten:

1. Besuchen Sie die [Aspose‑Kaufseite](https://purchase.aspose.com/buy), um Ihre Lizenz zu erhalten.  
2. Für eine kostenlose Testversion laden Sie sie von [Releases](https://releases.aspose.com/slides/java/) herunter.  
3. Beantragen Sie eine temporäre Lizenz [hier](https://purchase.aspose.com/temporary-license/).

Sobald Sie die Lizenzdatei haben, initialisieren Sie sie in Ihrer Java‑Anwendung:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Schritt‑für‑Schritt‑Anleitung

### Wie man ein Diagramm erstellt – Präsentation laden
Das Laden einer bestehenden PowerPoint‑Datei ist der erste Schritt, bevor Sie Diagramme hinzufügen oder ändern können.

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
- `Presentation` repräsentiert die PowerPoint‑Datei.  
- Rufen Sie stets `dispose()` auf, um native Ressourcen freizugeben.

### Wie man ein Diagramm erstellt – Ein Kreis‑Diagramm zu einer Folie hinzufügen
Jetzt fügen wir ein Kreis‑Diagramm ein, das sich ideal zur Darstellung proportionaler Daten eignet.

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
- `addChart` fügt das Diagramm auf der ersten Folie ein.  
- Die Parameter definieren Diagrammtyp, X/Y‑Position und Größe.

### Wie man Diagrammdaten nach Excel exportiert – Diagrammdaten exportieren
Der Export von Diagrammdaten ermöglicht Analysten, die Zahlen in Excel zu bearbeiten und tiefere Einblicke zu gewinnen.

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
- `readWorkbookStream()` extrahiert die zugrunde liegende Excel‑Arbeitsmappe des Diagramms als Byte‑Array.  
- Das Byte‑Array wird in `externalWorkbook1.xlsx` geschrieben und liefert Ihnen eine sofort einsatzbereite Excel‑Datei.

### Wie man ein Diagramm erstellt – Externe Arbeitsmappe für dynamische Daten setzen
Die Verknüpfung eines Diagramms mit einer externen Arbeitsmappe erlaubt es, das Diagramm einfach durch Bearbeiten der Excel‑Datei zu aktualisieren.

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
- `setExternalWorkbook` bindet das Diagramm an die angegebene Excel‑Datei und ermöglicht Live‑Daten‑Updates, ohne die Folie neu zu erstellen.

## Praktische Anwendungsfälle
Aspose.Slides bietet vielseitige Lösungen für verschiedene reale Szenarien:

1. **Business‑Report‑Folien:** Generieren Sie automatisch Quartals‑Performance‑Diagramme aus Ihren Datenpipelines.  
2. **Akademische Präsentationen:** Wandeln Sie Forschungsdaten in klare Visualisierungen um, ohne manuelles Diagrammzeichnen.  
3. **Finanzanalyse:** Exportieren Sie Diagrammdaten nach Excel, damit Prüfer die Zahlen überprüfen können.  
4. **Marketing‑Analytics:** Visualisieren Sie Kampagnen‑Metriken und teilen Sie editierbare Arbeitsmappen mit Stakeholdern.

## Häufige Probleme & Fehlersuche
- **`FileNotFoundException`** – Stellen Sie sicher, dass `dataDir` auf einen gültigen Ordner zeigt und der Ausgabepfad beschreibbar ist.  
- **Speicherlecks** – Rufen Sie immer `pres.dispose()` in einem `finally`‑Block auf, um native Ressourcen freizugeben.  
- **Diagramm wird nicht angezeigt** – Vergewissern Sie sich, dass der Folien‑Index (`get_Item(0)`) einer tatsächlich vorhandenen Folie entspricht.

## Häufig gestellte Fragen

**F: Kann ich einen anderen Diagrammtyp (z. B. Balken, Linie) mit demselben Code verwenden?**  
A: Ja. Ersetzen Sie `ChartType.Pie` durch einen anderen `ChartType`‑Enum‑Wert wie `ChartType.Bar` oder `ChartType.Line`.

**F: Ist es möglich, die externe Arbeitsmappe nach der Diagrammerstellung zu aktualisieren?**  
A: Absolut. Ändern Sie die Excel‑Datei direkt; das verknüpfte Diagramm spiegelt die Änderungen beim nächsten Öffnen der Präsentation wider.

**F: Benötige ich eine separate Lizenz für die Excel‑Export‑Funktion?**  
A: Nein. Die Excel‑Export‑Funktion ist in der Standard‑Aspose.Slides‑für‑Java‑Lizenz enthalten.

**F: Welche Java‑Versionen werden unterstützt?**  
A: Aspose.Slides für Java unterstützt JDK 16 und neuer; frühere Versionen können funktionieren, werden aber nicht offiziell getestet.

**F: Wie kann ich die erzeugte Excel‑Arbeitsmappe in die PPTX‑Datei einbetten?**  
A: Verwenden Sie `chart.getChartData().setExternalWorkbook(null)`, um die Arbeitsmappe einzubetten, oder behalten Sie den externen Link für dynamische Updates bei.

---

**Zuletzt aktualisiert:** 2026-02-09  
**Getestet mit:** Aspose.Slides für Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}