---
"description": "Dowiedz się, jak wyodrębnić filmy ze slajdów programu PowerPoint za pomocą Aspose.Slides dla .NET. Ten przewodnik krok po kroku uprości Ci ten proces."
"linktitle": "Wyodrębnij wideo ze slajdu"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Jak wyodrębnić wideo ze slajdu za pomocą Aspose.Slides dla .NET"
"url": "/pl/net/audio-and-video-extraction/extract-video/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jak wyodrębnić wideo ze slajdu za pomocą Aspose.Slides dla .NET


Aspose.Slides for .NET to potężna biblioteka, która umożliwia pracę z prezentacjami PowerPoint w środowisku .NET. Jedną z przydatnych funkcji, jakie oferuje, jest możliwość wyodrębniania filmów ze slajdów. W tym przewodniku krok po kroku pokażemy, jak wyodrębnić film ze slajdu PowerPoint za pomocą Aspose.Slides for .NET.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

- Aspose.Slides dla .NET: Musisz mieć zainstalowany Aspose.Slides dla .NET. Możesz go pobrać ze strony [strona internetowa](https://purchase.aspose.com/buy).

- Prezentacja programu PowerPoint: Przygotuj prezentację programu PowerPoint (np. Video.pptx) zawierającą film, który chcesz wyodrębnić.

## Importuj przestrzenie nazw

Musisz zaimportować niezbędne przestrzenie nazw, aby pracować z Aspose.Slides dla .NET. Oto, jak możesz to zrobić:

```csharp
using Aspose.Slides;
using Aspose.Slides.Video;
```

Teraz podzielimy proces wyodrębniania filmu ze slajdu na kilka kroków.

## Krok 1: Ustaw katalog dokumentów

```csharp
string dataDir = "Your Document Directory";
```

Zastępować `"Your Document Directory"` ze ścieżką do katalogu, w którym znajduje się prezentacja PowerPoint.

## Krok 2: Załaduj prezentację

```csharp
Presentation presentation = new Presentation(dataDir + "Video.pptx");
```

Ten kod inicjuje obiekt Presentation, reprezentujący plik prezentacji programu PowerPoint.

## Krok 3: Przejrzyj slajdy i kształty

```csharp
foreach (ISlide slide in presentation.Slides)
{
    foreach (IShape shape in presentation.Slides[0].Shapes)
    {
```

Tutaj przechodzimy przez każdy slajd prezentacji, a następnie powtarzamy kształty na pierwszym slajdzie (modyfikujemy w razie potrzeby).

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

Kod ten wyodrębnia informacje o filmie, w tym jego typ zawartości i dane binarne.

## Krok 6: Zapisz wideo

```csharp
using (FileStream stream = new FileStream(dataDir + "NewVideo_out." + type, FileMode.Create, FileAccess.Write, FileShare.Read))
{
    stream.Write(buffer, 0, buffer.Length);
}
```

Na koniec ten krok powoduje zapisanie filmu w nowym pliku w określonym katalogu.

Po wykonaniu tych kroków uda Ci się wyodrębnić wideo ze slajdu programu PowerPoint za pomocą Aspose.Slides dla platformy .NET.

## Wniosek

Aspose.Slides for .NET upraszcza proces pracy z prezentacjami PowerPoint, umożliwiając łatwe wykonywanie zadań, takich jak wyodrębnianie filmów ze slajdów. Postępując zgodnie z tym przewodnikiem krok po kroku i korzystając z biblioteki Aspose.Slides, możesz ulepszyć swoje aplikacje .NET o potężne funkcje PowerPoint.

## Często zadawane pytania (FAQ)

### Czym jest Aspose.Slides dla .NET?
Aspose.Slides for .NET to biblioteka umożliwiająca aplikacjom .NET pracę z prezentacjami PowerPoint, w tym tworzenie, edycję i wyodrębnianie treści.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
Dokumentację można znaleźć [Tutaj](https://reference.aspose.com/slides/net/).

### Czy Aspose.Slides dla platformy .NET jest dostępny w ramach bezpłatnej wersji próbnej?
Tak, możesz otrzymać bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).

### W jaki sposób mogę uzyskać tymczasową licencję na Aspose.Slides dla platformy .NET?
Możesz poprosić o tymczasową licencję [ten link](https://purchase.aspose.com/temporary-license/).

### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?
Wsparcie znajdziesz na [Forum Aspose.Slides](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}