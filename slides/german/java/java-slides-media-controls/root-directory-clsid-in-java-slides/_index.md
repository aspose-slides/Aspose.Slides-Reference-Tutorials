---
title: Stammverzeichnis ClsId in Java-Folien
linktitle: Stammverzeichnis ClsId in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie die ClsId des Stammverzeichnisses in Aspose.Slides für Java-Präsentationen festlegen. Passen Sie das Hyperlink-Verhalten mit CLSID an.
type: docs
weight: 10
url: /de/java/media-controls/root-directory-clsid-in-java-slides/
---

## Einführung in das Festlegen der ClsId des Stammverzeichnisses in Aspose.Slides für Java

In Aspose.Slides für Java können Sie die ClsId des Stammverzeichnisses festlegen. Dabei handelt es sich um die CLSID (Class Identifier), mit der die Anwendung angegeben wird, die als Stammverzeichnis verwendet werden soll, wenn ein Hyperlink in Ihrer Präsentation aktiviert wird. In dieser Anleitung führen wir Sie Schritt für Schritt durch die Vorgehensweise.

## Voraussetzungen

Stellen Sie zunächst sicher, dass die folgenden Voraussetzungen erfüllt sind:

- Auf Ihrem System ist Java Development Kit (JDK) installiert.
-  Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen von[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
- Ein für die Java-Entwicklung eingerichteter Code-Editor oder eine integrierte Entwicklungsumgebung (IDE).

## Schritt 1: Erstellen Sie eine neue Präsentation

Lassen Sie uns zunächst eine neue Präsentation mit Aspose.Slides für Java erstellen. In diesem Beispiel erstellen wir eine leere Präsentation.

```java
// Name der Ausgabedatei
String resultPath = "your_output_path/pres.ppt"; // Ersetzen Sie „Ihr_Ausgabepfad“ durch das gewünschte Ausgabeverzeichnis.
Presentation pres = new Presentation();
```

Im obigen Code definieren wir den Pfad für die Ausgabe-Präsentationsdatei und erstellen eine neue`Presentation` Objekt.

## Schritt 2: ClsId des Stammverzeichnisses festlegen

 Um die ClsId des Stammverzeichnisses festzulegen, müssen Sie eine Instanz von`PptOptions` und legen Sie die gewünschte CLSID fest. Die CLSID stellt die Anwendung dar, die als Stammverzeichnis verwendet wird, wenn ein Hyperlink aktiviert wird.

```java
PptOptions pptOptions = new PptOptions();
// Setzen Sie CLSID auf „Microsoft Powerpoint.Show.8“.
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 Im obigen Code erstellen wir eine`PptOptions` Objekt und setzen Sie die CLSID auf „Microsoft Powerpoint.Show.8“. Sie können es durch die CLSID der Anwendung ersetzen, die Sie als Stammverzeichnis verwenden möchten.

## Schritt 3: Speichern Sie die Präsentation

Speichern wir nun die Präsentation mit der festgelegten ClsId des Stammverzeichnisses.

```java
// Präsentation speichern
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 In diesem Schritt speichern wir die Präsentation im angegebenen`resultPath` mit dem`PptOptions` wir haben früher erstellt.

## Schritt 4: Bereinigen

 Vergessen Sie nicht, den`Presentation` Objekt, um alle zugewiesenen Ressourcen freizugeben.

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
	//Setzen Sie CLSID auf „Microsoft Powerpoint.Show.8“.
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Präsentation speichern
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Abschluss

Sie haben die ClsId des Stammverzeichnisses in Aspose.Slides für Java erfolgreich festgelegt. Dadurch können Sie die Anwendung angeben, die als Stammverzeichnis verwendet wird, wenn Hyperlinks in Ihrer Präsentation aktiviert werden. Sie können die CLSID entsprechend Ihren spezifischen Anforderungen anpassen.

## Häufig gestellte Fragen

### Wie finde ich die CLSID für eine bestimmte Anwendung?

Um die CLSID für eine bestimmte Anwendung zu finden, können Sie die Dokumentation oder die Ressourcen des Anwendungsentwicklers zu Rate ziehen. CLSIDs sind eindeutige Bezeichner, die COM-Objekten zugewiesen werden und normalerweise für jede Anwendung spezifisch sind.

### Kann ich eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen?

 Ja, Sie können eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen, indem Sie den gewünschten CLSID-Wert mit dem`setRootDirectoryClsid` -Methode, wie im Codebeispiel gezeigt. Dadurch können Sie eine bestimmte Anwendung als Stammverzeichnis verwenden, wenn in Ihrer Präsentation Hyperlinks aktiviert werden.

### Was passiert, wenn ich die ClsId des Stammverzeichnisses nicht festlege?

Wenn Sie die ClsId des Stammverzeichnisses nicht festlegen, hängt das Standardverhalten vom Viewer oder der Anwendung ab, mit der die Präsentation geöffnet wird. Beim Aktivieren von Hyperlinks kann die eigene Standardanwendung als Stammverzeichnis verwendet werden.

### Kann ich die ClsId des Stammverzeichnisses für einzelne Hyperlinks ändern?

Nein, die ClsId des Stammverzeichnisses wird normalerweise auf Präsentationsebene festgelegt und gilt für alle Hyperlinks innerhalb der Präsentation. Wenn Sie für einzelne Hyperlinks unterschiedliche Anwendungen angeben müssen, müssen Sie diese Hyperlinks möglicherweise separat in Ihrem Code behandeln.

### Gibt es Einschränkungen hinsichtlich der CLSIDs, die ich verwenden kann?

Die verwendbaren CLSIDs werden normalerweise durch die auf dem System installierten Anwendungen bestimmt. Sie sollten CLSIDs verwenden, die gültigen Anwendungen entsprechen, die Hyperlinks verarbeiten können. Beachten Sie, dass die Verwendung einer ungültigen CLSID zu unerwartetem Verhalten führen kann.