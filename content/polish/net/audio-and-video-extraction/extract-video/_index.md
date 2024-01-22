---
title: Jak wyodrębnić wideo ze slajdu za pomocą Aspose.Slides dla .NET
linktitle: Wyodrębnij wideo ze slajdu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak wyodrębniać filmy ze slajdów programu PowerPoint za pomocą Aspose.Slides dla .NET. Ten przewodnik krok po kroku uprości Ci ten proces.
type: docs
weight: 14
url: /pl/net/audio-and-video-extraction/extract-video/
---

Aspose.Slides dla .NET to potężna biblioteka, która umożliwia pracę z prezentacjami programu PowerPoint w środowisku .NET. Jedną z przydatnych funkcji, jakie zapewnia, jest możliwość wyodrębniania filmów ze slajdów. W tym przewodniku krok po kroku pokażemy, jak wyodrębnić wideo ze slajdu programu PowerPoint za pomocą Aspose.Slides dla .NET.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Slides dla .NET: Musisz mieć zainstalowany Aspose.Slides dla .NET. Można go uzyskać od[strona internetowa](https://purchase.aspose.com/buy).

- Prezentacja programu PowerPoint: Przygotuj prezentację programu PowerPoint (np. Video.pptx) zawierającą wideo, które chcesz wyodrębnić.

## Importuj przestrzenie nazw

Aby pracować z Aspose.Slides dla .NET, musisz zaimportować niezbędne przestrzenie nazw. Oto jak możesz to zrobić:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Podzielmy teraz proces wyodrębniania wideo ze slajdu na kilka etapów.

## Krok 1: Ustaw katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

 Zastępować`"Your Document Directory"` ze ścieżką do katalogu, w którym znajduje się prezentacja programu PowerPoint.

## Krok 2: Załaduj prezentację

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Ten kod inicjuje obiekt Prezentacja reprezentujący plik prezentacji programu PowerPoint.

## Krok 3: Przeglądaj slajdy i kształty

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

W tym miejscu przeglądamy każdy slajd prezentacji, a następnie przeglądamy kształty na pierwszym slajdzie (w razie potrzeby modyfikujemy).

## Krok 4: Sprawdź, czy kształt jest klatką wideo

```csharp
if (shape is VideoFrame)
{
    IVideoFrame vf = shape as IVideoFrame;
    String type = vf.EmbeddedVideo.ContentType;
```

Ten krok sprawdza, czy kształt na slajdzie jest klatką wideo.

## Krok 5: Wyodrębnij dane wideo

```csharp
int ss = type.LastIndexOf('/');
type = type.Remove(0, type.LastIndexOf('/') + 1);
Byte[] buffer = vf.EmbeddedVideo.BinaryData;
```

Ten kod wyodrębnia informacje o filmie, w tym jego typ zawartości i dane binarne.

## Krok 6: Zapisz wideo

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Na koniec ten krok zapisuje wideo w nowym pliku w określonym katalogu.

Po wykonaniu tych kroków pomyślnie wyodrębnisz wideo ze slajdu programu PowerPoint za pomocą Aspose.Slides dla .NET.

## Wniosek

Aspose.Slides dla .NET upraszcza proces pracy z prezentacjami programu PowerPoint, umożliwiając łatwe wykonywanie takich zadań, jak wyodrębnianie filmów ze slajdów. Postępując zgodnie z tym przewodnikiem krok po kroku i korzystając z biblioteki Aspose.Slides, możesz ulepszyć swoje aplikacje .NET za pomocą zaawansowanych funkcji programu PowerPoint.

## Często zadawane pytania (FAQ)

### Co to jest Aspose.Slides dla .NET?
Aspose.Slides dla .NET to biblioteka, która umożliwia aplikacjom .NET współpracę z prezentacjami programu PowerPoint, w tym tworzenie, edytowanie i wyodrębnianie zawartości.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
 Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/net/).

### Czy Aspose.Slides dla .NET jest dostępny w bezpłatnej wersji próbnej?
 Tak, możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).

### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla .NET?
 Możesz poprosić o licencję tymczasową od[ten link](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?
 Wsparcie znajdziesz na stronie[Forum Aspose.Slides](https://forum.aspose.com/).