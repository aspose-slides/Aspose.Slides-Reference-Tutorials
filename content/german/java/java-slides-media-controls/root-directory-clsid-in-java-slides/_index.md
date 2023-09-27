---
title: Stammverzeichnis ClsId in Java Slides
linktitle: Stammverzeichnis ClsId in Java Slides
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie die Stammverzeichnis-ClsId in Aspose.Slides für Java-Präsentationen festlegen. Passen Sie das Hyperlink-Verhalten mit CLSID an.
type: docs
weight: 10
url: /de/java/media-controls/root-directory-clsid-in-java-slides/
---

## Einführung in das Festlegen der Stammverzeichnis-ClsId in Aspose.Slides für Java

In Aspose.Slides für Java können Sie die Stammverzeichnis-ClsId festlegen. Hierbei handelt es sich um die CLSID (Klassenkennung), mit der die Anwendung angegeben wird, die als Stammverzeichnis verwendet werden soll, wenn ein Hyperlink in Ihrer Präsentation aktiviert wird. In dieser Anleitung führen wir Sie Schritt für Schritt durch die Vorgehensweise.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

- Java Development Kit (JDK) auf Ihrem System installiert.
-  Aspose.Slides für Java-Bibliothek zu Ihrem Projekt hinzugefügt. Sie können es herunterladen unter[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
- Ein Code-Editor oder eine integrierte Entwicklungsumgebung (IDE), die für die Java-Entwicklung eingerichtet wurde.

## Schritt 1: Erstellen Sie eine neue Präsentation

Lassen Sie uns zunächst eine neue Präsentation mit Aspose.Slides für Java erstellen. In diesem Beispiel erstellen wir eine leere Präsentation.

```java
// Name der Ausgabedatei
String resultPath = "your_output_path/pres.ppt"; // Ersetzen Sie „Ihr_Ausgabepfad“ durch Ihr gewünschtes Ausgabeverzeichnis.
Presentation pres = new Presentation();
```

 Im obigen Code definieren wir den Pfad für die Ausgabepräsentationsdatei und erstellen eine neue`Presentation` Objekt.

## Schritt 2: Legen Sie die ClsId des Stammverzeichnisses fest

 Um die Stammverzeichnis-ClsId festzulegen, müssen Sie eine Instanz von erstellen`PptOptions`und stellen Sie die gewünschte CLSID ein. Die CLSID stellt die Anwendung dar, die als Stammverzeichnis verwendet wird, wenn ein Hyperlink aktiviert wird.

```java
PptOptions pptOptions = new PptOptions();
// Setzen Sie CLSID auf „Microsoft Powerpoint.Show.8“.
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 Im obigen Code erstellen wir eine`PptOptions` Objekt und setzen Sie die CLSID auf „Microsoft Powerpoint.Show.8“. Sie können es durch die CLSID der Anwendung ersetzen, die Sie als Stammverzeichnis verwenden möchten.

## Schritt 3: Speichern Sie die Präsentation

Speichern wir nun die Präsentation mit der festgelegten Stammverzeichnis-ClsId.

```java
// Präsentation speichern
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 In diesem Schritt speichern wir die Präsentation unter dem angegebenen`resultPath` mit dem`PptOptions` wir haben es früher erstellt.

## Schritt 4: Aufräumen

 Vergessen Sie nicht, das zu entsorgen`Presentation` Objekt, um alle zugewiesenen Ressourcen freizugeben.

```java
if (pres != null) {
    pres.dispose();
}
```

## Vollständiger Quellcode für das Stammverzeichnis ClsId in Java-Folien

```java
// Name der Ausgabedatei
String resultPath = RunExamples.getOutPath() + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// CLSID auf „Microsoft Powerpoint.Show.8“ setzen
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Präsentation speichern
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Abschluss

Sie haben die Stammverzeichnis-ClsId in Aspose.Slides für Java erfolgreich festgelegt. Auf diese Weise können Sie die Anwendung angeben, die als Stammverzeichnis verwendet wird, wenn Hyperlinks in Ihrer Präsentation aktiviert werden. Sie können die CLSID entsprechend Ihren spezifischen Anforderungen anpassen.

## FAQs

### Wie finde ich die CLSID für eine bestimmte Anwendung?

Um die CLSID für eine bestimmte Anwendung zu finden, können Sie auf die Dokumentation oder Ressourcen zurückgreifen, die vom Entwickler der Anwendung bereitgestellt werden. CLSIDs sind eindeutige Bezeichner, die COM-Objekten zugewiesen werden und normalerweise für jede Anwendung spezifisch sind.

### Kann ich eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen?

 Ja, Sie können eine benutzerdefinierte CLSID für das Stammverzeichnis festlegen, indem Sie den gewünschten CLSID-Wert mithilfe von angeben`setRootDirectoryClsid` -Methode, wie im Codebeispiel gezeigt. Dadurch können Sie eine bestimmte Anwendung als Stammverzeichnis verwenden, wenn Hyperlinks in Ihrer Präsentation aktiviert sind.

### Was passiert, wenn ich die Stammverzeichnis-ClsId nicht festlege?

Wenn Sie die Stammverzeichnis-ClsId nicht festlegen, hängt das Standardverhalten vom Viewer oder der Anwendung ab, die zum Öffnen der Präsentation verwendet wird. Es kann seine eigene Standardanwendung als Stammverzeichnis verwenden, wenn Hyperlinks aktiviert sind.

### Kann ich die Stammverzeichnis-ClsId für einzelne Hyperlinks ändern?

Nein, die Stammverzeichnis-ClsId wird normalerweise auf Präsentationsebene festgelegt und gilt für alle Hyperlinks innerhalb der Präsentation. Wenn Sie unterschiedliche Anwendungen für einzelne Hyperlinks angeben müssen, müssen Sie diese Hyperlinks möglicherweise separat in Ihrem Code behandeln.

### Gibt es Einschränkungen hinsichtlich der CLSIDs, die ich verwenden kann?

Die CLSIDs, die Sie verwenden können, werden normalerweise von den auf dem System installierten Anwendungen bestimmt. Sie sollten CLSIDs verwenden, die gültigen Anwendungen entsprechen, die Hyperlinks verarbeiten können. Beachten Sie, dass die Verwendung einer ungültigen CLSID zu unerwartetem Verhalten führen kann.