---
title: Organisieren Sie den Diagrammlayouttyp in SmartArt mit Java
linktitle: Organisieren Sie den Diagrammlayouttyp in SmartArt mit Java
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Meistern Sie die Organisation von Diagrammlayouttypen in SmartArt mit Java und Aspose.Slides und verbessern Sie die visuelle Darstellung von Präsentationen mühelos.
weight: 13
url: /de/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Einführung
In diesem Tutorial gehen wir den Prozess der Organisation von Diagrammlayouttypen in SmartArt mit Java durch, wobei wir insbesondere die Aspose.Slides-Bibliothek nutzen. SmartArt in Präsentationen kann die visuelle Attraktivität und Klarheit Ihrer Daten erheblich verbessern, weshalb es wichtig ist, deren Bearbeitung zu beherrschen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Auf Ihrem System ist Java Development Kit (JDK) installiert.
2.  Aspose.Slides-Bibliothek heruntergeladen und eingerichtet. Falls noch nicht geschehen, laden Sie sie herunter von[Hier](https://releases.aspose.com/slides/java/).
3. Grundlegende Kenntnisse der Java-Programmierung.

## Pakete importieren
Importieren Sie zunächst die erforderlichen Pakete:
```java
import com.aspose.slides.*;
```
Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte aufteilen:
## Schritt 1: Präsentationsobjekt initialisieren
```java
Presentation presentation = new Presentation();
```
Erstellen Sie ein neues Präsentationsobjekt.
## Schritt 2: SmartArt zur Folie hinzufügen
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Fügen Sie der gewünschten Folie SmartArt mit den angegebenen Abmessungen und dem angegebenen Layouttyp hinzu.
## Schritt 3: Organigramm-Layout festlegen
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Legen Sie den Layouttyp des Organigramms fest. In diesem Beispiel verwenden wir das Layout „Links hängend“.
## Schritt 4: Präsentation speichern
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Speichern Sie die Präsentation mit dem übersichtlichen Diagrammlayout.

## Abschluss
Wenn Sie die Organisation von Diagrammlayouttypen in SmartArt mit Java beherrschen, können Sie mühelos visuell ansprechende Präsentationen erstellen. Mit Aspose.Slides wird der Prozess rationalisiert und effizient, sodass Sie sich auf die Erstellung wirkungsvoller Inhalte konzentrieren können.
## Häufig gestellte Fragen
### Ist Aspose.Slides mit verschiedenen Java-Entwicklungsumgebungen kompatibel?
Ja, Aspose.Slides ist mit verschiedenen Java-Entwicklungsumgebungen kompatibel und gewährleistet so Flexibilität für Entwickler.
### Kann ich das Erscheinungsbild von SmartArt-Elementen mit Aspose.Slides anpassen?
Absolut, Aspose.Slides bietet umfangreiche Anpassungsoptionen für SmartArt-Elemente, sodass Sie sie an Ihre spezifischen Anforderungen anpassen können.
### Bietet Aspose.Slides eine umfassende Dokumentation für Entwickler?
Ja, Entwickler können auf die ausführliche Dokumentation von Aspose.Slides für Java zurückgreifen, die Einblicke in die Funktionen und Verwendung bietet.
### Gibt es eine Testversion für Aspose.Slides?
Ja, Sie können auf eine kostenlose Testversion von Aspose.Slides zugreifen, um die Funktionen zu erkunden, bevor Sie eine Kaufentscheidung treffen.
### Wo kann ich Unterstützung bei Fragen zu Aspose.Slides erhalten?
 Für Hilfe oder Fragen zu Aspose.Slides können Sie das Support-Forum besuchen[Hier](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
