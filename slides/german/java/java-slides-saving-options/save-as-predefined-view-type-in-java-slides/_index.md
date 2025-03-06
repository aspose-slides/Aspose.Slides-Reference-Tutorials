---
title: Als vordefinierter Ansichtstyp in Java-Folien speichern
linktitle: Als vordefinierter Ansichtstyp in Java-Folien speichern
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java vordefinierte Ansichtstypen in Java Slides festlegen. Schritt-für-Schritt-Anleitung mit Codebeispielen und FAQs.
weight: 10
url: /de/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Als vordefinierter Ansichtstyp in Java-Folien speichern


## Einführung in „Als vordefinierten Ansichtstyp speichern“ in Java-Folien

In dieser Schritt-für-Schritt-Anleitung erfahren Sie, wie Sie mit Aspose.Slides für Java eine Präsentation mit einem vordefinierten Ansichtstyp speichern. Wir stellen Ihnen den erforderlichen Code und die Erklärungen zur Verfügung, damit Sie diese Aufgabe erfolgreich erledigen können.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes haben:

- Grundkenntnisse der Java-Programmierung.
- Aspose.Slides für Java-Bibliothek installiert.
- Integrierte Entwicklungsumgebung (IDE) Ihrer Wahl.

## Einrichten Ihrer Umgebung

Führen Sie zunächst die folgenden Schritte aus, um Ihre Entwicklungsumgebung einzurichten:

1. Erstellen Sie ein neues Java-Projekt in Ihrer IDE.
2. Fügen Sie Ihrem Projekt die Bibliothek Aspose.Slides für Java als Abhängigkeit hinzu.

Nachdem Ihre Umgebung nun eingerichtet ist, fahren wir mit dem Code fort.

## Schritt 1: Erstellen einer Präsentation

Um das Speichern einer Präsentation mit einem vordefinierten Ansichtstyp zu demonstrieren, erstellen wir zunächst eine neue Präsentation. Hier ist der Code zum Erstellen einer Präsentation:

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Öffnen der Präsentationsdatei
Presentation presentation = new Presentation();
```

 In diesem Code erstellen wir einen neuen`Presentation` Objekt, das unsere PowerPoint-Präsentation darstellt.

## Schritt 2: Festlegen des Ansichtstyps

Als Nächstes legen wir den Ansichtstyp für unsere Präsentation fest. Ansichtstypen definieren, wie die Präsentation beim Öffnen angezeigt wird. In diesem Beispiel legen wir „Folienmasteransicht“ fest. Hier ist der Code:

```java
// Festlegen des Ansichtstyps
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 Im obigen Code verwenden wir die`setLastView` Methode der`ViewProperties` Klasse, um den Ansichtstyp festzulegen auf`SlideMasterView`. Sie können nach Bedarf andere Ansichtstypen auswählen.

## Schritt 3: Speichern der Präsentation

Nachdem wir nun unsere Präsentation erstellt und den Ansichtstyp festgelegt haben, ist es an der Zeit, die Präsentation zu speichern. Wir speichern sie im PPTX-Format. Hier ist der Code:

```java
// Präsentation speichern
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 In diesem Code verwenden wir die`save` Methode der`Presentation` Klasse, um die Präsentation mit dem angegebenen Dateinamen und Format zu speichern.

## Vollständiger Quellcode zum Speichern als vordefinierter Ansichtstyp in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Öffnen der Präsentationsdatei
Presentation presentation = new Presentation();
try
{
	// Festlegen des Ansichtstyps
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

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java eine Präsentation mit einem vordefinierten Ansichtstyp in Java speichert. Indem Sie dem bereitgestellten Code und den Schritten folgen, können Sie den Ansichtstyp Ihrer Präsentationen einfach festlegen und sie im gewünschten Format speichern.

## Häufig gestellte Fragen

### Wie ändere ich den Ansichtstyp in etwas anderes als „Folienmasteransicht“?

 Um den Ansichtstyp auf etwas anderes als "Folienmasteransicht" zu ändern, ersetzen Sie einfach`ViewType.SlideMasterView` mit dem gewünschten Ansichtstyp, wie zum Beispiel`ViewType.NormalView` oder`ViewType.SlideSorterView`, im Code, in dem wir den Ansichtstyp festlegen.

### Kann ich Ansichtseigenschaften für einzelne Folien in der Präsentation festlegen?

Ja, Sie können mit Aspose.Slides für Java Ansichtseigenschaften für einzelne Folien festlegen. Sie können auf die Eigenschaften für jede Folie einzeln zugreifen und diese bearbeiten, indem Sie die Folien in der Präsentation durchlaufen.

### In welchen anderen Formaten kann ich meine Präsentation speichern?

Aspose.Slides für Java unterstützt verschiedene Ausgabeformate, darunter PPTX, PDF, TIFF, HTML und mehr. Sie können das gewünschte Format beim Speichern Ihrer Präsentation angeben, indem Sie die entsprechenden`SaveFormat` Enumerationswert.

### Ist Aspose.Slides für Java für die Stapelverarbeitung von Präsentationen geeignet?

Ja, Aspose.Slides für Java eignet sich gut für Stapelverarbeitungsaufgaben. Sie können die Verarbeitung mehrerer Präsentationen automatisieren, Änderungen anwenden und diese mit Java-Code in großen Mengen speichern.

### Wo finde ich weitere Informationen und Dokumentation zu Aspose.Slides für Java?

 Umfassende Dokumentationen und Referenzen zu Aspose.Slides für Java finden Sie auf der Dokumentationswebsite:[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
