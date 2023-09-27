---
title: Fügen Sie benutzerdefinierte Dokumenteigenschaften in Java Slides hinzu
linktitle: Fügen Sie benutzerdefinierte Dokumenteigenschaften in Java Slides hinzu
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie PowerPoint-Präsentationen mit benutzerdefinierten Dokumenteigenschaften in Java Slides verbessern. Schritt-für-Schritt-Anleitung mit Codebeispielen mit Aspose.Slides für Java.
type: docs
weight: 13
url: /de/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

## Einführung in das Hinzufügen benutzerdefinierter Dokumenteigenschaften in Java-Folien

In diesem Tutorial führen wir Sie durch den Prozess des Hinzufügens benutzerdefinierter Dokumenteigenschaften zu einer PowerPoint-Präsentation mithilfe von Aspose.Slides für Java. Mit benutzerdefinierten Dokumenteigenschaften können Sie zusätzliche Informationen zur Präsentation als Referenz oder Kategorisierung speichern.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt installiert und eingerichtet ist.

## Schritt 1: Erforderliche Pakete importieren

```java
import com.aspose.slides.*;
```

## Schritt 2: Erstellen Sie eine neue Präsentation

Zunächst müssen Sie ein neues Präsentationsobjekt erstellen. Sie können dies wie folgt tun:

```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";

// Instanziieren Sie die Presentation-Klasse
Presentation presentation = new Presentation();
```

## Schritt 3: Dokumenteigenschaften abrufen

Als Nächstes rufen Sie die Dokumenteigenschaften der Präsentation ab. Zu diesen Eigenschaften gehören integrierte Eigenschaften wie Titel, Autor und benutzerdefinierte Eigenschaften, die Sie hinzufügen können.

```java
// Dokumenteigenschaften abrufen
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Schritt 4: Benutzerdefinierte Eigenschaften hinzufügen

Nun fügen wir der Präsentation benutzerdefinierte Eigenschaften hinzu. Benutzerdefinierte Eigenschaften bestehen aus einem Namen und einem Wert. Sie können sie zum Speichern beliebiger Informationen verwenden.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Schritt 5: Abrufen eines Eigenschaftsnamens an einem bestimmten Index

Sie können auch den Namen einer benutzerdefinierten Eigenschaft an einem bestimmten Index abrufen. Dies kann nützlich sein, wenn Sie mit bestimmten Eigenschaften arbeiten müssen.

```java
// Eigenschaftsnamen an einem bestimmten Index abrufen
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Schritt 6: Entfernen einer ausgewählten Eigenschaft

Wenn Sie eine benutzerdefinierte Eigenschaft entfernen möchten, können Sie dies tun, indem Sie ihren Namen angeben. Hier entfernen wir die Eigenschaft, die wir in Schritt 5 erhalten haben.

```java
// Ausgewählte Eigenschaft wird entfernt
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
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Document Directory";
// Instanziieren Sie die Presentation-Klasse
Presentation presentation = new Presentation();
// Dokumenteigenschaften abrufen
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Hinzufügen benutzerdefinierter Eigenschaften
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Eigenschaftsnamen an einem bestimmten Index abrufen
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Ausgewählte Eigenschaft wird entfernt
documentProperties.removeCustomProperty(getPropertyName);
// Präsentation speichern
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Abschluss

Sie haben gelernt, wie Sie mit Aspose.Slides benutzerdefinierte Dokumenteigenschaften zu einer PowerPoint-Präsentation in Java hinzufügen. Benutzerdefinierte Eigenschaften können für die Speicherung zusätzlicher Informationen zu Ihren Präsentationen nützlich sein. Sie können dieses Wissen erweitern, um je nach Bedarf weitere benutzerdefinierte Eigenschaften für Ihren spezifischen Anwendungsfall einzubeziehen.

## FAQs

### Wie rufe ich den Wert einer benutzerdefinierten Eigenschaft ab?

 Um den Wert einer benutzerdefinierten Eigenschaft abzurufen, können Sie die verwenden`get_Item` Methode auf der`documentProperties` Objekt. Zum Beispiel:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Kann ich benutzerdefinierte Eigenschaften verschiedener Datentypen hinzufügen?

Ja, Sie können benutzerdefinierte Eigenschaften verschiedener Datentypen hinzufügen, einschließlich Zahlen, Zeichenfolgen, Datumsangaben und mehr, wie im Beispiel gezeigt. Aspose.Slides für Java verarbeitet verschiedene Datentypen nahtlos.

### Gibt es eine Begrenzung für die Anzahl der benutzerdefinierten Eigenschaften, die ich hinzufügen kann?

Es gibt keine strenge Begrenzung für die Anzahl der benutzerdefinierten Eigenschaften, die Sie hinzufügen können. Bedenken Sie jedoch, dass das Hinzufügen einer übermäßigen Anzahl von Eigenschaften die Leistung und Größe Ihrer Präsentationsdatei beeinträchtigen kann.

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