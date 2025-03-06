---
title: Überprüfen Sie den Präsentationsschutz in Java-Folien
linktitle: Überprüfen Sie den Präsentationsschutz in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie den Präsentationsschutz in Java-Folien mit Aspose.Slides für Java überprüfen. Diese Schritt-für-Schritt-Anleitung enthält Codebeispiele für Schreib- und Öffnungsschutzprüfungen.
type: docs
weight: 15
url: /de/java/presentation-properties/check-presentation-protection-in-java-slides/
---

## Einführung in die Überprüfung des Präsentationsschutzes in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie den Präsentationsschutz mit Aspose.Slides für Java überprüfen. Wir behandeln zwei Szenarien: Überprüfen des Schreibschutzes und Überprüfen des Öffnungsschutzes für eine Präsentation. Wir stellen für jedes Szenario schrittweise Codebeispiele bereit.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die Bibliothek Aspose.Slides für Java in Ihrem Java-Projekt eingerichtet haben. Sie können sie von der Aspose-Website herunterladen und zu den Abhängigkeiten Ihres Projekts hinzufügen.

### Maven-Abhängigkeit

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Ersetzen`your_version_here` mit der von Ihnen verwendeten Version von Aspose.Slides für Java.

## Schritt 1: Schreibschutz prüfen

 Um zu prüfen, ob eine Präsentation durch ein Passwort schreibgeschützt ist, können Sie den`IPresentationInfo` Schnittstelle. Hier ist der Code dazu:

```java
// Pfad zur Quelldarstellung
String pptxFile = "path_to_presentation.pptx";

// Überprüfen des Schreibschutzkennworts über die IPresentationInfo-Schnittstelle
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Ersetzen`"path_to_presentation.pptx"` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei und`"password_here"` mit dem Schreibschutzpasswort.

## Schritt 2: Öffnen-Schutz prüfen

 Um zu prüfen, ob eine Präsentation durch ein Passwort zum Öffnen geschützt ist, können Sie den`IPresentationInfo` Schnittstelle. Hier ist der Code dazu:

```java
// Pfad zur Quelldarstellung
String pptFile = "path_to_presentation.ppt";

// Überprüfen des Schutzes beim Öffnen von Präsentationen über die IPresentationInfo-Schnittstelle
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Ersetzen`"path_to_presentation.ppt"` durch den tatsächlichen Pfad zu Ihrer Präsentationsdatei.

## Vollständiger Quellcode zum Prüfen des Präsentationsschutzes in Java-Folien

```java
//Pfad zur Quellendarstellung
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Überprüfen des Schreibschutzkennworts über die IPresentationInfo-Schnittstelle
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Überprüfen Sie das Schreibschutzkennwort über die IProtectionManager-Schnittstelle
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// Überprüfen des Schutzes beim Öffnen von Präsentationen über die IPresentationInfo-Schnittstelle
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man den Präsentationsschutz in Java-Folien mit Aspose.Slides für Java überprüft. Wir haben zwei Szenarien behandelt: Überprüfung des Schreibschutzes und Überprüfung des Öffnungsschutzes. Sie können diese Prüfungen jetzt in Ihre Java-Anwendungen integrieren, um geschützte Präsentationen effektiv zu handhaben.

## Häufig gestellte Fragen

### Wie erhalte ich Aspose.Slides für Java?

Sie können Aspose.Slides für Java von der Aspose-Website herunterladen oder es als Maven-Abhängigkeit zu Ihrem Projekt hinzufügen, wie im Abschnitt „Voraussetzungen“ gezeigt.

### Kann ich für eine Präsentation sowohl den Schreibschutz als auch den Öffnungsschutz überprüfen?

Ja, Sie können mithilfe der bereitgestellten Codebeispiele sowohl den Schreibschutz als auch den Öffnungsschutz für eine Präsentation überprüfen.

### Was soll ich tun, wenn ich das Schutzkennwort vergesse?

Wenn Sie das Schutzkennwort für eine Präsentation vergessen, gibt es keine integrierte Möglichkeit, es wiederherzustellen. Notieren Sie sich Ihre Kennwörter, um solche Situationen zu vermeiden.

### Ist Aspose.Slides für Java mit den neuesten PowerPoint-Dateiformaten kompatibel?

Ja, Aspose.Slides für Java unterstützt die neuesten PowerPoint-Dateiformate, einschließlich PPTX-Dateien.