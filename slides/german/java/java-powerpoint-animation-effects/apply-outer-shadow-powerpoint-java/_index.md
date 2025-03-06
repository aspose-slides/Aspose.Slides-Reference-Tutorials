---
title: Äußeren Schatten in PowerPoint mit Java anwenden
linktitle: Äußeren Schatten in PowerPoint mit Java anwenden
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Java und Aspose.Slides einen äußeren Schatteneffekt in PowerPoint anwenden. Verleihen Sie Ihren Präsentationen Tiefe und visuelle Attraktivität.
type: docs
weight: 13
url: /de/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---
## Einführung
Beim Erstellen optisch ansprechender PowerPoint-Präsentationen müssen Formen und Text häufig mit verschiedenen Effekten versehen werden. Ein solcher Effekt ist der Außenschatten, der Elemente hervorstechen lässt und Ihren Folien Tiefe verleiht. In diesem Tutorial erfahren Sie, wie Sie mithilfe von Java und Aspose.Slides einen Außenschatteneffekt auf eine Form in PowerPoint anwenden.
## Voraussetzungen

Stellen Sie vor dem Starten dieses Tutorials sicher, dass die folgenden Voraussetzungen erfüllt sind:

1. Java Development Kit (JDK): Stellen Sie sicher, dass Java auf Ihrem System installiert ist. Sie können die neueste Version des JDK von der Oracle-Website herunterladen und installieren.

2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von der[Download-Seite](https://releases.aspose.com/slides/java/).

3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie Ihre bevorzugte Java-IDE wie Eclipse, IntelliJ IDEA oder NetBeans zum Codieren und Ausführen von Java-Anwendungen.

4. Grundlegende Java-Kenntnisse: Kenntnisse der Grundlagen der Programmiersprache Java und objektorientierter Konzepte sind für das Verständnis der Codebeispiele hilfreich.

## Pakete importieren

Importieren Sie zunächst die erforderlichen Pakete für die Arbeit mit Aspose.Slides und verwandten Funktionen in Ihrem Java-Projekt:

```java
import com.aspose.slides.*;
```

Lassen Sie uns nun den Beispielcode in mehrere Schritte aufteilen, um mit Java und Aspose.Slides den äußeren Schatteneffekt auf eine Form in PowerPoint anzuwenden:

## Schritt 1: Einrichten Ihrer Projektumgebung

Erstellen Sie ein neues Java-Projekt in Ihrer bevorzugten IDE und fügen Sie die Bibliothek Aspose.Slides für Java zum Build-Pfad Ihres Projekts hinzu.

## Schritt 2: Präsentationsobjekt initialisieren

 Erstellen Sie eine Instanz des`Presentation` Klasse, die eine PowerPoint-Präsentationsdatei darstellt.

```java
Presentation presentation = new Presentation();
```

## Schritt 3: Folie und Form hinzufügen

Suchen Sie nach einem Verweis auf die Folie, der Sie die Form hinzufügen möchten, und fügen Sie der Folie dann eine AutoForm (z. B. ein Rechteck) hinzu.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Schritt 4: Passen Sie die Form an

Stellen Sie den Fülltyp der Form auf „NoFill“ ein und fügen Sie der Form Text hinzu.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Schritt 5: Passen Sie den Text an

Greifen Sie auf die Texteigenschaften der Form zu und passen Sie die Schriftgröße an.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Schritt 6: Äußeren Schatteneffekt aktivieren

Aktivieren Sie den äußeren Schatteneffekt für den Textteil.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Schritt 7: Schattenparameter festlegen

Definieren Sie die Parameter für den äußeren Schatteneffekt, etwa Unschärferadius, Richtung, Entfernung und Schattenfarbe.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Schritt 8: Speichern Sie die Präsentation

Speichern Sie die geänderte Präsentation mit dem auf die Form angewendeten äußeren Schatteneffekt.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Abschluss

Herzlichen Glückwunsch! Sie haben mit Java und Aspose.Slides erfolgreich einen äußeren Schatteneffekt auf eine Form in PowerPoint angewendet. Experimentieren Sie mit verschiedenen Parametern, um die gewünschten visuellen Effekte in Ihren Präsentationen zu erzielen.

## Häufig gestellte Fragen

### Kann ich den äußeren Schatteneffekt auch auf andere Formen als Rechtecke anwenden?
Ja, Sie können den äußeren Schatteneffekt auf verschiedene von Aspose.Slides unterstützte Formen anwenden, beispielsweise Kreise, Dreiecke und benutzerdefinierte Formen.

### Ist es möglich, die Schattenfarbe und -intensität anzupassen?
Auf jeden Fall! Sie haben die volle Kontrolle über die Schattenparameter, einschließlich Farbe, Unschärferadius, Richtung und Entfernung.

### Kann ich mehrere Effekte auf dieselbe Form anwenden?
Ja, Sie können mehrere Effekte wie Außenschatten, Innenschatten, Glanz und Reflexion kombinieren, um die optische Attraktivität von Formen und Text in Ihren Präsentationen zu steigern.

### Unterstützt Aspose.Slides das Anwenden von Effekten auf Textelemente?
Ja, Sie können Effekte nicht nur auf Formen, sondern auch auf einzelne Textabschnitte innerhalb der Formen anwenden, was Ihnen umfassende Flexibilität bei der Gestaltung Ihrer Folien gibt.

### Wo finde ich weitere Ressourcen und Support für Aspose.Slides?
 Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/java/) für detaillierte API-Referenzen und erkunden Sie die[Aspose.Slides-Forum](https://forum.aspose.com/c/slides/11) für Community-Unterstützung und Diskussionen.