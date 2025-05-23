---
"description": "Erfahren Sie, wie Sie die Stammverzeichnis-ClsId in Aspose.Slides für Java-Präsentationen festlegen. Passen Sie das Hyperlink-Verhalten mit CLSID an."
"linktitle": "Stammverzeichnis ClsId in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Stammverzeichnis ClsId in Java-Folien"
"url": "/de/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Stammverzeichnis ClsId in Java-Folien


## Einführung in das Festlegen der ClsId des Stammverzeichnisses in Aspose.Slides für Java

In Aspose.Slides für Java können Sie die ClsId des Stammverzeichnisses festlegen. Diese CLSID (Class Identifier) gibt an, welche Anwendung als Stammverzeichnis verwendet werden soll, wenn ein Hyperlink in Ihrer Präsentation aktiviert wird. In dieser Anleitung erklären wir Ihnen Schritt für Schritt, wie Sie dies tun.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Auf Ihrem System ist das Java Development Kit (JDK) installiert.
- Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen von [Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
- Ein Code-Editor oder eine integrierte Entwicklungsumgebung (IDE), die für die Java-Entwicklung eingerichtet wurde.

## Schritt 1: Erstellen Sie eine neue Präsentation

Erstellen wir zunächst eine neue Präsentation mit Aspose.Slides für Java. In diesem Beispiel erstellen wir eine leere Präsentation.

```java
// Name der Ausgabedatei
String resultPath = "your_output_path/pres.ppt"; // Ersetzen Sie „Ihr_Ausgabepfad“ durch das gewünschte Ausgabeverzeichnis.
Presentation pres = new Presentation();
```

Im obigen Code definieren wir den Pfad für die Ausgabe-Präsentationsdatei und erstellen eine neue `Presentation` Objekt.

## Schritt 2: Stammverzeichnis-ClsId festlegen

Um die ClsId des Stammverzeichnisses festzulegen, müssen Sie eine Instanz von `PptOptions` und legen Sie die gewünschte CLSID fest. Die CLSID stellt die Anwendung dar, die bei Aktivierung eines Hyperlinks als Stammverzeichnis verwendet wird.

```java
PptOptions pptOptions = new PptOptions();
// Setzen Sie die CLSID auf „Microsoft Powerpoint.Show.8“.
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

Im obigen Code erstellen wir eine `PptOptions` Objekt und setzen Sie die CLSID auf „Microsoft Powerpoint.Show.8“. Sie können sie durch die CLSID der Anwendung ersetzen, die Sie als Stammverzeichnis verwenden möchten.

## Schritt 3: Speichern Sie die Präsentation

Speichern wir nun die Präsentation mit der festgelegten ClsId des Stammverzeichnisses.

```java
// Präsentation speichern
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

In diesem Schritt speichern wir die Präsentation auf dem angegebenen `resultPath` mit dem `PptOptions` wir zuvor erstellt haben.

## Schritt 4: Aufräumen

Vergessen Sie nicht, die `Presentation` Objekt, um alle zugewiesenen Ressourcen freizugeben.

```java
if (pres != null) {
    pres.dispose();
}
```

## Vollständiger Quellcode für das Stammverzeichnis ClsId in Java-Folien

```java
// Name der Ausgabedatei
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// Setzen Sie CLSID auf „Microsoft Powerpoint.Show.8“.
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Präsentation speichern
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Abschluss

Sie haben die Stammverzeichnis-ClsId in Aspose.Slides für Java erfolgreich festgelegt. Dadurch können Sie die Anwendung festlegen, die als Stammverzeichnis verwendet wird, wenn Hyperlinks in Ihrer Präsentation aktiviert werden. Sie können die CLSID Ihren spezifischen Anforderungen entsprechend anpassen.

## Häufig gestellte Fragen

### Wie finde ich die CLSID für eine bestimmte Anwendung?

Die CLSID einer bestimmten Anwendung finden Sie in der Dokumentation oder den Ressourcen des Anwendungsentwicklers. CLSIDs sind eindeutige Bezeichner, die COM-Objekten zugewiesen werden und in der Regel anwendungsspezifisch sind.

### Kann ich eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen?

Ja, Sie können eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen, indem Sie den gewünschten CLSID-Wert mit dem `setRootDirectoryClsid` -Methode, wie im Codebeispiel gezeigt. Dadurch können Sie eine bestimmte Anwendung als Stammverzeichnis verwenden, wenn Hyperlinks in Ihrer Präsentation aktiviert werden.

### Was passiert, wenn ich die ClsId des Stammverzeichnisses nicht festlege?

Wenn Sie die ClsId des Stammverzeichnisses nicht festlegen, hängt das Standardverhalten vom Viewer oder der Anwendung ab, mit der die Präsentation geöffnet wird. Bei aktivierten Hyperlinks kann die eigene Standardanwendung als Stammverzeichnis verwendet werden.

### Kann ich die ClsId des Stammverzeichnisses für einzelne Hyperlinks ändern?

Nein, die ClsId des Stammverzeichnisses wird normalerweise auf Präsentationsebene festgelegt und gilt für alle Hyperlinks innerhalb der Präsentation. Wenn Sie für einzelne Hyperlinks unterschiedliche Anwendungen angeben müssen, müssen Sie diese Hyperlinks möglicherweise separat in Ihrem Code behandeln.

### Gibt es Einschränkungen hinsichtlich der CLSIDs, die ich verwenden kann?

Die verwendbaren CLSIDs werden in der Regel durch die auf dem System installierten Anwendungen bestimmt. Verwenden Sie CLSIDs gültiger Anwendungen, die Hyperlinks verarbeiten können. Beachten Sie, dass die Verwendung einer ungültigen CLSID zu unerwartetem Verhalten führen kann.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}