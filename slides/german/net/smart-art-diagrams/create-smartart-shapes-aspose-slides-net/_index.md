---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET dynamische SmartArt-Grafiken in PowerPoint erstellen. Optimieren Sie Ihre Präsentationen mit diesem umfassenden Leitfaden."
"title": "Erstellen Sie SmartArt-Formen in PowerPoint mit Aspose.Slides für .NET – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/net/smart-art-diagrams/create-smartart-shapes-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie SmartArt-Formen in PowerPoint mit Aspose.Slides für .NET: Eine Schritt-für-Schritt-Anleitung

## Einführung

Optimieren Sie Ihre PowerPoint-Präsentationen durch die Integration dynamischer SmartArt-Grafiken mit C#. Mit Aspose.Slides für .NET können Sie SmartArt-Formen nahtlos in Ihren Folien erstellen und verwalten. Diese Anleitung führt Sie durch die Einrichtung und Implementierung von SmartArt mit Aspose.Slides für .NET.

**Was Sie lernen werden:**
- Einrichten Ihrer Umgebung mit Aspose.Slides für .NET
- Erstellen einer SmartArt-Form innerhalb einer PowerPoint-Folie
- Effektive Verwaltung von Verzeichnissen in Ihrem Code

## Voraussetzungen (H2)

Um diese Lösung erfolgreich zu implementieren, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Erforderliche Bibliotheken**: Aspose.Slides für .NET (Version 21.11 oder höher empfohlen)
- **Entwicklungsumgebung**: .NET Core oder .NET Framework
- **Grundkenntnisse**: Vertrautheit mit C# und Dateisystemoperationen

## Einrichten von Aspose.Slides für .NET (H2)

### Installation

Beginnen Sie mit der Installation von Aspose.Slides mit einer der folgenden Methoden:

**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```

**Paket-Manager-Konsole in Visual Studio**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
1. Öffnen Sie den NuGet-Paket-Manager.
2. Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb
- **Kostenlose Testversion**: Laden Sie eine temporäre Lizenz herunter von [Hier](https://purchase.aspose.com/temporary-license/) um die vollständigen Funktionen von Aspose.Slides zu bewerten.
- **Kaufen**: Für die dauerhafte Nutzung erwerben Sie eine Lizenz über [dieser Link](https://purchase.aspose.com/buy).

Sobald Sie Ihre Lizenzdatei haben, initialisieren Sie sie in Ihrer Anwendung wie folgt:
```csharp
License license = new License();
license.SetLicense("Aspose.Slides.lic");
```

## Implementierungsleitfaden (H2)

### Funktion: SmartArt-Form erstellen (H2)

Mit dieser Funktion können Sie Ihren PowerPoint-Folien programmgesteuert optisch ansprechende SmartArt-Grafiken hinzufügen.

#### Überblick über den Prozess (H3)
Wir beginnen mit dem Einrichten eines Verzeichnisses, erstellen ein Präsentationsobjekt und fügen dann eine SmartArt-Form hinzu.

#### Code-Walkthrough (H3)
1. **Verzeichnisverwaltung**
   Stellen Sie sicher, dass Ihr Dokumentverzeichnis vorhanden ist, oder erstellen Sie es bei Bedarf:
   ```csharp
   string dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Definieren Sie den Zieldokumentverzeichnispfad
   bool isExists = Directory.Exists(dataDir); // Überprüfen Sie, ob das Verzeichnis existiert
   if (!isExists) 
       Directory.CreateDirectory(dataDir); // Erstellen Sie das Verzeichnis, falls es nicht existiert
   ```

2. **Erstellen einer neuen Präsentation**
   Initialisieren Sie eine neue Präsentation und greifen Sie auf ihre erste Folie zu:
   ```csharp
   using (Presentation pres = new Presentation())
   {
       ISlide slide = pres.Slides[0]; // Greifen Sie auf die erste Folie zu
   ```
   
3. **Hinzufügen von SmartArt zur Folie**
   Fügen Sie an den angegebenen Koordinaten eine SmartArt-Form mit den gewünschten Abmessungen und dem gewünschten Layouttyp hinzu:
   ```csharp
   // Hinzufügen einer SmartArt-Form mit dem BasicBlockList-Layout
   ISmartArt smart = slide.Shapes.AddSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);
   ```

4. **Speichern der Präsentation**
   Speichern Sie Ihre Präsentation abschließend im gewünschten Verzeichnis:
   ```csharp
   pres.Save(dataDir + "SimpleSmartArt_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}