---
title: Zugriff auf Layoutformate in Java-Folien
linktitle: Zugriff auf Layoutformate in Java-Folien
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java auf Layoutformate in Java Slides zugreifen und diese bearbeiten. Passen Sie Formen und Linienstile in PowerPoint-Präsentationen mühelos an.
weight: 10
url: /de/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zugriff auf Layoutformate in Java-Folien


## Einführung in Access-Layoutformate in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API auf Layoutformate in Java Slides zugreifen und mit ihnen arbeiten können. Mit Layoutformaten können Sie das Erscheinungsbild von Formen und Linien in den Layoutfolien einer Präsentation steuern. Wir zeigen Ihnen, wie Sie Füllformate und Linienformate für Formen auf Layoutfolien abrufen.

## Voraussetzungen

1. Aspose.Slides für die Java-Bibliothek.
2. Eine PowerPoint-Präsentation (PPTX-Format) mit Layoutfolien.

## Schritt 1: Laden Sie die Präsentation

 Zuerst müssen wir die PowerPoint-Präsentation laden, die die Layoutfolien enthält. Ersetzen Sie`"Your Document Directory"` durch den tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Schritt 2: Zugriff auf Layoutformate

Lassen Sie uns nun alle Layoutfolien in der Präsentation durchlaufen und auf die Füllformate und Linienformate der Formen auf jeder Layoutfolie zugreifen.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Zugriff auf Füllformate von Formen
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Zugriff auf Linienformate von Formen
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

Im obigen Code:

- Wir durchlaufen jede Layoutfolie mit einem`for` Schleife.
- Für jede Layoutfolie erstellen wir Arrays zum Speichern von Füllformaten und Linienformaten für die Formen auf dieser Folie.
-  Wir verwenden verschachtelte`for` Schleifen, um die Formen auf der Layoutfolie zu durchlaufen und ihre Füll- und Linienformate abzurufen.

## Schritt 3: Mit Layoutformaten arbeiten

Nachdem wir nun auf die Füllformate und Linienformate für Formen auf Layoutfolien zugegriffen haben, können Sie bei Bedarf verschiedene Vorgänge damit ausführen. Sie können beispielsweise die Füllfarbe, den Linienstil oder andere Eigenschaften von Formen ändern.

## Vollständiger Quellcode für Access-Layoutformate in Java-Folien

```java
// Der Pfad zum Dokumentverzeichnis.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mithilfe der Aspose.Slides für Java-API auf Layoutformate in Java-Folien zugreifen und diese bearbeiten können. Layoutformate sind wichtig, um das Erscheinungsbild von Formen und Linien in Layoutfolien in PowerPoint-Präsentationen zu steuern.

## Häufig gestellte Fragen

### Wie ändere ich die Füllfarbe einer Form?

 Um die Füllfarbe einer Form zu ändern, können Sie das`IFillFormat`Methoden des Objekts. Hier ist ein Beispiel:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Fülltyp auf Volltonfarbe einstellen
fillFormat.getSolidFillColor().setColor(Color.RED); // Stellen Sie die Füllfarbe auf Rot ein
```

### Wie ändere ich den Linienstil einer Form?

 Um den Linienstil einer Form zu ändern, können Sie das`ILineFormat`Methoden des Objekts. Hier ist ein Beispiel:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Stellen Sie den Linienstil auf „Einzeln“ ein.
lineFormat.setWidth(2.0); // Stellen Sie die Linienbreite auf 2,0 Punkte ein.
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Stellen Sie die Linienfarbe auf Blau ein
```

### Wie wende ich diese Änderungen auf eine Form auf einer Layoutfolie an?

Um diese Änderungen auf eine bestimmte Form auf einer Layoutfolie anzuwenden, können Sie über ihren Index in der Formensammlung der Layoutfolie auf die Form zugreifen. Beispiel:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Greifen Sie auf die erste Form auf der Layoutfolie zu
```

 Sie können dann mit dem`IFillFormat` Und`ILineFormat` Methoden wie in den vorherigen Antworten gezeigt, um die Füll- und Linienformate der Form zu ändern.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
