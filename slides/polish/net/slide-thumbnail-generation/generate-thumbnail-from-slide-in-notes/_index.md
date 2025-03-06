---
title: Wygeneruj miniaturę ze slajdu w notatkach
linktitle: Wygeneruj miniaturę ze slajdu w notatkach
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak generować miniatury slajdów w sekcji notatek swojej prezentacji za pomocą Aspose.Slides dla .NET. Wzbogać swoje treści wizualne!
type: docs
weight: 12
url: /pl/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

świecie nowoczesnych prezentacji najważniejsza jest treść wizualna. Tworzenie atrakcyjnych slajdów jest niezbędne dla skutecznej komunikacji. Jednym ze sposobów ulepszenia prezentacji jest generowanie miniatur ze slajdów, zwłaszcza gdy chcesz podkreślić określone szczegóły lub udostępnić przegląd. Aspose.Slides dla .NET to potężne narzędzie, które pomoże Ci to osiągnąć bezproblemowo. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces generowania miniatur ze slajdów w sekcji notatek prezentacji przy użyciu Aspose.Slides dla .NET.

## Warunki wstępne

Zanim zagłębimy się w szczegóły, należy spełnić następujące wymagania wstępne:

### 1. Aspose.Slides dla .NET

 Upewnij się, że masz zainstalowany i skonfigurowany Aspose.Slides dla .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

### 2. Środowisko .NET

Powinieneś mieć gotowe środowisko programistyczne .NET w swoim systemie.

### 3. Plik prezentacji

 Przygotuj plik prezentacji (np.`ThumbnailFromSlideInNotes.pptx`), z którego chcesz wygenerować miniatury.

Podzielmy teraz proces na etapy:

## Krok 1: Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby móc pracować z Aspose.Slides. Dodaj następujący kod na początku skryptu C#:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Krok 2: Załaduj prezentację

 Następnie musisz załadować plik prezentacji zawierający slajdy z notatkami. Użyj poniższego kodu, aby utworzyć instancję a`Presentation` klasa:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Twój kod trafia tutaj
}
```

## Krok 3: Uzyskaj dostęp do slajdu

Możesz wybrać, dla którego slajdu w prezentacji chcesz wygenerować miniaturę. W tym przykładzie uzyskamy dostęp do pierwszego slajdu:

```csharp
ISlide sld = pres.Slides[0];
```

## Krok 4: Zdefiniuj żądane wymiary

Określ wymiary (szerokość i wysokość) miniatury, którą chcesz wygenerować. Na przykład:

```csharp
int desiredX = 1200; // Szerokość
int desiredY = 800;  // Wysokość
```

## Krok 5: Oblicz współczynniki skalowania

Aby upewnić się, że miniatura ma odpowiednie wymiary, oblicz współczynniki skalowania w następujący sposób:

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

Otóż to! Pomyślnie wygenerowałeś miniaturę ze slajdu w sekcji notatek swojej prezentacji przy użyciu Aspose.Slides dla .NET.

## Wniosek

Włączenie miniatur do prezentacji może znacznie poprawić ich atrakcyjność wizualną i skuteczność. Aspose.Slides dla .NET sprawia, że ten proces jest prosty, umożliwiając łatwe tworzenie niestandardowych miniatur ze slajdów.

## Często zadawane pytania (często zadawane pytania)

### W jakich formatach mogę zapisać wygenerowane miniatury?
Miniatury możesz zapisywać w różnych formatach, w tym JPEG, PNG i innych, w zależności od wymagań.

### Czy mogę wygenerować miniatury dla wielu slajdów jednocześnie?
Tak, możesz przeglądać slajdy w prezentacji i generować miniatury dla każdego z nich.

### Czy Aspose.Slides for .NET jest kompatybilny z różnymi frameworkami .NET?
Tak, Aspose.Slides dla .NET jest kompatybilny z różnymi frameworkami .NET, w tym .NET Core i .NET Framework.

### Czy mogę dostosować wygląd generowanych miniatur?
Absolutnie! Aspose.Slides dla .NET zapewnia opcje dostosowywania wyglądu miniatur, takich jak wymiary, jakość i inne.

### Gdzie mogę uzyskać wsparcie lub dalszą pomoc dotyczącą Aspose.Slides dla .NET?
 Możesz znaleźć pomoc i nawiązać kontakt ze społecznością Aspose na stronie[Forum wsparcia Aspose](https://forum.aspose.com/).