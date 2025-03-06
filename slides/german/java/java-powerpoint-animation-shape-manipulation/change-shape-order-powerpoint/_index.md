---
title: Ändern der Formreihenfolge in PowerPoint
linktitle: Ändern der Formreihenfolge in PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie in diesem Schritt-für-Schritt-Tutorial, wie Sie die Formreihenfolge in PowerPoint mit Aspose.Slides für Java ändern. Verbessern Sie mühelos Ihre Präsentationsfähigkeiten.
weight: 15
url: /de/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
Das Erstellen optisch ansprechender und gut strukturierter Präsentationen kann eine gewaltige Aufgabe sein. Mit den richtigen Tools und Techniken können Sie es sich jedoch deutlich erleichtern. Aspose.Slides für Java ist eine leistungsstarke Bibliothek, mit der Sie PowerPoint-Präsentationen programmgesteuert bearbeiten und verwalten können. In diesem Tutorial führen wir Sie durch die Schritte zum Ändern der Formreihenfolge in einer PowerPoint-Folie mit Aspose.Slides für Java.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Rechner installiert ist. Sie können es von der[Oracle-Website](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides für Java-Bibliothek: Laden Sie die neueste Version herunter von[Aspose.Slides für Java-Downloadseite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie zum Codieren eine IDE wie IntelliJ IDEA oder Eclipse.
4. Präsentationsdatei: Halten Sie eine PowerPoint-Datei bereit, die Sie bearbeiten möchten.
## Pakete importieren
Um zu beginnen, müssen Sie die erforderlichen Pakete aus der Aspose.Slides-Bibliothek importieren. Diese Importe ermöglichen Ihnen die Arbeit mit Präsentationen, Folien und Formen.
```java
import com.aspose.slides.*;

```
In dieser Anleitung unterteilen wir den Vorgang zum Ändern der Formreihenfolge zum besseren Verständnis und zur einfacheren Umsetzung in mehrere Schritte.
## Schritt 1: Laden Sie die Präsentation
 Zuerst müssen Sie die PowerPoint-Präsentationsdatei laden, mit der Sie arbeiten möchten. Dieser Schritt beinhaltet die Initialisierung der`Presentation` Klasse durch den Pfad zu Ihrer PowerPoint-Datei.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## Schritt 2: Auf die gewünschte Folie zugreifen
Sobald die Präsentation geladen ist, rufen Sie die Folie auf, auf der Sie die Formen neu anordnen möchten. Die Folien werden beginnend bei 0 indiziert. Um auf die erste Folie zuzugreifen, verwenden Sie also den Index 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## Schritt 3: Formen zur Folie hinzufügen
Als Nächstes fügen Sie der Folie die Formen hinzu. Zur Demonstration fügen wir der Folie ein Rechteck und ein Dreieck hinzu.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Schritt 4: Ordnen Sie die Formen neu an
 Ordnen Sie nun die Formen auf der Folie neu an.`reorder` Mit der Methode können Sie die neue Position der Form innerhalb der Formensammlung der Folie angeben.
```java
slide.getShapes().reorder(2, shp3);
```
## Schritt 5: Speichern der geänderten Präsentation
Nachdem Sie die Formen neu angeordnet haben, speichern Sie die geänderte Präsentation in einer neuen Datei. Dadurch wird sichergestellt, dass Ihre Originaldatei unverändert bleibt.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## Schritt 6: Ressourcen bereinigen
Entsorgen Sie abschließend das Präsentationsobjekt, um Ressourcen freizugeben.
```java
if (presentation1 != null) presentation1.dispose();
```
## Abschluss
Wenn Sie diese Schritte befolgen, können Sie die Reihenfolge der Formen in einer PowerPoint-Folie mithilfe von Aspose.Slides für Java ganz einfach ändern. Diese leistungsstarke Bibliothek vereinfacht viele Aufgaben im Zusammenhang mit PowerPoint-Präsentationen und ermöglicht Ihnen das programmgesteuerte Erstellen und Bearbeiten von Folien. Egal, ob Sie die Erstellung von Präsentationen automatisieren oder nur Massenänderungen vornehmen müssen, Aspose.Slides für Java ist ein unschätzbar wertvolles Tool.
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine Java-API zum Erstellen und Bearbeiten von PowerPoint-Präsentationen ohne Verwendung von Microsoft PowerPoint.
### Kann ich Aspose.Slides für Java mit anderen Java-IDEs verwenden?
Ja, Sie können es mit jeder Java-IDE wie IntelliJ IDEA, Eclipse oder NetBeans verwenden.
### Ist Aspose.Slides für Java mit allen PowerPoint-Formaten kompatibel?
Ja, Aspose.Slides für Java unterstützt PPT, PPTX und andere PowerPoint-Formate.
### Wie erhalte ich eine kostenlose Testversion von Aspose.Slides für Java?
 Sie können eine kostenlose Testversion herunterladen von der[Aspose.Slides für Java-Downloadseite](https://releases.aspose.com/).
### Wo finde ich weitere Dokumentation zu Aspose.Slides für Java?
 Eine ausführliche Dokumentation finden Sie auf der[Aspose.Slides für Java-Dokumentationsseite](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
