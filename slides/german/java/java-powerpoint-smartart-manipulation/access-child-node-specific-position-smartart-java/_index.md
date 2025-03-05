---
title: Zugriff auf untergeordneten Knoten an bestimmter Position in SmartArt
linktitle: Zugriff auf untergeordneten Knoten an bestimmter Position in SmartArt
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Lernen Sie mit dieser ausführlichen Anleitung, SmartArt in Aspose.Slides für Java zu bearbeiten. Schritt-für-Schritt-Anleitungen, Beispiele und bewährte Methoden inklusive.
type: docs
weight: 11
url: /de/java/java-powerpoint-smartart-manipulation/access-child-node-specific-position-smartart-java/
---
## Einführung
Möchten Sie Ihre Präsentationen mit anspruchsvollen SmartArt-Grafiken auf die nächste Stufe heben? Suchen Sie nicht weiter! Aspose.Slides für Java bietet eine leistungsstarke Suite zum Erstellen, Bearbeiten und Verwalten von Präsentationsfolien, einschließlich der Möglichkeit, mit SmartArt-Objekten zu arbeiten. In diesem umfassenden Tutorial führen wir Sie durch den Zugriff auf und die Bearbeitung eines untergeordneten Knotens an einer bestimmten Position innerhalb einer SmartArt-Grafik mithilfe der Aspose.Slides für Java-Bibliothek.

