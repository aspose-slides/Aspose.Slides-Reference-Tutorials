---
title: Benutzerdefinierte Dokumenteigenschaften in Java-Folien hinzufügen
linktitle: Benutzerdefinierte Dokumenteigenschaften in Java-Folien hinzufügen
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit benutzerdefinierten Dokumenteigenschaften in Java Slides verbessern. Schritt-für-Schritt-Anleitung mit Codebeispielen unter Verwendung von Aspose.Slides für Java.
type: docs
weight: 13
url: /de/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

## Einführung in das Hinzufügen benutzerdefinierter Dokumenteigenschaften in Java-Folien

In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens benutzerdefinierter Dokumenteigenschaften zu einer PowerPoint-Präsentation mit Aspose.Slides für Java. Mit benutzerdefinierten Dokumenteigenschaften können Sie zusätzliche Informationen zur Präsentation als Referenz oder zur Kategorisierung speichern.

## Voraussetzungen

Stellen Sie vor dem Beginn sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt installiert und eingerichtet haben.

## Schritt 1: Erforderliche Pakete importieren

```java
import com.aspose.slides.*;
```

## Schritt 2: Erstellen Sie eine neue Präsentation

Zuerst müssen Sie ein neues Präsentationsobjekt erstellen. Dies können Sie wie folgt tun:

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren der Präsentationsklasse
Presentation presentation = new Presentation();
```

## Schritt 3: Dokumenteigenschaften abrufen

Als Nächstes rufen Sie die Dokumenteigenschaften der Präsentation ab. Zu diesen Eigenschaften gehören integrierte Eigenschaften wie Titel, Autor und benutzerdefinierte Eigenschaften, die Sie hinzufügen können.

```java
// Abrufen von Dokumenteigenschaften
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Schritt 4: Hinzufügen benutzerdefinierter Eigenschaften

Fügen wir nun der Präsentation benutzerdefinierte Eigenschaften hinzu. Benutzerdefinierte Eigenschaften bestehen aus einem Namen und einem Wert. Sie können sie verwenden, um beliebige Informationen zu speichern.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Schritt 5: Abrufen eines Eigenschaftsnamens an einem bestimmten Index

Sie können auch den Namen einer benutzerdefinierten Eigenschaft an einem bestimmten Index abrufen. Dies kann nützlich sein, wenn Sie mit bestimmten Eigenschaften arbeiten müssen.

```java
// Abrufen des Eigenschaftsnamens an einem bestimmten Index
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Schritt 6: Entfernen einer ausgewählten Eigenschaft

Wenn Sie eine benutzerdefinierte Eigenschaft entfernen möchten, können Sie dies tun, indem Sie ihren Namen angeben. Hier entfernen wir die Eigenschaft, die wir in Schritt 5 erhalten haben.

```java
// Ausgewählte Eigenschaft entfernen
documentProperties.removeCustomProperty(getPropertyName);
```

## Schritt 7: Speichern der Präsentation

Speichern Sie abschließend die Präsentation mit den hinzugefügten und entfernten benutzerdefinierten Eigenschaften in einer Datei.

```java
// Präsentation speichern
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Vollständiger Quellcode zum Hinzufügen benutzerdefinierter Dokumenteigenschaften in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren der Präsentationsklasse
Presentation presentation = new Presentation();
// Abrufen von Dokumenteigenschaften
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Hinzufügen benutzerdefinierter Eigenschaften
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Abrufen des Eigenschaftsnamens an einem bestimmten Index
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Ausgewählte Eigenschaft entfernen
documentProperties.removeCustomProperty(getPropertyName);
// Präsentation speichern
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Abschluss

Sie haben gelernt, wie Sie mit Aspose.Slides in Java einer PowerPoint-Präsentation benutzerdefinierte Dokumenteigenschaften hinzufügen. Benutzerdefinierte Eigenschaften können hilfreich sein, um zusätzliche Informationen zu Ihren Präsentationen zu speichern. Sie können dieses Wissen erweitern, um bei Bedarf weitere benutzerdefinierte Eigenschaften für Ihren spezifischen Anwendungsfall einzuschließen.

## Häufig gestellte Fragen

### Wie rufe ich den Wert einer benutzerdefinierten Eigenschaft ab?

 Um den Wert einer benutzerdefinierten Eigenschaft abzurufen, können Sie den`get_Item` Methode auf der`documentProperties` Objekt. Beispiel:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Kann ich benutzerdefinierte Eigenschaften verschiedener Datentypen hinzufügen?

Ja, Sie können benutzerdefinierte Eigenschaften verschiedener Datentypen hinzufügen, darunter Zahlen, Zeichenfolgen, Daten und mehr, wie im Beispiel gezeigt. Aspose.Slides für Java verarbeitet verschiedene Datentypen nahtlos.

### Gibt es eine Begrenzung für die Anzahl der benutzerdefinierten Eigenschaften, die ich hinzufügen kann?

Es gibt keine strikte Beschränkung für die Anzahl der benutzerdefinierten Eigenschaften, die Sie hinzufügen können. Beachten Sie jedoch, dass das Hinzufügen einer übermäßigen Anzahl von Eigenschaften die Leistung und Größe Ihrer Präsentationsdatei beeinträchtigen kann.

### Wie kann ich alle benutzerdefinierten Eigenschaften in einer Präsentation auflisten?

Sie können alle benutzerdefinierten Eigenschaften durchlaufen, um sie aufzulisten. Hier ist ein Beispiel dafür:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Dieser Code zeigt die Namen und Werte aller benutzerdefinierten Eigenschaften in der Präsentation an.