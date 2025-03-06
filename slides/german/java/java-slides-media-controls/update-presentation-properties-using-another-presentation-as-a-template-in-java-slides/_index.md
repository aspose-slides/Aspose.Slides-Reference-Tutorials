---
title: Aktualisieren der Präsentationseigenschaften mithilfe einer anderen Präsentation als Vorlage in Java Slides
linktitle: Aktualisieren der Präsentationseigenschaften mithilfe einer anderen Präsentation als Vorlage in Java Slides
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Verbessern Sie PowerPoint-Präsentationen mit aktualisierten Metadaten mithilfe von Aspose.Slides für Java. Erfahren Sie, wie Sie Eigenschaften wie Autor, Titel und Schlüsselwörter mithilfe von Vorlagen in Java Slides aktualisieren.
weight: 14
url: /de/java/media-controls/update-presentation-properties-using-another-presentation-as-a-template-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Einführung zum Aktualisieren von Präsentationseigenschaften mithilfe einer anderen Präsentation als Vorlage in Java Slides

In diesem Tutorial führen wir Sie durch den Prozess der Aktualisierung von Präsentationseigenschaften (Metadaten) für PowerPoint-Präsentationen mit Aspose.Slides für Java. Sie können eine andere Präsentation als Vorlage verwenden, um Eigenschaften wie Autor, Titel, Schlüsselwörter und mehr zu aktualisieren. Wir stellen Ihnen Schritt-für-Schritt-Anleitungen und Quellcodebeispiele zur Verfügung.

## Voraussetzungen

 Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für Java-Bibliothek in Ihr Java-Projekt integriert haben. Sie können sie hier herunterladen:[Hier](https://releases.aspose.com/slides/java/).

## Schritt 1: Richten Sie Ihr Projekt ein

Stellen Sie sicher, dass Sie ein Java-Projekt erstellt und die Aspose.Slides-Bibliothek für Java zu den Abhängigkeiten Ihres Projekts hinzugefügt haben.

## Schritt 2: Erforderliche Pakete importieren

Sie müssen die erforderlichen Aspose.Slides-Pakete importieren, um mit Präsentationseigenschaften arbeiten zu können. Fügen Sie am Anfang Ihrer Java-Klasse die folgenden Importanweisungen ein:

```java
import com.aspose.slides.DocumentProperties;
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.IPresentationInfo;
import com.aspose.slides.PresentationFactory;
```

## Schritt 3: Präsentationseigenschaften aktualisieren

Lassen Sie uns nun die Präsentationseigenschaften aktualisieren und dabei eine andere Präsentation als Vorlage verwenden. In diesem Beispiel aktualisieren wir die Eigenschaften für mehrere Präsentationen, aber Sie können diesen Code an Ihren spezifischen Anwendungsfall anpassen.

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";

// Laden Sie die Vorlagepräsentation, aus der Sie Eigenschaften kopieren möchten
DocumentProperties template;
IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
template = (DocumentProperties) info.readDocumentProperties();

// Legen Sie die Eigenschaften fest, die Sie aktualisieren möchten
template.setAuthor("Template Author");
template.setTitle("Template Title");
template.setCategory("Template Category");
template.setKeywords("Keyword1, Keyword2, Keyword3");
template.setCompany("Our Company");
template.setComments("Created from template");
template.setContentType("Template Content");
template.setSubject("Template Subject");

// Aktualisieren Sie mehrere Präsentationen mit derselben Vorlage
updateByTemplate(dataDir + "doc1.pptx", template);
updateByTemplate(dataDir + "doc2.odp", template);
updateByTemplate(dataDir + "doc3.ppt", template);
```

##  Schritt 4: Definieren Sie die`updateByTemplate` Method

Definieren wir eine Methode zum Aktualisieren der Eigenschaften einzelner Präsentationen mithilfe der Vorlage. Diese Methode verwendet den Pfad der zu aktualisierenden Präsentation und die Vorlageneigenschaften als Parameter.

```java
private static void updateByTemplate(String path, IDocumentProperties template)
{
    // Laden Sie die zu aktualisierende Präsentation
    IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
    
    // Aktualisieren Sie die Dokumenteigenschaften mithilfe der Vorlage
    toUpdate.updateDocumentProperties(template);
    
    // Speichern der aktualisierten Präsentation
    toUpdate.writeBindedPresentation(path);
}
```

## Vollständiger Quellcode zum Aktualisieren von Präsentationseigenschaften unter Verwendung einer anderen Präsentation als Vorlage in Java-Folien

```java
	// Der Pfad zum Dokumentverzeichnis.
	String dataDir = "Your Document Directory";
	DocumentProperties template;
	IPresentationInfo info = PresentationFactory.getInstance().getPresentationInfo(dataDir + "template.pptx");
	template = (DocumentProperties) info.readDocumentProperties();
	template.setAuthor("Template Author");
	template.setTitle("Template Title");
	template.setCategory("Template Category");
	template.setKeywords("Keyword1, Keyword2, Keyword3");
	template.setCompany("Our Company");
	template.setComments("Created from template");
	template.setContentType("Template Content");
	template.setSubject("Template Subject");
	updateByTemplate(dataDir + "doc1.pptx", template);
	updateByTemplate(dataDir + "doc2.odp", template);
	updateByTemplate(dataDir + "doc3.ppt", template);
}
private static void updateByTemplate(String path, IDocumentProperties template)
{
	IPresentationInfo toUpdate = PresentationFactory.getInstance().getPresentationInfo(path);
	toUpdate.updateDocumentProperties(template);
	toUpdate.writeBindedPresentation(path);
```

## Abschluss

In diesem umfassenden Tutorial haben wir untersucht, wie man Präsentationseigenschaften in PowerPoint-Präsentationen mit Aspose.Slides für Java aktualisiert. Wir haben uns insbesondere darauf konzentriert, eine andere Präsentation als Vorlage zu verwenden, um Metadaten wie Autorennamen, Titel, Schlüsselwörter und mehr effizient zu aktualisieren.

## Häufig gestellte Fragen

### Wie kann ich Eigenschaften für weitere Präsentationen aktualisieren?

 Sie können die Eigenschaften für mehrere Präsentationen aktualisieren, indem Sie den`updateByTemplate` Methode für jede Präsentation mit dem gewünschten Pfad.

### Kann ich diesen Code für verschiedene Eigenschaften anpassen?

Ja, Sie können den Code anpassen, um bestimmte Eigenschaften entsprechend Ihren Anforderungen zu aktualisieren. Ändern Sie einfach die`template` Objekt mit den gewünschten Eigenschaftswerten.

### Gibt es eine Einschränkung hinsichtlich der Art der Präsentationen, die aktualisiert werden können?

Nein, Sie können Eigenschaften für Präsentationen in verschiedenen Formaten aktualisieren, einschließlich PPTX, ODP und PPT.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
