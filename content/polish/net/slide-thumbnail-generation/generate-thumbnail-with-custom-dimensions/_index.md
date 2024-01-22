---
title: Generuj miniatury na slajdach o niestandardowych wymiarach
linktitle: Wygeneruj miniaturę z niestandardowymi wymiarami
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak generować niestandardowe miniatury z prezentacji programu PowerPoint za pomocą Aspose.Slides dla .NET. Zwiększ komfort użytkowania i funkcjonalność.
type: docs
weight: 13
url: /pl/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

Tworzenie niestandardowych miniatur prezentacji programu PowerPoint może być cennym nabytkiem, niezależnie od tego, czy tworzysz interaktywną aplikację, poprawiasz komfort użytkownika, czy optymalizujesz zawartość dla różnych platform. W tym samouczku przeprowadzimy Cię przez proces generowania niestandardowych miniatur z prezentacji programu PowerPoint przy użyciu biblioteki Aspose.Slides dla .NET. Ta potężna biblioteka umożliwia programowe manipulowanie, konwertowanie i ulepszanie plików programu PowerPoint w aplikacjach .NET.

## Warunki wstępne

Zanim zajmiemy się generowaniem niestandardowych obrazów miniatur, upewnij się, że spełnione są następujące wymagania wstępne:

### 1. Aspose.Slides dla .NET

 Musisz mieć zainstalowaną bibliotekę Aspose.Slides for .NET w swoim projekcie. Jeśli jeszcze tego nie zrobiłeś, możesz znaleźć niezbędną dokumentację i linki do pobrania[Tutaj](https://reference.aspose.com/slides/net/).

### 2. Prezentacja programu PowerPoint

Upewnij się, że masz prezentację programu PowerPoint, z której chcesz wygenerować niestandardową miniaturę. Ta prezentacja powinna być dostępna w katalogu Twojego projektu.

### 3. Środowisko programistyczne

Aby skorzystać z tego samouczka, należy posiadać praktyczną wiedzę na temat programowania .NET przy użyciu języka C# i skonfigurowanego środowiska programistycznego, takiego jak Visual Studio.

Teraz, gdy omówiliśmy wymagania wstępne, podzielmy proces generowania niestandardowych miniatur na instrukcje krok po kroku.

## Importuj przestrzenie nazw

Najpierw musisz uwzględnić wymagane przestrzenie nazw w kodzie C#. Te przestrzenie nazw umożliwiają pracę z Aspose.Slides i manipulowanie prezentacjami programu PowerPoint.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 1: Załaduj prezentację

Aby rozpocząć, załaduj prezentację programu PowerPoint, z której chcesz wygenerować niestandardową miniaturę. Osiąga się to za pomocą biblioteki Aspose.Slides.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Utwórz instancję klasy Prezentacja reprezentującej plik prezentacji
using (Presentation pres = new Presentation(srcFileName))
{
    // Twój kod do generowania miniatur będzie tutaj
}
```

## Krok 2: Uzyskaj dostęp do slajdu

W załadowanej prezentacji musisz uzyskać dostęp do konkretnego slajdu, z którego chcesz wygenerować niestandardową miniaturę. Możesz wybrać slajd według jego indeksu.

```csharp
// Uzyskaj dostęp do pierwszego slajdu (w razie potrzeby możesz zmienić indeks)
ISlide sld = pres.Slides[0];
```

## Krok 3: Zdefiniuj niestandardowe wymiary miniatur

Określ żądane wymiary niestandardowej miniatury. Możesz zdefiniować szerokość i wysokość w pikselach zgodnie z wymaganiami aplikacji.

```csharp
int desiredX = 1200; // Szerokość
int desiredY = 800;  // Wysokość
```

## Krok 4: Oblicz współczynniki skalowania

Aby zachować proporcje slajdu, oblicz współczynniki skalowania dla wymiarów X i Y w oparciu o rozmiar slajdu i żądane wymiary.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 5: Wygeneruj obraz miniatury

Utwórz pełnowymiarowy obraz slajdu o określonych niestandardowych wymiarach i zapisz go na dysku w formacie JPEG.

```csharp
// Utwórz obraz w pełnej skali
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Zapisz obraz na dysku w formacie JPEG
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Po wykonaniu tych kroków powinieneś pomyślnie wygenerować niestandardową miniaturę z prezentacji programu PowerPoint.

## Wniosek

Generowanie niestandardowych miniatur z prezentacji programu PowerPoint przy użyciu Aspose.Slides dla .NET to cenna umiejętność, która może poprawić komfort użytkowania i funkcjonalność aplikacji. Wykonując kroki opisane w tym samouczku, możesz łatwo tworzyć niestandardowe miniatury spełniające Twoje specyficzne wymagania.

---

## Często zadawane pytania (często zadawane pytania)

### Co to jest Aspose.Slides dla .NET?
Aspose.Slides dla .NET to potężna biblioteka, która umożliwia programistom programową pracę z prezentacjami programu PowerPoint w aplikacjach .NET.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
 Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/net/).

### Czy korzystanie z Aspose.Slides dla .NET jest bezpłatne?
 Aspose.Slides dla .NET to biblioteka komercyjna. Można znaleźć informacje o cenach i licencjach[Tutaj](https://purchase.aspose.com/buy).

### Czy potrzebuję zaawansowanych umiejętności programowania, aby korzystać z Aspose.Slides dla .NET?
Chociaż pewna znajomość programowania .NET jest korzystna, Aspose.Slides dla .NET zapewnia przyjazny dla użytkownika interfejs API, który upraszcza pracę z prezentacjami programu PowerPoint.

### Czy dostępna jest pomoc techniczna dla Aspose.Slides dla .NET?
 Tak, możesz uzyskać dostęp do pomocy technicznej i forów społeczności[Tutaj](https://forum.aspose.com/).