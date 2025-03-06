---
title: Hinzufügen benutzerdefinierter untergeordneter Knoten in SmartArt mit Java
linktitle: Hinzufügen benutzerdefinierter untergeordneter Knoten in SmartArt mit Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Java und Aspose.Slides benutzerdefinierte untergeordnete Knoten zu SmartArt in PowerPoint-Präsentationen hinzufügen. Verbessern Sie Ihre Folien mühelos mit professionellen Grafiken.
weight: 11
url: /de/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
SmartArt ist eine leistungsstarke Funktion in PowerPoint, mit der Benutzer schnell und einfach professionell aussehende Grafiken erstellen können. In diesem Tutorial erfahren Sie, wie Sie mit Java und Aspose.Slides benutzerdefinierte untergeordnete Knoten zu SmartArt hinzufügen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:
1. Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist.
2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von[Hier](https://releases.aspose.com/slides/java/).

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete in Ihr Java-Projekt:
```java
import com.aspose.slides.*;
```
## Schritt 1: Laden Sie die Präsentation
Laden Sie die PowerPoint-Präsentation, in der Sie der SmartArt benutzerdefinierte untergeordnete Knoten hinzufügen möchten:
```java
String dataDir = "Your Document Directory";
// Laden Sie die gewünschte Präsentation
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Schritt 2: SmartArt zur Folie hinzufügen
Fügen wir nun der Folie SmartArt hinzu:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Schritt 3: SmartArt-Form verschieben
Verschieben Sie die SmartArt-Form an eine neue Position:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Schritt 4: Formbreite ändern
Ändern Sie die Breite der SmartArt-Form:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Schritt 5: Formhöhe ändern
Ändern Sie die Höhe der SmartArt-Form:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Schritt 6: Drehen Sie die Form
Drehen Sie die SmartArt-Form:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Schritt 7: Speichern Sie die Präsentation
Abschließend speichern Sie die geänderte Präsentation:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Java und Aspose.Slides benutzerdefinierte untergeordnete Knoten zu SmartArt hinzufügt. Indem Sie diese Schritte befolgen, können Sie Ihre Präsentationen mit benutzerdefinierten Grafiken verbessern und sie ansprechender und professioneller gestalten.
## Häufig gestellte Fragen
### Kann ich mit Aspose.Slides für Java verschiedene Arten von SmartArt-Layouts hinzufügen?
Ja, Aspose.Slides für Java unterstützt verschiedene SmartArt-Layouts, sodass Sie dasjenige auswählen können, das Ihren Präsentationsanforderungen am besten entspricht.
### Ist Aspose.Slides für Java mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides für Java ist für die nahtlose Zusammenarbeit mit verschiedenen PowerPoint-Versionen konzipiert und gewährleistet plattformübergreifende Kompatibilität und Konsistenz.
### Kann ich das Erscheinungsbild von SmartArt-Formen programmgesteuert anpassen?
Auf jeden Fall! Mit Aspose.Slides für Java können Sie das Aussehen, die Größe, die Farbe und das Layout von SmartArt-Formen programmgesteuert an Ihre Designvorlieben anpassen.
### Bietet Aspose.Slides für Java Dokumentation und Support?
Ja, Sie finden umfassende Dokumentationen und Zugriff auf Community-Supportforen auf der Aspose-Website.
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion von Aspose.Slides für Java von der Website herunterladen, um die Funktionen und Möglichkeiten zu erkunden, bevor Sie einen Kauf tätigen.[Hier](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
