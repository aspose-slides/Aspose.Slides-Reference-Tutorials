---
"date": "2025-04-18"
"description": "Erfahren Sie, wie Sie Ihre Präsentationen verbessern, indem Sie SmartArt-Aufzählungszeichen mit Bildern mithilfe von Aspose.Slides für Java anpassen. Folgen Sie dieser Schritt-für-Schritt-Anleitung für einen professionellen Look."
"title": "So passen Sie SmartArt-Aufzählungszeichen mit Bildern mithilfe von Aspose.Slides für Java an | Schritt-für-Schritt-Anleitung"
"url": "/de/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So passen Sie SmartArt-Aufzählungszeichen mit Bildern mithilfe von Aspose.Slides für Java an

## Einführung

Visuell ansprechende Präsentationen sind entscheidend, um die Aufmerksamkeit Ihres Publikums zu fesseln und Ihre Botschaft effektiv zu vermitteln. Eine häufige Herausforderung bei der Foliengestaltung ist die Verbesserung von Aufzählungspunkten in SmartArt-Grafiken mithilfe benutzerdefinierter Bilder. Dieses Tutorial führt Sie durch die Einrichtung eines Bilds als Aufzählungsfüllformat in SmartArt-Knoten mit Aspose.Slides für Java und ermöglicht Ihnen so, Ihre Präsentationen professionell zu gestalten.

**Was Sie lernen werden:**
- Einrichten und Verwenden von Aspose.Slides für Java
- Anpassen von Aufzählungspunkten mit Bildern in SmartArt-Grafiken
- Praktische Anwendungen dieser Anpassung
- Beheben häufiger Probleme

Bevor wir mit der Implementierung beginnen, stellen Sie sicher, dass Sie alles bereit haben.

## Voraussetzungen

Um diesem Tutorial folgen zu können, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. **Bibliotheken und Abhängigkeiten**Sie benötigen Aspose.Slides für die Java-Bibliothek Version 25.4 oder höher.
2. **Umgebungs-Setup**:
   - Eine kompatible IDE wie IntelliJ IDEA oder Eclipse
   - JDK 16 auf Ihrem Computer installiert
3. **Voraussetzungen**: Vertrautheit mit Java-Programmierung und der grundlegenden Struktur von PowerPoint-Präsentationen.

## Einrichten von Aspose.Slides für Java

Binden Sie zunächst die Bibliothek Aspose.Slides mit einer der folgenden Methoden in Ihr Projekt ein:

### Maven

Fügen Sie diese Abhängigkeit zu Ihrem `pom.xml` Datei:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Nehmen Sie dies in Ihre `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkter Download

Alternativ können Sie die Bibliothek auch direkt von [Aspose.Slides für Java-Versionen](https://releases.aspose.com/slides/java/).

**Schritte zum Lizenzerwerb**Aspose bietet eine kostenlose Testlizenz an, die sich ideal zum Testen der Funktionen eignet. Sie können eine temporäre Lizenz anfordern oder eine erwerben, um die Testbeschränkungen aufzuheben.

Um Ihre Umgebung zu initialisieren und einzurichten, erstellen Sie eine Instanz des `Presentation` Klasse wie gezeigt:

```java
Presentation presentation = new Presentation();
```

## Implementierungshandbuch

In diesem Abschnitt wird der Prozess in überschaubare Schritte unterteilt und erläutert, wie die gewünschte Funktionalität erreicht wird.

### Hinzufügen von SmartArt mit benutzerdefinierter Aufzählungszeichenfüllung

#### Überblick

Wir beginnen damit, Ihrer Folie eine SmartArt-Form hinzuzufügen und ihre Aufzählungspunkte mithilfe einer Bildfüllung anzupassen.

#### Schritt-für-Schritt-Anleitung

**1. Präsentationsobjekt initialisieren**

```java
Presentation presentation = new Presentation();
```

*Zweck*: Initialisiert eine neue Präsentationsinstanz, in der Sie die SmartArt-Grafiken hinzufügen.

**2. SmartArt-Form hinzufügen**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Erläuterung*: Diese Zeile fügt der ersten Folie an Position (x=10, y=10) eine neue SmartArt-Form mit den Abmessungen 500x400 Pixel hinzu. Die `VerticalPictureList` Layout wird für die vertikale Ausrichtung verwendet.

**3. Aufzählungszeichenfüllung aufrufen und anpassen**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Zweck*: Überprüft, ob der Knoten über eine `BulletFillFormat` Eigenschaft. Wenn ja, wird ein Bild geladen und als Füllung für Aufzählungszeichen festgelegt.
*Parameter*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Der Pfad zu Ihrer Bilddatei.
  - `PictureFillMode.Stretch`: Stellt sicher, dass das Bild den Aufzählungsbereich vollständig ausfüllt.

**4. Speichern Sie Ihre Präsentation**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}