---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie Ihre Präsentationen mit Aspose.Slides für .NET mit benutzerdefinierten Sternformen optimieren. Folgen Sie dieser Schritt-für-Schritt-Anleitung, um ansprechende Visualisierungen zu erstellen."
"title": "So erstellen und speichern Sie benutzerdefinierte Sternformen in .NET-Präsentationen mit Aspose.Slides"
"url": "/de/net/shapes-text-frames/create-star-shape-dotnet-presentation-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und speichern Sie benutzerdefinierte Sternformen in .NET-Präsentationen mit Aspose.Slides

Einzigartige Formen wie Sterne können Ihre Präsentationsfolien von gewöhnlich zu außergewöhnlich machen. Dieses Tutorial führt Sie durch das Erstellen und Speichern benutzerdefinierter sternförmiger Geometrien mit Aspose.Slides für .NET und macht Ihre Präsentationen ansprechender und optisch ansprechender.

## Was Sie lernen werden:
- Erstellen einer benutzerdefinierten Sternform mit bestimmten Radien in C#.
- Integrieren dieser Funktion in eine .NET-Anwendung.
- Speichern der Präsentation mit der neuen benutzerdefinierten Form mithilfe von Aspose.Slides.

Tauchen wir ein!

### Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:
- **Aspose.Slides für .NET**Version 23.x oder höher ist erforderlich. Diese Bibliothek ermöglicht das programmgesteuerte Erstellen und Bearbeiten von PowerPoint-Präsentationen.
- **Entwicklungsumgebung**: Visual Studio mit einem .NET-Projekt-Setup.
- **Grundlegende C#-Kenntnisse**: Wenn Sie mit den Konzepten der C#-Programmierung vertraut sind, verstehen Sie die Implementierung besser.

### Einrichten von Aspose.Slides für .NET

Fügen Sie Aspose.Slides mit einer der folgenden Methoden zu Ihrem Projekt hinzu:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Verwenden des Paketmanagers:**
```powershell
Install-Package Aspose.Slides
```

**Verwenden der NuGet-Paket-Manager-Benutzeroberfläche:**
1. Öffnen Sie das Dialogfeld „NuGet-Pakete verwalten“ in Visual Studio.
2. Suchen Sie nach „Aspose.Slides“.
3. Installieren Sie die neueste Version.

#### Erwerb einer Lizenz
Um Aspose.Slides vollständig nutzen zu können, sollten Sie den Erwerb einer Lizenz in Erwägung ziehen:
- **Kostenlose Testversion**: Beginnen Sie mit einer temporären Lizenz, um alle Funktionen ohne Einschränkungen zu nutzen.
- **Kaufen**Besuchen [Aspose Kauf](https://purchase.aspose.com/buy) für verschiedene, auf Ihre Bedürfnisse zugeschnittene Lizenzierungsoptionen.

### Implementierungshandbuch
Wir werden die Sternform erstellen und in einer Präsentation speichern, die in zwei Hauptfunktionen unterteilt ist.

#### Funktion 1: Benutzerdefinierten Geometriepfad erstellen
Bei dieser Funktion wird ein geometrischer Pfad generiert, der mithilfe festgelegter Außen- und Innenradien eine Sternform bildet.

**Überblick**: Wir berechnen Punkte für die Außen- und Innenkanten des Sterns und verbinden diese zu einer geschlossenen Sternform.

##### Implementierungsschritte:

**Schritt 1**: Definieren Sie die Sternpunktberechnung
```csharp
using System.Collections.Generic;
using Aspose.Slides.Export;
using System.Drawing;

public static class StarGeometryCreator
{
    public static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
    {
        GeometryPath starPath = new GeometryPath();
        List<PointF> points = new List<PointF>();
        int step = 72; // Schrittwinkel in Grad

        for (int angle = -90; angle < 270; angle += step)
        {
            double radians = angle * (Math.PI / 180f);
            double xOuter = outerRadius * Math.Cos(radians) + outerRadius;
            double yOuter = outerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xOuter, (float)yOuter));

            radians = Math.PI * (angle + step / 2) / 180.0;
            double xInner = innerRadius * Math.Cos(radians) + outerRadius;
            double yInner = innerRadius * Math.Sin(radians) + outerRadius;
            points.Add(new PointF((float)xInner, (float)yInner));
        }

        starPath.MoveTo(points[0]);
        for (int i = 1; i < points.Count; i++)
        {
            starPath.LineTo(points[i]);
        }
        starPath.CloseFigure();

        return starPath;
    }
}
```
**Erläuterung**: Die Methode `CreateStarGeometry` Berechnet die Koordinaten der äußeren und inneren Scheitelpunkte anhand der eingegebenen Radien. Die Platzierung der einzelnen Punkte erfolgt trigonometrisch, wodurch ein durchgehender Pfad entsteht, der einen Stern bildet.

#### Funktion 2: Erstellen und Speichern einer Präsentation mit benutzerdefinierter Form
Hier integrieren wir die benutzerdefinierte Geometrie in eine Präsentation und speichern diese als .pptx-Datei.

**Überblick**: Fügen Sie einer Folie mithilfe des im vorherigen Schritt erstellten benutzerdefinierten Geometriepfads eine Form hinzu.

##### Implementierungsschritte:

**Schritt 1**Initialisieren der Präsentation
```csharp
using Aspose.Slides;
using System.IO;

public static class PresentationCreator
{
    public static void CreateAndSavePresentation()
    {
        string resultPath = Path.Combine("YOUR_OUTPUT_DIRECTORY\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}