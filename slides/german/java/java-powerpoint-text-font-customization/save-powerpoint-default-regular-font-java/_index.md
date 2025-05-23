---
"description": "Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java programmgesteuert bearbeiten. Meistern Sie die Java-PowerPoint-Bedienung mit Schritt-für-Schritt-Tutorials."
"linktitle": "Speichern Sie PowerPoint mit der Standardschriftart „Regular“ mithilfe von Java"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Speichern Sie PowerPoint mit der Standardschriftart „Regular“ mithilfe von Java"
"url": "/de/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Speichern Sie PowerPoint mit der Standardschriftart „Regular“ mithilfe von Java

## Einführung
In der Java-Entwicklung kann die programmgesteuerte Erstellung und Bearbeitung von PowerPoint-Präsentationen die Produktivität und die Anpassungsmöglichkeiten erheblich steigern. Aspose.Slides für Java ist eine robuste Bibliothek, die Entwicklern die effiziente Bearbeitung von PowerPoint-Dateien ermöglicht und umfassende Funktionen von einfachen Änderungen bis hin zu komplexen Präsentationen bietet.
## Voraussetzungen
Bevor Sie mit der Verwendung von Aspose.Slides für Java beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Java Development Kit (JDK): Aspose.Slides für Java erfordert JDK 1.8 oder höher, um ordnungsgemäß zu funktionieren.
2. Aspose.Slides für Java JAR: Laden Sie die neueste Version von Aspose.Slides für Java herunter von [Hier](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie IntelliJ IDEA, Eclipse oder eine andere Java-IDE Ihrer Wahl.
4. Grundlegende Kenntnisse in Java: Kenntnisse der Grundlagen der Programmiersprache Java sind erforderlich.

## Pakete importieren
Um Aspose.Slides für Java zu verwenden, importieren Sie die erforderlichen Pakete:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Dadurch wird sichergestellt, dass Sie Zugriff auf alle von Aspose.Slides für Java bereitgestellten Klassen und Methoden haben.
## Schritt 1: Richten Sie Ihr Projekt ein
Erstellen Sie zunächst ein neues Java-Projekt in Ihrer IDE und fügen Sie die JAR-Datei „Aspose.Slides für Java“ in den Build-Pfad Ihres Projekts ein.
## Schritt 2: Präsentationsobjekt initialisieren
Instanziieren Sie ein `Presentation` Objekt, indem Sie eine vorhandene PowerPoint-Datei (.pptx) aus Ihrem lokalen Verzeichnis laden.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Präsentation laden
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Ersetzen `"Your Document Directory"` Und `"Your Output Directory"` mit Ihren tatsächlichen Dateipfaden.
## Schritt 3: Präsentation mit den Standardschriftarten speichern
Geben Sie die Standardschriftart für die Ausgabeformate (HTML und PDF) an mit `HtmlOptions` Und `PdfOptions` jeweils.
```java
try {
    // HTML-Speicheroptionen
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF-Speicheroptionen
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Stellen Sie sicher, dass Sie `"Arial Black"` Und `"Lucida Console"` mit den gewünschten Standardschriftarten.

## Abschluss
Mit diesen Schritten haben Sie gelernt, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Java effektiv bearbeiten. So können Sie Aufgaben automatisieren, Präsentationen anpassen und Ihre Java-Anwendungen mit erweiterten PowerPoint-Funktionen erweitern.
## Häufig gestellte Fragen
### Kann Aspose.Slides für Java mit älteren JDK-Versionen funktionieren?
Aspose.Slides für Java erfordert aus Kompatibilitätsgründen JDK 1.8 oder höher.
### Wie kann ich eine vorübergehende Lizenz für Aspose.Slides für Java erhalten?
Eine vorläufige Lizenz erhalten Sie bei [Hier](https://purchase.aspose.com/temporary-license/).
### Wo finde ich ausführlichere Dokumentation zu Aspose.Slides für Java?
Erkunden Sie die umfassende Dokumentation [Hier](https://reference.aspose.com/slides/java/).
### Gibt es Community-Support für Aspose.Slides für Java?
Ja, Sie können Community-Support erhalten [Hier](https://forum.aspose.com/c/slides/11).
### Kann ich Aspose.Slides für Java kostenlos testen?
Ja, laden Sie eine kostenlose Testversion herunter [Hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}