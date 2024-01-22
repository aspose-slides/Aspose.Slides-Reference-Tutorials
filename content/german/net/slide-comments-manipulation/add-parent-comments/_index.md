---
title: Fügen Sie mit Aspose.Slides übergeordnete Kommentare zur Folie hinzu
linktitle: Fügen Sie Elternkommentare zur Folie hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET interaktive Kommentare und Antworten zu Ihren PowerPoint-Präsentationen hinzufügen. Verbessern Sie Engagement und Zusammenarbeit.
type: docs
weight: 12
url: /de/net/slide-comments-manipulation/add-parent-comments/
---

Möchten Sie Ihre PowerPoint-Präsentationen mit interaktiven Funktionen erweitern? Mit Aspose.Slides für .NET können Sie Kommentare und Antworten integrieren und so ein dynamisches und ansprechendes Erlebnis für Ihr Publikum schaffen. In dieser Schritt-für-Schritt-Anleitung zeigen wir Ihnen, wie Sie mit Aspose.Slides für .NET übergeordnete Kommentare zu Folien hinzufügen. Lassen Sie uns eintauchen und diese aufregende Funktion erkunden.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:

1.  Aspose.Slides für .NET: Stellen Sie sicher, dass Aspose.Slides für .NET installiert ist. Sie können es herunterladen[Hier](https://releases.aspose.com/slides/net/).

2. Visual Studio: Sie benötigen Visual Studio, um Ihre .NET-Anwendung zu erstellen und auszuführen.

3. Grundkenntnisse in C#: In diesem Tutorial wird davon ausgegangen, dass Sie über grundlegende Kenntnisse der C#-Programmierung verfügen.

Nachdem wir nun die Voraussetzungen erfüllt haben, fahren wir mit dem Import der erforderlichen Namespaces fort.

## Namensräume importieren

Zunächst müssen Sie die relevanten Namespaces in Ihr Projekt importieren. Diese Namespaces stellen die Klassen und Methoden bereit, die für die Arbeit mit Aspose.Slides für .NET erforderlich sind.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Nachdem die Voraussetzungen und Namespaces vorhanden sind, unterteilen wir den Prozess zum Hinzufügen übergeordneter Kommentare zu einer Folie in mehrere Schritte.

## Schritt 1: Erstellen Sie eine Präsentation

Um zu beginnen, müssen Sie eine neue Präsentation mit Aspose.Slides für .NET erstellen. Diese Präsentation dient als Leinwand, auf der Sie Ihre Kommentare hinzufügen.

```csharp
// Der Pfad zum Ausgabeverzeichnis.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Hier finden Sie Ihren Code zum Hinzufügen von Kommentaren.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 Ersetzen Sie im obigen Code`"Output Path"` mit dem gewünschten Pfad für Ihre Ausgabepräsentation.

## Schritt 2: Kommentarautoren hinzufügen

Bevor Sie Kommentare hinzufügen, müssen Sie die Autoren dieser Kommentare definieren. In diesem Beispiel haben wir zwei Autoren, „Autor_1“ und „Autor_2“, die jeweils durch eine Instanz von dargestellt werden`ICommentAuthor`.

```csharp
// Einen Kommentar hinzufügen
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Antwort für Kommentar1 hinzufügen
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

In diesem Schritt erstellen wir zwei Kommentarautoren und fügen den ersten Kommentar und eine Antwort auf den Kommentar hinzu.

## Schritt 3: Weitere Antworten hinzufügen

Um eine hierarchische Struktur von Kommentaren zu erstellen, können Sie weitere Antworten zu vorhandenen Kommentaren hinzufügen. Hier fügen wir eine zweite Antwort auf „comment1“ hinzu.

```csharp
// Antwort für Kommentar1 hinzufügen
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Dadurch entsteht ein Gesprächsfluss innerhalb Ihrer Präsentation.

## Schritt 4: Verschachtelte Antworten hinzufügen

Kommentare können auch verschachtelte Antworten enthalten. Um dies zu demonstrieren, fügen wir eine Antwort auf „Antwort 2 für Kommentar 1“ hinzu und erstellen so eine Unterantwort.

```csharp
// Antwort zur Antwort hinzufügen
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Dieser Schritt unterstreicht die Vielseitigkeit von Aspose.Slides für .NET bei der Verwaltung von Kommentarhierarchien.

## Schritt 5: Weitere Kommentare und Antworten

Sie können bei Bedarf weitere Kommentare und Antworten hinzufügen. In diesem Beispiel fügen wir zwei weitere Kommentare und eine Antwort auf einen davon hinzu.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Dieser Schritt zeigt, wie Sie ansprechende und interaktive Inhalte für Ihre Präsentationen erstellen können.

## Schritt 6: Zeigen Sie die Hierarchie an

Um die Kommentarhierarchie zu visualisieren, können Sie sie auf der Konsole anzeigen. Dieser Schritt ist optional, kann aber beim Debuggen und Verständnis der Struktur hilfreich sein.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## Schritt 7: Kommentare entfernen

In einigen Fällen müssen Sie möglicherweise Kommentare und deren Antworten entfernen. Der folgende Codeausschnitt zeigt, wie „comment1“ und alle seine Antworten entfernt werden.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Dieser Schritt ist nützlich für die Verwaltung und Aktualisierung Ihrer Präsentationsinhalte.

Mit diesen Schritten können Sie mit Aspose.Slides für .NET Präsentationen mit interaktiven Kommentaren und Antworten erstellen. Unabhängig davon, ob Sie Ihr Publikum einbeziehen oder mit Teammitgliedern zusammenarbeiten möchten, bietet diese Funktion eine Vielzahl von Möglichkeiten.

## Abschluss

Aspose.Slides für .NET bietet leistungsstarke Tools zur Verbesserung Ihrer PowerPoint-Präsentationen. Mit der Möglichkeit, Kommentare und Antworten hinzuzufügen, können Sie dynamische und interaktive Inhalte erstellen, die Ihr Publikum fesseln. Diese Schritt-für-Schritt-Anleitung hat Ihnen gezeigt, wie Sie übergeordnete Kommentare zu Folien hinzufügen, Hierarchien einrichten und bei Bedarf sogar Kommentare entfernen. Indem Sie diese Schritte befolgen und die Aspose.Slides-Dokumentation erkunden[Hier](https://reference.aspose.com/slides/net/)können Sie Ihre Präsentationen auf die nächste Stufe heben.

## FAQs

### Kann ich Kommentare zu bestimmten Folien in meiner Präsentation hinzufügen?
Ja, Sie können jeder Folie Ihrer Präsentation Kommentare hinzufügen, indem Sie beim Erstellen eines Kommentars die Zielfolie angeben.

### Ist es möglich, das Erscheinungsbild von Kommentaren in der Präsentation anzupassen?
Mit Aspose.Slides für .NET können Sie das Erscheinungsbild von Kommentaren anpassen, einschließlich Text, Autoreninformationen und Position auf der Folie.

### Kann ich die Kommentare und Antworten in eine separate Datei exportieren?
Ja, Sie können Kommentare und Antworten in eine separate Präsentationsdatei exportieren, wie in Schritt 7 gezeigt.

### Ist Aspose.Slides für .NET mit den neuesten Versionen von PowerPoint kompatibel?
Aspose.Slides für .NET ist für die Zusammenarbeit mit einer Vielzahl von PowerPoint-Versionen konzipiert und gewährleistet die Kompatibilität mit den neuesten Versionen.

### Gibt es Lizenzoptionen für Aspose.Slides für .NET?
 Ja, Sie können Lizenzoptionen, einschließlich temporärer Lizenzen, auf der Aspose-Website erkunden[Hier](https://purchase.aspose.com/buy) oder probieren Sie die kostenlose Testversion aus[Hier](https://releases.aspose.com/temporary-license/).