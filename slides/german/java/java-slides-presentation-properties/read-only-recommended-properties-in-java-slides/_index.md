---
title: Schreibgeschützte empfohlene Eigenschaften in Java-Folien
linktitle: Schreibgeschützte empfohlene Eigenschaften in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java schreibgeschützte empfohlene Eigenschaften in Java PowerPoint-Präsentationen aktivieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Quellcodebeispielen für verbesserte Präsentationssicherheit.
weight: 17
url: /de/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung in das Aktivieren schreibgeschützter empfohlener Eigenschaften in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java schreibgeschützte empfohlene Eigenschaften für PowerPoint-Präsentationen aktivieren. Schreibgeschützte empfohlene Eigenschaften können nützlich sein, wenn Sie Benutzer dazu ermutigen möchten, eine Präsentation anzusehen, ohne Änderungen vorzunehmen. Diese Eigenschaften legen nahe, dass die Präsentation im schreibgeschützten Modus geöffnet werden soll. Wir stellen Ihnen dazu eine Schritt-für-Schritt-Anleitung sowie Java-Quellcode zur Verfügung.

## Voraussetzungen

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihrem Projekt eingerichtet haben. Sie können sie von der[Aspose.Slides für Java-Website](https://products.aspose.com/slides/java/).

## Schritt 1: Erstellen Sie eine neue PowerPoint-Präsentation

Wir beginnen mit der Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für Java. Wenn Sie bereits eine Präsentation haben, können Sie diesen Schritt überspringen.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

Im obigen Code haben wir den Pfad für die PowerPoint-Ausgabedatei definiert und ein neues Präsentationsobjekt erstellt.

## Schritt 2: Aktivieren Sie die schreibgeschützte empfohlene Eigenschaft

Aktivieren wir nun die Eigenschaft „Schreibgeschützt empfohlen“ für die Präsentation.

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

 In diesem Codeausschnitt verwenden wir die`getProtectionManager().setReadOnlyRecommended(true)` Methode, um die Eigenschaft Schreibgeschützt empfohlen auf`true`. Dadurch wird sichergestellt, dass beim Öffnen der Präsentation die Person aufgefordert wird, diese im schreibgeschützten Modus zu öffnen.

## Schritt 3: Speichern Sie die Präsentation

Abschließend speichern wir die Präsentation mit aktivierter Eigenschaft „Schreibgeschützt empfohlen“.

## Vollständiger Quellcode für schreibgeschützte empfohlene Eigenschaften in Java-Folien

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
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

In diesem Tutorial haben Sie gelernt, wie Sie die Eigenschaft „Schreibgeschützt empfohlen“ für eine PowerPoint-Präsentation mit Aspose.Slides für Java aktivieren. Diese Funktion kann hilfreich sein, wenn Sie die Bearbeitung einschränken und die Betrachter dazu ermutigen möchten, die Präsentation im schreibgeschützten Modus zu verwenden. Sie können die Sicherheit weiter erhöhen, indem Sie ein Kennwort für die Präsentation festlegen.

## Häufig gestellte Fragen

### Wie deaktiviere ich die Eigenschaft „Schreibgeschützt, empfohlen“?

Um die Eigenschaft „Schreibgeschützt empfohlen“ zu deaktivieren, verwenden Sie einfach den folgenden Code:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Kann ich für eine schreibgeschützte empfohlene Präsentation ein Kennwort festlegen?

Ja, Sie können ein Passwort für eine schreibgeschützte empfohlene Präsentation mit Aspose.Slides für Java festlegen. Sie können das`setPassword` Methode, um ein Kennwort für die Präsentation festzulegen. Wenn ein Kennwort festgelegt ist, müssen Benutzer es eingeben, um die Präsentation zu öffnen, auch im schreibgeschützten Modus.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Denken Sie daran, zu ersetzen`"YourPassword"` mit Ihrem gewünschten Passwort.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
