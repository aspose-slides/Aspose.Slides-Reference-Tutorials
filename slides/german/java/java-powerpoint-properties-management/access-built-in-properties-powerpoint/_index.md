---
title: Zugriff auf integrierte Eigenschaften in PowerPoint
linktitle: Zugriff auf integrierte Eigenschaften in PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint zugreifen. Dieses Tutorial führt Sie durch das Abrufen von Autor, Erstellungsdatum und mehr.
weight: 10
url: /de/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint-Präsentationen zugreifen können. Aspose.Slides ist eine leistungsstarke Bibliothek, die es Java-Entwicklern ermöglicht, programmgesteuert mit PowerPoint-Präsentationen zu arbeiten und Aufgaben wie das nahtlose Lesen und Ändern von Eigenschaften zu ermöglichen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist. Sie können es hier herunterladen:[Hier](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides für Java: Laden Sie Aspose.Slides für Java herunter und installieren Sie es von[dieser Link](https://releases.aspose.com/slides/java/).

## Pakete importieren
Zuerst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren. Fügen Sie am Anfang Ihrer Java-Datei die folgende Importanweisung hinzu:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Schritt 1: Einrichten des Präsentationsobjekts
Richten Sie zunächst das Präsentationsobjekt so ein, dass es die PowerPoint-Präsentation darstellt, mit der Sie arbeiten möchten. So können Sie es tun:
```java
// Der Pfad zum Verzeichnis, das die Präsentationsdatei enthält
String dataDir = "path_to_your_presentation_directory/";
// Instanziieren der Präsentationsklasse
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Schritt 2: Zugriff auf die Dokumenteigenschaften
Nachdem Sie das Präsentationsobjekt eingerichtet haben, können Sie über die Schnittstelle IDocumentProperties auf die integrierten Eigenschaften der Präsentation zugreifen. So können Sie verschiedene Eigenschaften abrufen:
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
### Zuletzt geändert durch
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
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java auf integrierte Eigenschaften in PowerPoint-Präsentationen zugreift. Indem Sie die oben beschriebenen Schritte befolgen, können Sie verschiedene Eigenschaften wie Autor, Erstellungsdatum und Titel problemlos programmgesteuert abrufen.
## Häufig gestellte Fragen
### Kann ich diese integrierten Eigenschaften mit Aspose.Slides für Java ändern?
Ja, Sie können diese Eigenschaften mit Aspose.Slides ändern. Verwenden Sie einfach die entsprechenden Setter-Methoden, die von der IDocumentProperties-Schnittstelle bereitgestellt werden.
### Ist Aspose.Slides mit verschiedenen Versionen von PowerPoint kompatibel?
Aspose.Slides unterstützt eine Vielzahl von PowerPoint-Versionen und gewährleistet so die Kompatibilität zwischen verschiedenen Plattformen.
### Kann ich auch benutzerdefinierte Eigenschaften abrufen?
Ja, neben integrierten Eigenschaften können Sie mit Aspose.Slides für Java auch benutzerdefinierte Eigenschaften abrufen und ändern.
### Bietet Aspose.Slides Dokumentation und Support?
 Ja, Sie finden umfassende Dokumentation und Zugriff auf Support-Foren auf der[Aspose-Website](https://reference.aspose.com/slides/java/).
### Gibt es eine Testversion von Aspose.Slides für Java?
 Ja, Sie können eine kostenlose Testversion herunterladen von[Hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
