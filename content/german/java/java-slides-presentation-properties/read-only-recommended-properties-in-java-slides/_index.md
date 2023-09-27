---
title: Schreibgeschützte empfohlene Eigenschaften in Java-Folien
linktitle: Schreibgeschützte empfohlene Eigenschaften in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java schreibgeschützte empfohlene Eigenschaften in Java-PowerPoint-Präsentationen aktivieren. Befolgen Sie unsere Schritt-für-Schritt-Anleitung mit Quellcode-Beispielen für mehr Präsentationssicherheit.
type: docs
weight: 17
url: /de/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Einführung in die Aktivierung schreibgeschützter empfohlener Eigenschaften in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe von Aspose.Slides für Java schreibgeschützte empfohlene Eigenschaften für PowerPoint-Präsentationen aktivieren. Schreibgeschützte empfohlene Eigenschaften können nützlich sein, wenn Sie Benutzer dazu ermutigen möchten, eine Präsentation anzusehen, ohne Änderungen vorzunehmen. Diese Eigenschaften legen nahe, dass die Präsentation im schreibgeschützten Modus geöffnet werden sollte. Wir stellen Ihnen dazu eine Schritt-für-Schritt-Anleitung zusammen mit dem Java-Quellcode zur Verfügung.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass in Ihrem Projekt die Aspose.Slides for Java-Bibliothek eingerichtet ist. Sie können es hier herunterladen[Aspose.Slides für Java-Website](https://products.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine neue PowerPoint-Präsentation

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für Java. Wenn Sie bereits eine Präsentation haben, können Sie diesen Schritt überspringen.

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Im obigen Code haben wir den Pfad für die PowerPoint-Ausgabedatei definiert und ein neues Präsentationsobjekt erstellt.

## Schritt 2: Aktivieren Sie die schreibgeschützte empfohlene Eigenschaft

Jetzt aktivieren wir die Eigenschaft „Schreibgeschützt empfohlen“ für die Präsentation.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 In diesem Codeausschnitt verwenden wir die`getProtectionManager().setReadOnlyRecommended(true)` Methode, auf die die Eigenschaft „Schreibgeschützt empfohlen“ festgelegt werden soll`true`. Dadurch wird sichergestellt, dass jemand, der die Präsentation öffnet, aufgefordert wird, sie im schreibgeschützten Modus zu öffnen.

## Schritt 3: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation mit aktivierter Eigenschaft „Schreibgeschützt empfohlen“.

## Vollständiger Quellcode für schreibgeschützte empfohlene Eigenschaften in Java-Folien

```java
String outPptxPath = RunExamples.getOutPath() + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben Sie erfahren, wie Sie die Eigenschaft „Schreibgeschützt empfohlen“ für eine PowerPoint-Präsentation mithilfe von Aspose.Slides für Java aktivieren. Diese Funktion kann hilfreich sein, wenn Sie die Bearbeitung einschränken und Zuschauer dazu ermutigen möchten, die Präsentation im schreibgeschützten Modus zu verwenden. Sie können die Sicherheit weiter erhöhen, indem Sie ein Passwort für die Präsentation festlegen.

## FAQs

### Wie deaktiviere ich die Eigenschaft „Schreibgeschützt empfohlen“?

Um die Eigenschaft „Schreibgeschützt empfohlen“ zu deaktivieren, verwenden Sie einfach den folgenden Code:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Kann ich ein Passwort für eine schreibgeschützte empfohlene Präsentation festlegen?

Ja, Sie können mit Aspose.Slides für Java ein Passwort für eine schreibgeschützte empfohlene Präsentation festlegen. Du kannst den ... benutzen`setPassword` Methode zum Festlegen eines Passworts für die Präsentation. Wenn ein Passwort festgelegt ist, müssen Benutzer dieses eingeben, um die Präsentation zu öffnen, auch im schreibgeschützten Modus.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Denken Sie daran, es auszutauschen`"YourPassword"` mit Ihrem Wunschpasswort.