## Voraussetzungen
Bevor wir beginnen, müssen einige Voraussetzungen erfüllt sein:
1.  Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem Computer installiert ist. Sie können es von der[Oracle JDK-Seite](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides für Java-Bibliothek: Laden Sie die Aspose.Slides für Java-Bibliothek herunter von der[Download-Seite](https://releases.aspose.com/slides/java/).
3. Integrierte Entwicklungsumgebung (IDE): Verwenden Sie eine beliebige Java-IDE Ihrer Wahl. Beliebte Optionen sind IntelliJ IDEA, Eclipse oder NetBeans.
4.  Aspose-Lizenz: Sie können zwar mit einer kostenlosen Testversion beginnen, für den vollen Funktionsumfang sollten Sie jedoch eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) oder den Kauf einer Volllizenz bei[Hier](https://purchase.aspose.com/buy).
## Pakete importieren
Importieren wir zunächst die erforderlichen Pakete in Ihr Java-Projekt. Dies ist für die Verwendung der Aspose.Slides-Funktionen von entscheidender Bedeutung.
```java
import com.aspose.slides.*;
import java.io.File;
```
Lassen Sie uns das Beispiel nun in einzelne Schritte aufschlüsseln:
## Schritt 1: Erstellen Sie das Verzeichnis
Der erste Schritt besteht darin, das Verzeichnis einzurichten, in dem Ihre Präsentationsdateien gespeichert werden. Dadurch wird sichergestellt, dass Ihre Anwendung über einen ausgewiesenen Speicherplatz für die Dateiverwaltung verfügt.
```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
// Erstellen Sie ein Verzeichnis, falls es noch nicht vorhanden ist.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Hier prüfen wir, ob das Verzeichnis existiert, und wenn nicht, erstellen wir es. Dies ist eine gängige bewährte Vorgehensweise, um Fehler bei der Dateiverarbeitung zu vermeiden.
## Schritt 2: Instanziieren der Präsentation

Als Nächstes erstellen wir eine neue Präsentationsinstanz. Dies ist das Rückgrat unseres Projekts, in das alle Folien und Formen eingefügt werden.
```java
//Instanziieren der Präsentation
Presentation pres = new Presentation();
```
Diese Codezeile initialisiert ein neues Präsentationsobjekt mit Aspose.Slides.
## Schritt 3: Zugriff auf die erste Folie

Jetzt müssen wir auf die erste Folie der Präsentation zugreifen. Auf den Folien befindet sich der gesamte Inhalt der Präsentation.
```java
// Zugriff auf die erste Folie
ISlide slide = pres.getSlides().get_Item(0);
```
Dadurch wird auf die erste Folie der Präsentation zugegriffen, und wir können ihr Inhalt hinzufügen.
## Schritt 4: SmartArt-Form hinzufügen
### Hinzufügen einer SmartArt-Form
Als Nächstes fügen wir der Folie eine SmartArt-Form hinzu. SmartArt ist eine großartige Möglichkeit, Informationen visuell darzustellen.
```java
// Hinzufügen der SmartArt-Form zur ersten Folie
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
 Hier geben wir die Position und Abmessungen der SmartArt-Form an und wählen einen Layouttyp aus, in diesem Fall`StackedList`.
## Schritt 5: Auf SmartArt-Knoten zugreifen

Nun greifen wir auf einen bestimmten Knoten innerhalb der SmartArt-Grafik zu. Knoten sind einzelne Elemente innerhalb einer SmartArt-Form.
```java
// Zugriff auf den SmartArt-Knoten bei Index 0
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Dadurch wird der erste Knoten in der SmartArt-Grafik abgerufen, den wir weiter bearbeiten werden.
## Schritt 6: Auf untergeordneten Knoten zugreifen

In diesem Schritt greifen wir auf einen untergeordneten Knoten an einer bestimmten Position innerhalb des übergeordneten Knotens zu.
```java
// Zugriff auf den untergeordneten Knoten an Position 1 im übergeordneten Knoten
int position = 1;
SmartArtNode chNode = (SmartArtNode) node.getChildNodes().get_Item(position);
```
Dadurch wird der untergeordnete Knoten an der angegebenen Position abgerufen, sodass wir seine Eigenschaften bearbeiten können.
## Schritt 7: Parameter des untergeordneten Knotens drucken

Drucken wir abschließend die Parameter des untergeordneten Knotens aus, um unsere Manipulationen zu überprüfen.
```java
// Drucken der Parameter des untergeordneten SmartArt-Knotens
String outString = String.format("j = {0},.Text{1},  Level = {2}, Position = {3}", position, chNode.getTextFrame().getText(), chNode.getLevel(), chNode.getPosition());
System.out.println(outString);
```
Diese Codezeile formatiert und druckt die Details des untergeordneten Knotens, beispielsweise seinen Text, seine Ebene und seine Position.
## Abschluss
Herzlichen Glückwunsch! Sie haben erfolgreich auf einen untergeordneten Knoten in einer SmartArt-Grafik zugegriffen und ihn mithilfe von Aspose.Slides für Java bearbeitet. Diese Anleitung hat Sie Schritt für Schritt durch die Einrichtung Ihres Projekts, das Hinzufügen von SmartArt und die Bearbeitung seiner Knoten geführt. Mit diesem Wissen können Sie jetzt dynamischere und optisch ansprechendere Präsentationen erstellen.
 Weitere Informationen und Informationen zu erweiterten Funktionen finden Sie im[Aspose.Slides für Java-Dokumentation](https://reference.aspose.com/slides/java/)Wenn Sie Fragen haben oder Unterstützung benötigen,[Aspose-Community-Forum](https://forum.aspose.com/c/slides/11) ist eine großartige Anlaufstelle, um Hilfe zu suchen.
## Häufig gestellte Fragen
### Wie kann ich Aspose.Slides für Java installieren?
 Sie können es herunterladen von der[Download-Seite](https://releases.aspose.com/slides/java/) und befolgen Sie die bereitgestellten Installationsanweisungen.
### Kann ich Aspose.Slides für Java vor dem Kauf ausprobieren?
 Ja, Sie können eine[Kostenlose Testphase](https://releases.aspose.com/) oder ein[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) um die Funktionen zu testen.
### Welche Arten von SmartArt-Layouts sind in Aspose.Slides verfügbar?
 Aspose.Slides unterstützt verschiedene SmartArt-Layouts wie Liste, Prozess, Zyklus, Hierarchie und mehr. Detaillierte Informationen finden Sie im[Dokumentation](https://reference.aspose.com/slides/java/).
### Wie erhalte ich Unterstützung für Aspose.Slides für Java?
 Unterstützung erhalten Sie vom[Aspose-Community-Forum](https://forum.aspose.com/c/slides/11) oder lesen Sie die umfangreichen[Dokumentation](https://reference.aspose.com/slides/java/).
### Kann ich eine Volllizenz für Aspose.Slides für Java kaufen?
 Ja, Sie können eine Volllizenz erwerben bei[Kaufseite](https://purchase.aspose.com/buy).