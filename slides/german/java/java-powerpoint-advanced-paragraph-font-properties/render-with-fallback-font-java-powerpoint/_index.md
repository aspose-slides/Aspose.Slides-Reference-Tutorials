---
title: Rendern mit Ersatzschriftart in Java PowerPoint
linktitle: Rendern mit Ersatzschriftart in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides Text mit Ersatzschriftarten in Java PowerPoint-Präsentationen rendern. Folgen Sie dieser Schritt-für-Schritt-Anleitung für eine nahtlose Implementierung.
weight: 13
url: /de/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Einführung
Das Erstellen und Bearbeiten von PowerPoint-Präsentationen in Java kann eine Herausforderung sein, aber mit Aspose.Slides können Sie dies effizient tun. Eine wichtige Funktion ist die Möglichkeit, Text mit Ersatzschriftarten darzustellen. Dieser Artikel bietet eine detaillierte Schritt-für-Schritt-Anleitung zum Implementieren von Ersatzschriftarten in Ihren PowerPoint-Folien mit Aspose.Slides für Java.
## Voraussetzungen
Bevor wir mit der Implementierung beginnen, stellen wir sicher, dass Sie alles haben, was Sie brauchen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Slides für Java: Sie können es herunterladen von der[Aspose.Slides für Java Download-Seite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Eine IDE wie IntelliJ IDEA oder Eclipse vereinfacht Ihren Entwicklungsprozess.
4. Abhängigkeiten: Fügen Sie Aspose.Slides in die Abhängigkeiten Ihres Projekts ein.
## Pakete importieren
Zuerst müssen wir die erforderlichen Pakete in unser Java-Programm importieren.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Lassen Sie uns den Prozess in überschaubare Schritte unterteilen.
## Schritt 1: Richten Sie Ihr Projekt ein
 Bevor Sie Code schreiben, stellen Sie sicher, dass Ihr Projekt richtig eingerichtet ist. Dazu gehört das Hinzufügen der Aspose.Slides-Bibliothek zu Ihrem Projekt. Sie können dies tun, indem Sie die Bibliothek von herunterladen[Aspose.Slides für Java](https://releases.aspose.com/slides/java/) und fügen Sie es Ihrem Build-Pfad hinzu.
## Schritt 2: Initialisieren der Font-Fallback-Regeln
 Sie müssen eine Instanz des`IFontFallBackRulesCollection` Klasse und fügen Sie ihr Regeln hinzu. Diese Regeln definieren die Schriftart-Fallbacks für bestimmte Unicode-Bereiche.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen einer neuen Instanz einer Regelsammlung
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Erstellen Sie eine Reihe von Regeln
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Schritt 3: Fallback-Regeln ändern
In diesem Schritt ändern wir die Fallback-Regeln, indem wir vorhandene Fallback-Schriftarten entfernen und die Regeln für bestimmte Unicode-Bereiche aktualisieren.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Versuch, die FallBack-Schriftart „Tahoma“ aus geladenen Regeln zu entfernen
    fallBackRule.remove("Tahoma");
    // Updateregeln für den angegebenen Bereich
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Entfernen Sie alle vorhandenen Regeln aus der Liste.
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Schritt 4: Laden Sie die Präsentation
Laden Sie die PowerPoint-Präsentation, die Sie ändern möchten.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Schritt 5: Der Präsentation Fallback-Regeln zuweisen
Weisen Sie dem Font-Manager der Präsentation die vorbereiteten Fallback-Regeln zu.
```java
try {
    // Zuweisen der vorbereiteten Regelliste zur Verwendung
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Rendern eines Miniaturbilds unter Verwendung der initialisierten Regelsammlung und Speichern im PNG-Format
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Schritt 6: Speichern und testen
Speichern Sie abschließend Ihre Arbeit und testen Sie die Implementierung, um sicherzustellen, dass alles wie erwartet funktioniert. Wenn Sie auf Probleme stoßen, überprüfen Sie Ihr Setup noch einmal und stellen Sie sicher, dass alle Abhängigkeiten korrekt hinzugefügt wurden.
## Abschluss
Wenn Sie dieser Anleitung folgen, können Sie mit Aspose.Slides für Java Text in Ihren PowerPoint-Präsentationen effizient mit Ersatzschriftarten rendern. Dieser Prozess stellt sicher, dass Ihre Präsentationen eine einheitliche Formatierung beibehalten, auch wenn die primären Schriftarten nicht verfügbar sind. Viel Spaß beim Programmieren!
## Häufig gestellte Fragen
### Was ist Aspose.Slides für Java?
Aspose.Slides für Java ist eine Bibliothek, mit der Entwickler PowerPoint-Präsentationen in Java-Anwendungen erstellen, ändern und rendern können.
### Wie füge ich Aspose.Slides zu meinem Projekt hinzu?
 Sie können die Bibliothek herunterladen von der[Aspose.Slides-Downloadseite](https://releases.aspose.com/slides/java/) und fügen Sie es dem Build-Pfad Ihres Projekts hinzu.
### Was sind Fallback-Schriftarten?
Fallback-Schriftarten sind alternative Schriftarten, die verwendet werden, wenn die angegebene Schriftart nicht verfügbar ist oder bestimmte Zeichen nicht unterstützt.
### Kann ich mehrere Fallback-Regeln verwenden?
Ja, Sie können mehrere Fallback-Regeln hinzufügen, um verschiedene Unicode-Bereiche und Schriftarten zu verarbeiten.
### Wo erhalte ich Support für Aspose.Slides?
 Unterstützung erhalten Sie vom[Aspose.Slides Support-Forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
