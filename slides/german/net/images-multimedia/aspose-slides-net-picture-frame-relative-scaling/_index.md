---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Bildrahmen mit relativer Skalierung hinzufügen. Diese Anleitung behandelt Einrichtung, Bildbearbeitung und Skalierungstechniken."
"title": "So fügen Sie Bilderrahmen mit relativer Skalierung in Aspose.Slides .NET hinzu – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/images-multimedia/aspose-slides-net-picture-frame-relative-scaling/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So fügen Sie Bilderrahmen mit relativer Skalierung in Aspose.Slides .NET hinzu: Eine Schritt-für-Schritt-Anleitung

## Einführung

Visuell ansprechende PowerPoint-Präsentationen sind entscheidend für eine effektive Kommunikation, egal ob Sie einen Business-Pitch oder einen Lehrvortrag halten. Das Anpassen von Bildern an das Design Ihrer Folien kann mühsam und zeitaufwändig sein. Mit Aspose.Slides für .NET können Sie ganz einfach Bilderrahmen mit relativer Skalierung hinzufügen. So stellen Sie sicher, dass Ihre Bilder ihr Seitenverhältnis beibehalten und perfekt auf Ihre Folien passen.

In diesem Tutorial erfahren Sie, wie Sie Aspose.Slides für .NET nutzen, um ein Bild als Bilderrahmen hinzuzufügen und seine Abmessungen proportional anzupassen. Sie lernen die Grundlagen der Einrichtung von Aspose.Slides in Ihrer Entwicklungsumgebung und die Implementierung relativer Skalierungsfunktionen in Ihren Präsentationen. Am Ende erhalten Sie eine Präsentation, die nicht nur professionell aussieht, sondern sich auch dynamisch an verschiedene Anzeigeeinstellungen anpasst.

**Was Sie lernen werden:**
- Einrichten von Aspose.Slides für .NET
- Hinzufügen eines Bildes als Bilderrahmen zu einer PowerPoint-Folie
- Implementierung der relativen Skalierung für Bilderrahmen
- Bewährte Methoden und Tipps zur Fehlerbehebung

Lassen Sie uns in die Voraussetzungen eintauchen, bevor wir unsere Reise mit Aspose.Slides beginnen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes eingerichtet haben:

### Erforderliche Bibliotheken und Abhängigkeiten

Um diese Funktion zu implementieren, müssen Sie Aspose.Slides für .NET installiert haben. Diese Bibliothek ermöglicht die umfassende Bearbeitung von PowerPoint-Präsentationen mit C#.

### Anforderungen für die Umgebungseinrichtung

Stellen Sie sicher, dass Ihre Entwicklungsumgebung wie folgt eingerichtet ist:
- Eine kompatible Version von .NET (vorzugsweise .NET Core oder .NET Framework 4.5 und höher)
- Ein Code-Editor wie Visual Studio, Visual Studio Code oder eine beliebige IDE, die die .NET-Entwicklung unterstützt
- Zugriff auf ein Dateiverzeichnis, in dem Sie Ihre PowerPoint-Dateien speichern können

### Voraussetzungen

Kenntnisse in der C#-Programmierung sind von Vorteil, aber nicht zwingend erforderlich. Grundkenntnisse im Umgang mit Bildern und im Verständnis der Prinzipien der objektorientierten Programmierung sind ebenfalls hilfreich.

## Einrichten von Aspose.Slides für .NET

Um Aspose.Slides für .NET zu verwenden, befolgen Sie die folgenden Installationsschritte:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paketmanager**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
Öffnen Sie Ihr Projekt in Visual Studio, navigieren Sie zum NuGet-Paket-Manager und suchen Sie nach „Aspose.Slides“, um die neueste Version zu installieren.

### Schritte zum Lizenzerwerb

- **Kostenlose Testversion**: Sie können mit einer kostenlosen Testversion beginnen, mit der Sie die Funktionen von Aspose.Slides testen können.
- **Temporäre Lizenz**: Erhalten Sie eine temporäre Lizenz zur erweiterten Evaluierung ohne Einschränkungen.
- **Kaufen**: Für vollständigen Zugriff und Support sollten Sie den Kauf einer Lizenz von Aspose in Erwägung ziehen.

#### Grundlegende Initialisierung und Einrichtung

Initialisieren Sie Aspose.Slides nach der Installation in Ihrem Projekt, indem Sie die erforderlichen Using-Direktiven hinzufügen:

```csharp
using Aspose.Slides;
```

## Implementierungshandbuch

### Hinzufügen eines Bilderrahmens mit relativer Skalierung

In diesem Abschnitt erfahren Sie, wie Sie ein Bild als Bilderrahmen hinzufügen und seine relative Skalierung festlegen.

#### Laden Ihres Bildes

Laden Sie zunächst Ihr gewünschtes Bild in die Bildersammlung der Präsentation:

```csharp
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";
IImage img = Images.FromFile(dataDir + "aspose-logo.jpg");
IPPImage image = presentation.Images.AddImage(img);
```

Dieser Codeausschnitt lädt ein Bild aus einem angegebenen Verzeichnis und fügt es der Präsentation hinzu.

#### Hinzufügen des Bilderrahmens

Fügen Sie als Nächstes einen Bilderrahmen vom Typ „Rechteck“ auf Ihrer Folie hinzu:

```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```

Hier, `ShapeType.Rectangle` gibt die Form an und die Parameter legen ihre Position und Anfangsgröße fest.

#### Festlegen des relativen Maßstabs

Passen Sie die Abmessungen proportional an, indem Sie die relative Maßstabshöhe und -breite festlegen:

```csharp
pf.RelativeScaleHeight = 0.8f; // Skaliert auf 80 % der Originalhöhe
pf.RelativeScaleWidth = 1.35f; // Skaliert auf 135 % der Originalbreite
```

Dadurch wird sichergestellt, dass Ihr Bild richtig skaliert wird und ein konsistentes Seitenverhältnis beibehalten wird.

#### Speichern Ihrer Präsentation

Abschließend speichern Sie die Präsentation mit dem geänderten Bilderrahmen:

```csharp\presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}