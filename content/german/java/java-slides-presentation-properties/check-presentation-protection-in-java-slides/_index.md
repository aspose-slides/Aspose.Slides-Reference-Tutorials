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

In diesem Tutorial erfahren Sie, wie Sie den Präsentationsschutz mit Aspose.Slides für Java überprüfen. Wir werden zwei Szenarien behandeln: die Prüfung des Schreibschutzes und die Prüfung des offenen Schutzes für eine Präsentation. Wir stellen Schritt-für-Schritt-Codebeispiele für jedes Szenario bereit.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die Aspose.Slides for Java-Bibliothek in Ihrem Java-Projekt eingerichtet ist. Sie können es von der Aspose-Website herunterladen und zu den Abhängigkeiten Ihres Projekts hinzufügen.

### Maven-Abhängigkeit

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Ersetzen`your_version_here` mit der Version von Aspose.Slides für Java, die Sie verwenden.

## Schritt 1: Überprüfen Sie den Schreibschutz

 Um zu überprüfen, ob eine Präsentation durch ein Passwort schreibgeschützt ist, können Sie das verwenden`IPresentationInfo` Schnittstelle. Hier ist der Code dafür:

```java
// Pfad für die Quellpräsentation
String pptxFile = "path_to_presentation.pptx";

// Überprüfen Sie das Schreibschutzkennwort über die IPresentationInfo-Schnittstelle
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Ersetzen`"path_to_presentation.pptx"` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei und`"password_here"` mit dem Schreibschutzpasswort.

## Schritt 2: Öffnen Sie den Schutz

 Um zu überprüfen, ob eine Präsentation zum Öffnen durch ein Passwort geschützt ist, können Sie das verwenden`IPresentationInfo` Schnittstelle. Hier ist der Code dafür:

```java
// Pfad für die Quellpräsentation
String pptFile = "path_to_presentation.ppt";

// Überprüfen Sie den Präsentations-Öffnungsschutz über die IPresentationInfo-Schnittstelle
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Ersetzen`"path_to_presentation.ppt"` mit dem tatsächlichen Pfad zu Ihrer Präsentationsdatei.

## Vollständiger Quellcode für den Scheckpräsentationsschutz in Java-Folien

```java
//Pfad zur Quellenpräsentation
String pptxFile = RunExamples.getDataDir_PresentationProperties() + "modify_pass2.pptx";
String pptFile = RunExamples.getDataDir_PresentationProperties() + "open_pass1.ppt";
// Überprüfen Sie das Schreibschutzkennwort über die IPresentationInfo-Schnittstelle
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
// Überprüfen Sie den Präsentations-Öffnungsschutz über die IPresentationInfo-Schnittstelle
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Slides für Java den Präsentationsschutz in Java-Folien überprüft. Wir haben zwei Szenarien abgedeckt: die Prüfung des Schreibschutzes und die Prüfung des offenen Schutzes. Sie können diese Prüfungen jetzt in Ihre Java-Anwendungen integrieren, um geschützte Präsentationen effektiv zu verwalten.

## FAQs

### Wie erhalte ich Aspose.Slides für Java?

Sie können Aspose.Slides für Java von der Aspose-Website herunterladen oder es als Maven-Abhängigkeit in Ihrem Projekt hinzufügen, wie im Abschnitt „Voraussetzungen“ gezeigt.

### Kann ich sowohl den Schreibschutz als auch den offenen Schutz für eine Präsentation überprüfen?

Ja, Sie können anhand der bereitgestellten Codebeispiele sowohl den Schreibschutz als auch den offenen Schutz für eine Präsentation überprüfen.

### Was soll ich tun, wenn ich das Schutzpasswort vergesse?

Wenn Sie das Schutzkennwort für eine Präsentation vergessen, gibt es keine integrierte Möglichkeit, es wiederherzustellen. Notieren Sie sich unbedingt Ihre Passwörter, um solche Situationen zu vermeiden.

### Ist Aspose.Slides für Java mit den neuesten PowerPoint-Dateiformaten kompatibel?

Ja, Aspose.Slides für Java unterstützt die neuesten PowerPoint-Dateiformate, einschließlich .pptx-Dateien.