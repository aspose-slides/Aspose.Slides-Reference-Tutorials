---
"description": "Erfahren Sie, wie Sie schreibgeschützte, empfohlene Eigenschaften in Java PowerPoint-Präsentationen mit Aspose.Slides für Java aktivieren. Folgen Sie unserer Schritt-für-Schritt-Anleitung mit Quellcodebeispielen für verbesserte Präsentationssicherheit."
"linktitle": "Schreibgeschützte empfohlene Eigenschaften in Java-Folien"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Schreibgeschützte empfohlene Eigenschaften in Java-Folien"
"url": "/de/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Schreibgeschützte empfohlene Eigenschaften in Java-Folien


## Einführung in die Aktivierung schreibgeschützter empfohlener Eigenschaften in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie schreibgeschützte, empfohlene Eigenschaften für PowerPoint-Präsentationen mit Aspose.Slides für Java aktivieren. Schreibgeschützte, empfohlene Eigenschaften sind nützlich, wenn Sie Benutzer dazu anregen möchten, eine Präsentation ohne Änderungen anzusehen. Diese Eigenschaften empfehlen, die Präsentation schreibgeschützt zu öffnen. Wir stellen Ihnen dazu eine Schritt-für-Schritt-Anleitung sowie Java-Quellcode zur Verfügung.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihrem Projekt eingerichtet haben. Sie können sie von der [Aspose.Slides für Java-Website](https://products.aspose.com/slides/java/).

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

In diesem Code-Ausschnitt verwenden wir die `getProtectionManager().setReadOnlyRecommended(true)` Methode, um die Eigenschaft Schreibgeschützt empfohlen auf `true`Dadurch wird sichergestellt, dass beim Öffnen der Präsentation die Aufforderung angezeigt wird, diese im schreibgeschützten Modus zu öffnen.

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

In diesem Tutorial haben Sie gelernt, wie Sie die Eigenschaft „Schreibgeschützt empfohlen“ für eine PowerPoint-Präsentation mit Aspose.Slides für Java aktivieren. Diese Funktion ist hilfreich, wenn Sie die Bearbeitung einschränken und die Betrachter dazu anregen möchten, die Präsentation im Lesemodus zu verwenden. Sie können die Sicherheit zusätzlich erhöhen, indem Sie ein Kennwort für die Präsentation festlegen.

## Häufig gestellte Fragen

### Wie deaktiviere ich die Eigenschaft „Schreibgeschützt empfohlen“?

Um die Eigenschaft „Schreibgeschützt empfohlen“ zu deaktivieren, verwenden Sie einfach den folgenden Code:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Kann ich für eine schreibgeschützte, empfohlene Präsentation ein Kennwort festlegen?

Ja, Sie können ein Passwort für eine schreibgeschützte empfohlene Präsentation mit Aspose.Slides für Java festlegen. Sie können das `setPassword` Methode zum Festlegen eines Kennworts für die Präsentation. Wenn ein Kennwort festgelegt ist, müssen Benutzer es eingeben, um die Präsentation zu öffnen, auch im schreibgeschützten Modus.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Denken Sie daran, zu ersetzen `"YourPassword"` mit Ihrem gewünschten Passwort.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}