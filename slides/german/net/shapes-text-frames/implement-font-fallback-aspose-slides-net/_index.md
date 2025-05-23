---
"date": "2025-04-16"
"description": "Erfahren Sie, wie Sie in Aspose.Slides für .NET Fallback-Regeln für Schriftarten implementieren, um sicherzustellen, dass Ihre Präsentationen Text in verschiedenen Sprachen und Skripts korrekt anzeigen."
"title": "So legen Sie Font-Fallback-Regeln in Aspose.Slides für .NET fest – Ein umfassender Leitfaden"
"url": "/de/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie Font-Fallback-Regeln in Aspose.Slides für .NET fest: Eine umfassende Anleitung

## Einführung

Beim Erstellen von Präsentationen mit Aspose.Slides für .NET müssen manchmal Zeichen verarbeitet werden, die bestimmte Schriftarten nicht unterstützen, wie z. B. Tamil oder japanische Hiragana. Das Festlegen von Schriftart-Fallback-Regeln ist wichtig, um sicherzustellen, dass Ihre Präsentation Text in verschiedenen Sprachen und Symbolen korrekt anzeigt.

In diesem Tutorial führen wir Sie durch die Implementierung von Font-Fallback-Regeln mit Aspose.Slides für .NET. Von der Installation bis zur praktischen Anwendung stellt dieser Leitfaden sicher, dass Ihre Präsentationen unabhängig vom Inhalt visuell konsistent bleiben.

**Was Sie lernen werden:**
- Definieren Sie Unicode-Bereiche für verschiedene Skripts.
- Richten Sie Ersatzschriftarten für nicht unterstützte Zeichen ein.
- Wenden Sie in realen Präsentationsszenarien einen Font-Fallback an.
- Tipps zur Optimierung der Leistung und Integration mit anderen Systemen.

Beginnen wir mit der Überprüfung der Voraussetzungen.

## Voraussetzungen

Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:

- **Aspose.Slides für .NET** Bibliothek installiert. Installieren Sie mit einer der folgenden Methoden:
  - **.NET-CLI**: Laufen `dotnet add package Aspose.Slides`
  - **Paketmanager**: Ausführen `Install-Package Aspose.Slides`
  - **NuGet-Paket-Manager-Benutzeroberfläche**: Suchen und installieren Sie die neueste Version.
- Eine mit .NET Core oder .NET Framework (Version 4.5 oder höher) eingerichtete Entwicklungsumgebung.
- Grundlegende Kenntnisse der C#-Programmierung.

## Einrichten von Aspose.Slides für .NET

Um Aspose.Slides zu verwenden, erwerben Sie eine Lizenz von der [Aspose-Website](https://purchase.aspose.com/buy)So richten Sie es ein:

1. **Installation**: Befolgen Sie die oben genannten Installationsschritte.
2. **Lizenz-Setup**:
   - Laden Sie Ihre Lizenzdatei in Ihr Projekt mit:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Mit diesem Setup können Sie mit Aspose.Slides für .NET arbeiten.

## Implementierungshandbuch

In diesem Abschnitt beschreiben wir den Vorgang zum Festlegen von Schriftart-Fallback-Regeln in klaren Schritten.

### 1. Unicode-Bereiche und Ersatzschriftarten definieren

Jedes Skript oder jeder Symbolsatz erfordert bestimmte Unicode-Bereiche und entsprechende Ersatzschriftarten, um eine ordnungsgemäße Anzeige zu gewährleisten.

#### Tamilische Schrift

- **Überblick**: Verwenden Sie „Vijaya“ für tamilische Zeichen, wenn die primäre Schriftart diese nicht unterstützt.

**Implementierungsschritte:**

##### Schritt 1: Unicode-Bereich definieren
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Beginn des tamilischen Verbreitungsgebiets
uint endUnicodeIndexTamil = 0x0BFF;   // Ende des tamilischen Verbreitungsgebiets
```
Dieser Codeausschnitt definiert den Unicode-Bereich für tamilische Zeichen.

##### Schritt 2: Fallback-Regel erstellen
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Hier erstellen wir eine Fallback-Regel mit „Vijaya“ als alternative Schriftart.

#### Japanische Hiragana

- **Überblick**: Verwenden Sie „MS Mincho“ oder „MS Gothic“ für nicht unterstützte Hiragana-Zeichen.

**Implementierungsschritte:**

##### Schritt 1: Unicode-Bereich definieren
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Beginn der Hiragana-Reihe
uint endUnicodeIndexHiragana = 0x309F;   // Ende des Hiragana-Bereichs
```
Dieser Codeausschnitt legt die Unicode-Grenzen für Hiragana fest.

##### Schritt 2: Fallback-Regel erstellen
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Diese Regel gibt mehrere Ersatzschriftarten für Hiragana-Zeichen an.

#### Emoji-Zeichen

- **Überblick**: Stellen Sie sicher, dass Emojis in geeigneten Schriftarten wie „Segoe UI Emoji“ angezeigt werden.

**Implementierungsschritte:**

##### Schritt 1: Unicode-Bereich definieren
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Beginn des Emoji-Bereichs
uint endUnicodeIndexEmoji = 0x1F64F;   // Ende des Emoji-Bereichs
```
Dies definiert den Unicode-Bereich für Emojis.

##### Schritt 2: Fallback-Regel erstellen
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}