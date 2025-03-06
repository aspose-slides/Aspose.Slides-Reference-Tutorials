---
title: Standardschriftarten in PowerPoint mit Aspose.Slides für Java
linktitle: Standardschriftarten in PowerPoint mit Aspose.Slides für Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java Standardschriftarten in PowerPoint-Präsentationen festlegen. Sorgen Sie mühelos für Konsistenz und verbessern Sie die visuelle Attraktivität.
weight: 11
url: /de/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Das Erstellen von PowerPoint-Präsentationen mit benutzerdefinierten Schriftarten ist in vielen Projekten eine gängige Anforderung. Aspose.Slides für Java bietet eine nahtlose Lösung zum Verwalten von Standardschriftarten und gewährleistet Konsistenz in verschiedenen Umgebungen. In diesem Tutorial führen wir Sie durch den Prozess zum Festlegen von Standardschriftarten in PowerPoint-Präsentationen mit Aspose.Slides für Java.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von der[Download-Seite](https://releases.aspose.com/slides/java/).
3. Grundlegende Java-Kenntnisse: Vertrautheit mit den Grundlagen der Programmiersprache Java.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Schritt 1: Standardschriftarten festlegen
Definieren Sie den Pfad zu Ihrem Dokumentverzeichnis und erstellen Sie Ladeoptionen, um normale und asiatische Standardschriftarten festzulegen:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Schritt 2: Laden Sie die Präsentation
Laden Sie die PowerPoint-Präsentation mit den definierten Ladeoptionen:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Schritt 3: Ausgaben generieren
Generieren Sie verschiedene Ausgaben wie Folienminiaturen, PDF- und XPS-Dateien:
```java
try {
    // Miniaturansicht der Folie generieren
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // PDF erzeugen
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // XPS generieren
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Abschluss
Das Festlegen von Standardschriftarten in PowerPoint-Präsentationen mit Aspose.Slides für Java ist unkompliziert und effizient. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie einheitliche Schriftstile auf verschiedenen Plattformen und in verschiedenen Umgebungen sicherstellen und so die visuelle Attraktivität Ihrer Präsentationen steigern.
## Häufig gestellte Fragen
### Kann ich mit Aspose.Slides für Java benutzerdefinierte Schriftarten verwenden?
Ja, Sie können mit Aspose.Slides für Java benutzerdefinierte Schriftarten in Ihren Präsentationen angeben.
### Ist Aspose.Slides für Java mit allen Versionen von PowerPoint kompatibel?
Aspose.Slides für Java unterstützt eine breite Palette von PowerPoint-Versionen und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### Wie kann ich Support für Aspose.Slides für Java erhalten?
 Sie erhalten Support für Aspose.Slides für Java über die[Aspose-Foren](https://forum.aspose.com/c/slides/11).
### Kann ich Aspose.Slides für Java vor dem Kauf ausprobieren?
 Ja, Sie können Aspose.Slides für Java über eine kostenlose Testversion erkunden, die verfügbar ist unter[www.aspose.com](https://releases.aspose.com/).
### Wo kann ich eine temporäre Lizenz für Aspose.Slides für Java erhalten?
 Sie können eine temporäre Lizenz für Aspose.Slides für Java erhalten von der[Kaufseite](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
