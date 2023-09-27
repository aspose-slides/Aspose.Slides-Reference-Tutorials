---
title: Als vordefinierten Ansichtstyp in Java-Folien speichern
linktitle: Als vordefinierten Ansichtstyp in Java-Folien speichern
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java vordefinierte Ansichtstypen in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen und FAQs.
type: docs
weight: 10
url: /de/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Einführung in das Speichern als vordefinierten Ansichtstyp in Java-Folien

In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Slides für Java eine Präsentation mit einem vordefinierten Ansichtstyp speichern. Wir stellen Ihnen den notwendigen Code und Erklärungen zur Verfügung, um diese Aufgabe erfolgreich zu erledigen.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- Grundkenntnisse der Java-Programmierung.
- Aspose.Slides für Java-Bibliothek installiert.
- Integrierte Entwicklungsumgebung (IDE) Ihrer Wahl.

## Einrichten Ihrer Umgebung

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Erstellen Sie ein neues Java-Projekt in Ihrer IDE.
2. Fügen Sie die Aspose.Slides for Java-Bibliothek als Abhängigkeit zu Ihrem Projekt hinzu.

Nachdem Ihre Umgebung nun eingerichtet ist, fahren wir mit dem Code fort.

## Schritt 1: Erstellen einer Präsentation

Um das Speichern einer Präsentation mit einem vordefinierten Ansichtstyp zu demonstrieren, erstellen wir zunächst eine neue Präsentation. Hier ist der Code zum Erstellen einer Präsentation:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Öffnen der Präsentationsdatei
Presentation presentation = new Presentation();
```

 In diesem Code erstellen wir einen neuen`Presentation` Objekt, das unsere PowerPoint-Präsentation darstellt.

## Schritt 2: Festlegen des Ansichtstyps

Als Nächstes legen wir den Ansichtstyp für unsere Präsentation fest. Ansichtstypen legen fest, wie die Präsentation beim Öffnen angezeigt wird. In diesem Beispiel stellen wir es auf „Folienmasteransicht“ ein. Hier ist der Code:

```java
// Ansichtstyp festlegen
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Im obigen Code verwenden wir die`setLastView` Methode der`ViewProperties` Klasse, auf die der Ansichtstyp festgelegt werden soll`SlideMasterView`. Sie können bei Bedarf andere Ansichtstypen auswählen.

## Schritt 3: Speichern der Präsentation

Nachdem wir nun unsere Präsentation erstellt und den Ansichtstyp festgelegt haben, ist es an der Zeit, die Präsentation zu speichern. Wir speichern es im PPTX-Format. Hier ist der Code:

```java
// Präsentation speichern
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 In diesem Code verwenden wir die`save` Methode der`Presentation` Klasse, um die Präsentation mit dem angegebenen Dateinamen und Format zu speichern.

## Vollständiger Quellcode zum Speichern als vordefinierter Ansichtstyp in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Öffnen der Präsentationsdatei
Presentation presentation = new Presentation();
try
{
	// Ansichtstyp festlegen
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Präsentation speichern
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java eine Präsentation mit einem vordefinierten Ansichtstyp in Java speichert. Indem Sie den bereitgestellten Code und die Schritte befolgen, können Sie ganz einfach den Ansichtstyp Ihrer Präsentationen festlegen und sie im gewünschten Format speichern.

## FAQs

### Wie ändere ich den Ansichtstyp auf etwas anderes als „Folienmasteransicht“?

 Um den Ansichtstyp auf etwas anderes als „Folienmasteransicht“ zu ändern, ersetzen Sie ihn einfach`ViewType.SlideMasterView` mit dem gewünschten Ansichtstyp, z`ViewType.NormalView` oder`ViewType.SlideSorterView`, im Code, in dem wir den Ansichtstyp festlegen.

### Kann ich Ansichtseigenschaften für einzelne Folien in der Präsentation festlegen?

Ja, Sie können mit Aspose.Slides für Java Ansichtseigenschaften für einzelne Folien festlegen. Sie können auf die Eigenschaften jeder Folie separat zugreifen und diese bearbeiten, indem Sie die Folien in der Präsentation durchlaufen.

### In welchen anderen Formaten kann ich meine Präsentation speichern?

Aspose.Slides für Java unterstützt verschiedene Ausgabeformate, darunter PPTX, PDF, TIFF, HTML und mehr. Sie können beim Speichern Ihrer Präsentation das gewünschte Format festlegen, indem Sie das entsprechende verwenden`SaveFormat` Enum-Wert.

### Ist Aspose.Slides für Java für die Stapelverarbeitung von Präsentationen geeignet?

Ja, Aspose.Slides für Java eignet sich gut für Stapelverarbeitungsaufgaben. Sie können die Verarbeitung mehrerer Präsentationen automatisieren, Änderungen anwenden und diese mithilfe von Java-Code in großen Mengen speichern.

### Wo finde ich weitere Informationen und Dokumentation zu Aspose.Slides für Java?

 Eine umfassende Dokumentation und Referenzen zu Aspose.Slides für Java finden Sie auf der Dokumentationswebsite:[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).