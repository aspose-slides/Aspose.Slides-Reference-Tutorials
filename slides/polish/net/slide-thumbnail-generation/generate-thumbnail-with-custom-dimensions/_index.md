---
"description": "Dowiedz się, jak generować niestandardowe obrazy miniatur z prezentacji PowerPoint przy użyciu Aspose.Slides dla .NET. Ulepsz wrażenia użytkownika i funkcjonalność."
"linktitle": "Generuj miniaturę z niestandardowymi wymiarami"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Generuj miniatury w slajdach z niestandardowymi wymiarami"
"url": "/pl/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generuj miniatury w slajdach z niestandardowymi wymiarami


Tworzenie niestandardowych miniatur prezentacji PowerPoint może być cennym atutem, niezależnie od tego, czy tworzysz interaktywną aplikację, ulepszasz doświadczenie użytkownika, czy optymalizujesz zawartość dla różnych platform. W tym samouczku przeprowadzimy Cię przez proces generowania niestandardowych miniatur prezentacji PowerPoint przy użyciu biblioteki Aspose.Slides for .NET. Ta potężna biblioteka umożliwia programowe manipulowanie, konwertowanie i ulepszanie plików PowerPoint w aplikacjach .NET.

## Wymagania wstępne

Zanim przejdziemy do generowania niestandardowych miniatur, upewnij się, że spełnione są następujące wymagania wstępne:

### 1. Aspose.Slides dla .NET

Musisz mieć zainstalowaną bibliotekę Aspose.Slides for .NET w swoim projekcie. Jeśli jeszcze tego nie zrobiłeś, możesz znaleźć potrzebną dokumentację i linki do pobrania [Tutaj](https://reference.aspose.com/slides/net/).

### 2. Prezentacja PowerPoint

Upewnij się, że masz prezentację PowerPoint, z której chcesz wygenerować niestandardowy obraz miniatury. Ta prezentacja powinna być dostępna w katalogu projektu.

### 3. Środowisko programistyczne

Aby móc skorzystać z tego samouczka, musisz mieć praktyczną znajomość programowania .NET za pomocą języka C# i posiadać skonfigurowane środowisko programistyczne, np. Visual Studio.

Teraz, gdy omówiliśmy już wymagania wstępne, możemy przedstawić proces generowania niestandardowych miniatur w postaci instrukcji krok po kroku.

## Importuj przestrzenie nazw

Najpierw musisz uwzględnić wymagane przestrzenie nazw w kodzie C#. Te przestrzenie nazw umożliwiają pracę z Aspose.Slides i manipulowanie prezentacjami PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 1: Załaduj prezentację

Na początek wczytaj prezentację PowerPoint, z której chcesz wygenerować niestandardowy obraz miniatury. Można to zrobić za pomocą biblioteki Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Utwórz klasę Presentation reprezentującą plik prezentacji
using (Presentation pres = new Presentation(srcFileName))
{
    // Twój kod do generowania miniaturek będzie tutaj
}
```

## Krok 2: Dostęp do slajdu

W załadowanej prezentacji musisz uzyskać dostęp do konkretnego slajdu, z którego chcesz wygenerować niestandardowy obraz miniatury. Możesz wybrać slajd według jego indeksu.

```csharp
// Uzyskaj dostęp do pierwszego slajdu (indeks możesz zmienić w razie potrzeby)
ISlide sld = pres.Slides[0];
```

## Krok 3: Zdefiniuj niestandardowe wymiary miniatur

Określ żądane wymiary dla swojego niestandardowego obrazu miniatury. Możesz zdefiniować szerokość i wysokość w pikselach zgodnie z wymaganiami swojej aplikacji.

```csharp
int desiredX = 1200; // Szerokość
int desiredY = 800;  // Wysokość
```

## Krok 4: Oblicz współczynniki skalowania

Aby zachować proporcje slajdu, oblicz współczynniki skalowania dla wymiarów X i Y na podstawie rozmiaru slajdu i pożądanych wymiarów.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 5: Wygeneruj obraz miniatury

Utwórz obraz slajdu w pełnej skali o określonych wymiarach i zapisz go na dysku w formacie JPEG.

```csharp
// Utwórz obraz w pełnej skali
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Zapisz obraz na dysku w formacie JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Po wykonaniu tych kroków powinieneś pomyślnie wygenerować niestandardowy obraz miniatury ze swojej prezentacji PowerPoint.

## Wniosek

Generowanie niestandardowych miniatur z prezentacji PowerPoint przy użyciu Aspose.Slides dla .NET to cenna umiejętność, która może poprawić wrażenia użytkownika i funkcjonalność Twoich aplikacji. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz łatwo tworzyć niestandardowe miniatury, które spełniają Twoje specyficzne wymagania.

---

## FAQ (najczęściej zadawane pytania)

### Czym jest Aspose.Slides dla .NET?
Aspose.Slides for .NET to zaawansowana biblioteka umożliwiająca programistom programistyczną pracę z prezentacjami PowerPoint w aplikacjach .NET.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
Dokumentację można znaleźć [Tutaj](https://reference.aspose.com/slides/net/).

### Czy korzystanie z Aspose.Slides dla .NET jest bezpłatne?
Aspose.Slides dla .NET to komercyjna biblioteka. Informacje o cenach i licencjach można znaleźć [Tutaj](https://purchase.aspose.com/buy).

### Czy do korzystania z Aspose.Slides dla .NET potrzebne są zaawansowane umiejętności programistyczne?
Chociaż pewna znajomość programowania .NET może być przydatna, Aspose.Slides for .NET udostępnia przyjazny dla użytkownika interfejs API, który ułatwia pracę z prezentacjami PowerPoint.

### Czy dla Aspose.Slides dla .NET dostępna jest pomoc techniczna?
Tak, możesz uzyskać dostęp do pomocy technicznej i forów społecznościowych [Tutaj](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}