---
title: Greifen Sie auf Layoutformate in Java-Folien zu
linktitle: Greifen Sie auf Layoutformate in Java-Folien zu
second_title: Aspose.Slides Java PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für Java auf Layoutformate in Java Slides zugreifen und diese bearbeiten. Passen Sie Formen und Linienstile mühelos in PowerPoint-Präsentationen an.
type: docs
weight: 10
url: /de/java/presentation-properties/access-layout-formats-in-java-slides/
---

## Einführung in Access-Layoutformate in Java-Folien

In diesem Tutorial erfahren Sie, wie Sie mithilfe der Aspose.Slides für Java-API auf Layoutformate in Java Slides zugreifen und mit ihnen arbeiten. Mithilfe von Layoutformaten können Sie das Erscheinungsbild von Formen und Linien innerhalb der Layoutfolien einer Präsentation steuern. Wir behandeln, wie Sie Füllformate und Linienformate für Formen auf Layoutfolien abrufen.

## Voraussetzungen

1. Aspose.Slides für Java-Bibliothek.
2. Eine PowerPoint-Präsentation (PPTX-Format) mit Layout-Folien.

## Schritt 1: Laden Sie die Präsentation

 Zuerst müssen wir die PowerPoint-Präsentation laden, die die Layout-Folien enthält. Ersetzen`"Your Document Directory"` mit dem tatsächlichen Pfad zu Ihrem Dokumentverzeichnis.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Schritt 2: Auf Layoutformate zugreifen

Lassen Sie uns nun die Layoutfolien in der Präsentation durchlaufen und auf die Füllformate und Linienformate der Formen auf jeder Layoutfolie zugreifen.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Greifen Sie auf Füllformate von Formen zu
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Greifen Sie auf Linienformate von Formen zu
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

Im Code oben:

- Wir durchlaufen jede Layoutfolie mit a`for` Schleife.
- Für jede Layoutfolie erstellen wir Arrays, um Füllformate und Linienformate für die Formen auf dieser Folie zu speichern.
-  Wir verwenden verschachtelt`for` Schleifen, um die Formen auf der Layoutfolie zu durchlaufen und deren Füll- und Linienformate abzurufen.

## Schritt 3: Arbeiten Sie mit Layoutformaten

Nachdem wir nun auf die Füllformate und Linienformate für Formen auf Layoutfolien zugegriffen haben, können Sie bei Bedarf verschiedene Vorgänge daran durchführen. Sie können beispielsweise die Füllfarbe, den Linienstil oder andere Eigenschaften von Formen ändern.

## Vollständiger Quellcode für Access-Layoutformate in Java-Folien

```java
// Der Pfad zum Dokumentenverzeichnis.
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

In diesem Tutorial haben wir untersucht, wie Sie mithilfe der Aspose.Slides für Java-API auf Layoutformate in Java Slides zugreifen und diese bearbeiten. Layoutformate sind wichtig, um das Erscheinungsbild von Formen und Linien in Layoutfolien in PowerPoint-Präsentationen zu steuern.

## FAQs

### Wie ändere ich die Füllfarbe einer Form?

 Um die Füllfarbe einer Form zu ändern, können Sie die verwenden`IFillFormat`Methoden des Objekts. Hier ist ein Beispiel:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Stellen Sie den Fülltyp auf Volltonfarbe ein
fillFormat.getSolidFillColor().setColor(Color.RED); // Stellen Sie die Füllfarbe auf Rot ein
```

### Wie ändere ich den Linienstil einer Form?

 Um den Linienstil einer Form zu ändern, können Sie die verwenden`ILineFormat`Methoden des Objekts. Hier ist ein Beispiel:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Stellen Sie den Linienstil auf „Einfach“ ein
lineFormat.setWidth(2.0); // Stellen Sie die Linienstärke auf 2,0 Punkte ein
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Stellen Sie die Linienfarbe auf Blau ein
```

### Wie wende ich diese Änderungen auf eine Form auf einer Layoutfolie an?

Um diese Änderungen auf eine bestimmte Form auf einer Layoutfolie anzuwenden, können Sie über ihren Index in der Formensammlung der Layoutfolie auf die Form zugreifen. Zum Beispiel:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Greifen Sie auf die erste Form auf der Layoutfolie zu
```

 Anschließend können Sie die verwenden`IFillFormat` Und`ILineFormat` Methoden wie in den vorherigen Antworten gezeigt, um die Füll- und Linienformate der Form zu ändern.