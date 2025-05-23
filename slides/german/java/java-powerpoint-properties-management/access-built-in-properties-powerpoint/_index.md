---
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint zugreifen. Dieses Tutorial führt Sie durch das Abrufen von Autor, Erstellungsdatum und mehr."
"linktitle": "Zugriff auf integrierte Eigenschaften in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-Verarbeitungs-API"
"title": "Zugriff auf integrierte Eigenschaften in PowerPoint"
"url": "/de/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zugriff auf integrierte Eigenschaften in PowerPoint

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint-Präsentationen zugreifen. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Java-Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten und Aufgaben wie das nahtlose Lesen und Ändern von Eigenschaften zu ermöglichen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es herunterladen von [Hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von [dieser Link](https://releases.aspose.com/slides/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren. Fügen Sie am Anfang Ihrer Java-Datei die folgende Importanweisung ein:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Schritt 1: Einrichten des Präsentationsobjekts
Richten Sie zunächst das Präsentationsobjekt so ein, dass es die PowerPoint-Präsentation darstellt, mit der Sie arbeiten möchten. So geht's:
```java
// Der Pfad zum Verzeichnis, das die Präsentationsdatei enthält
String dataDir = "path_to_your_presentation_directory/";
// Instanziieren der Präsentationsklasse
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Schritt 2: Zugriff auf die Dokumenteigenschaften
Nachdem Sie das Präsentationsobjekt eingerichtet haben, können Sie über die IDocumentProperties-Schnittstelle auf die integrierten Eigenschaften der Präsentation zugreifen. So rufen Sie verschiedene Eigenschaften ab:
### Kategorie
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Aktueller Status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Erstellungsdatum
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Beschreibung
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Schlüsselwörter
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Zuletzt geändert von
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Aufsicht
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Änderungsdatum
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Präsentationsformat
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Letztes Druckdatum
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Gemeinsame Nutzung durch Produzenten
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Thema
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titel
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint-Präsentationen zugreifen. Mit den oben beschriebenen Schritten können Sie verschiedene Eigenschaften wie Autor, Erstellungsdatum und Titel einfach programmgesteuert abrufen.
## Häufig gestellte Fragen
### Kann ich diese integrierten Eigenschaften mit Aspose.Slides für Java ändern?
Ja, Sie können diese Eigenschaften mit Aspose.Slides ändern. Verwenden Sie dazu einfach die entsprechenden Setter-Methoden der IDocumentProperties-Schnittstelle.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt eine Vielzahl von PowerPoint-Versionen und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### Kann ich auch benutzerdefinierte Eigenschaften abrufen?
Ja, neben integrierten Eigenschaften können Sie mit Aspose.Slides für Java auch benutzerdefinierte Eigenschaften abrufen und ändern.
### Bietet Aspose.Slides Dokumentation und Support?
Ja, Sie finden umfassende Dokumentation und Zugriff auf Support-Foren auf der [Aspose-Website](https://reference.aspose.com/slides/java/).
### Gibt es eine Testversion für Aspose.Slides für Java?
Ja, Sie können eine kostenlose Testversion herunterladen von [Hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}