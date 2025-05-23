---
"description": "Dowiedz się, jak generować miniatury ze slajdów w sekcji notatek swojej prezentacji, używając Aspose.Slides dla .NET. Ulepsz swoją zawartość wizualną!"
"linktitle": "Generuj miniaturę ze slajdu w notatkach"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Generuj miniaturę ze slajdu w notatkach"
"url": "/pl/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Generuj miniaturę ze slajdu w notatkach


świecie nowoczesnych prezentacji króluje treść wizualna. Tworzenie atrakcyjnych slajdów jest niezbędne do skutecznej komunikacji. Jednym ze sposobów na ulepszenie prezentacji jest generowanie miniatur ze slajdów, zwłaszcza gdy chcesz podkreślić konkretne szczegóły lub udostępnić przegląd. Aspose.Slides for .NET to potężne narzędzie, które może pomóc Ci to osiągnąć bezproblemowo. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces generowania miniatur ze slajdów w sekcji notatek prezentacji przy użyciu Aspose.Slides for .NET.

## Wymagania wstępne

Zanim przejdziemy do szczegółów, powinieneś spełnić następujące wymagania wstępne:

### 1. Aspose.Slides dla .NET

Upewnij się, że masz zainstalowany i skonfigurowany Aspose.Slides dla .NET. Możesz go pobrać ze strony [Tutaj](https://releases.aspose.com/slides/net/).

### 2. Środowisko .NET

Powinieneś mieć w swoim systemie gotowe środowisko programistyczne .NET.

### 3. Plik prezentacji

Posiadasz plik prezentacji (np. `ThumbnailFromSlideInNotes.pptx`) z którego chcesz wygenerować miniatury.

Teraz podzielmy proces na kroki:

## Krok 1: Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby pracować z Aspose.Slides. Dodaj następujący kod na początku skryptu C#:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 2: Załaduj prezentację

Następnie musisz załadować plik prezentacji zawierający slajdy z notatkami. Użyj następującego kodu, aby utworzyć wystąpienie `Presentation` klasa:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Twój kod wpisz tutaj
}
```

## Krok 3: Dostęp do slajdu

Możesz wybrać, dla którego slajdu prezentacji chcesz wygenerować miniaturę. W tym przykładzie uzyskamy dostęp do pierwszego slajdu:

```csharp
ISlide sld = pres.Slides[0];
```

## Krok 4: Określ żądane wymiary

Określ wymiary (szerokość i wysokość) miniatury, którą chcesz wygenerować. Na przykład:

```csharp
int desiredX = 1200; // Szerokość
int desiredY = 800;  // Wysokość
```

## Krok 5: Oblicz współczynniki skalowania

Aby mieć pewność, że miniatura będzie miała żądane wymiary, oblicz współczynniki skalowania w następujący sposób:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Krok 6: Utwórz miniaturę

Teraz utwórz miniaturę obrazu w pełnej skali, korzystając z obliczonych współczynników skalowania:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Krok 7: Zapisz miniaturę

Na koniec zapisz wygenerowaną miniaturę jako obraz JPEG:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

To wszystko! Udało Ci się wygenerować miniaturę ze slajdu w sekcji notatek swojej prezentacji przy użyciu Aspose.Slides dla .NET.

## Wniosek

Dodanie miniatur do prezentacji może znacznie poprawić ich atrakcyjność wizualną i skuteczność. Aspose.Slides for .NET sprawia, że proces ten jest prosty, umożliwiając łatwe tworzenie niestandardowych miniatur ze slajdów.

## FAQ (najczęściej zadawane pytania)

### W jakich formatach mogę zapisać wygenerowane miniatury?
Miniatury możesz zapisywać w różnych formatach, w tym JPEG, PNG i innych, zależnie od swoich potrzeb.

### Czy mogę generować miniatury dla wielu slajdów jednocześnie?
Tak, możesz przeglądać slajdy prezentacji i generować miniatury dla każdego z nich.

### Czy Aspose.Slides dla .NET jest kompatybilny z różnymi frameworkami .NET?
Tak, Aspose.Slides dla .NET jest kompatybilny z różnymi platformami .NET, w tym .NET Core i .NET Framework.

### Czy mogę dostosować wygląd generowanych miniatur?
Oczywiście! Aspose.Slides dla .NET udostępnia opcje dostosowywania wyglądu miniatur, takie jak wymiary, jakość i inne.

### Gdzie mogę uzyskać pomoc lub dalsze wsparcie dotyczące Aspose.Slides dla .NET?
Pomoc i zaangażowanie społeczności Aspose można znaleźć na stronie [Forum wsparcia Aspose](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}