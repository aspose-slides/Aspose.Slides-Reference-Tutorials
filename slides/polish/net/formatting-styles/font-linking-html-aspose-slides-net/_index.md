---
"date": "2025-04-15"
"description": "Dowiedz się, jak zapewnić spójne renderowanie czcionek podczas konwersji prezentacji do formatu HTML za pomocą Aspose.Slides dla platformy .NET poprzez bezpośrednie osadzanie czcionek."
"title": "Jak łączyć czcionki w HTML za pomocą Aspose.Slides dla .NET&#58; Przewodnik krok po kroku"
"url": "/pl/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak łączyć czcionki w HTML za pomocą Aspose.Slides dla .NET

## Wstęp

Konwersja prezentacji do formatu HTML przy jednoczesnym zachowaniu spójności czcionek na różnych platformach może być wyzwaniem. **Aspose.Slides dla .NET** oferuje płynne rozwiązanie, pozwalając na łączenie wszystkich czcionek użytych w prezentacji bezpośrednio w wynikach HTML za pomocą osadzonych plików czcionek.

W tym samouczku pokażemy, jak wdrożyć łączenie czcionek za pomocą Aspose.Slides dla .NET i zapewnić spójność projektu na różnych platformach. 

**Czego się nauczysz:**
- Konfigurowanie środowiska z Aspose.Slides dla .NET
- Łączenie czcionek w konwersji HTML
- Pisanie niestandardowych kontrolerów do osadzania czcionek
- Zastosowania praktyczne i rozważania dotyczące wydajności

Przyjrzyjmy się bliżej krokom niezbędnym do osiągnięcia tego celu.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

### Wymagane biblioteki i zależności
- **Aspose.Slides dla .NET** Biblioteka: Główny komponent naszej implementacji.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne z zainstalowanym .NET Framework lub .NET Core.

### Wymagania wstępne dotyczące wiedzy
- Podstawowa znajomość programowania w języku C#.
- Znajomość HTML i CSS, szczególnie `@font-face` reguła.

## Konfigurowanie Aspose.Slides dla .NET

Aby użyć Aspose.Slides w projekcie .NET, musisz zainstalować bibliotekę. Oto kilka metod:

### Korzystanie z interfejsu wiersza poleceń .NET
```bash
dotnet add package Aspose.Slides
```

### Korzystanie z konsoli Menedżera pakietów
```powershell
Install-Package Aspose.Slides
```

### Za pomocą interfejsu użytkownika Menedżera pakietów NuGet
- Otwórz projekt w programie Visual Studio.
- Przejdź do „Menedżera pakietów NuGet”.
- Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Etapy uzyskania licencji
Możesz uzyskać bezpłatną licencję próbną, aby przetestować wszystkie funkcje bez ograniczeń, wykonując następujące czynności:
1. **Bezpłatna wersja próbna**:Pobierz tymczasową licencję [Tutaj](https://releases.aspose.com/slides/net/).
2. **Licencja tymczasowa**:Złóż wniosek o przedłużony dostęp [Tutaj](https://purchase.aspose.com/temporary-license/).
3. **Zakup**:Aby uzyskać pełną funkcjonalność, należy zakupić licencję [Tutaj](https://purchase.aspose.com/buy).

### Podstawowa inicjalizacja i konfiguracja
```csharp
// Utwórz instancję klasy License
easpose.slides.License license = new aspose.slides.License();

// Zastosuj licencję ze ścieżki pliku
license.SetLicense("Aspose.Slides.lic");
```

## Przewodnik wdrażania

Teraz zaimplementujmy łączenie czcionek w konwersji HTML za pomocą **Aspose.Slides dla .NET**.

### Omówienie funkcji: łączenie czcionek w konwersji HTML
Ta funkcja zapewnia, że wszystkie czcionki używane w prezentacji są bezpośrednio połączone w wynikowym pliku HTML poprzez osadzanie plików czcionek. Ta metoda zapewnia solidne rozwiązanie do zachowania spójności projektu w różnych przeglądarkach i na różnych platformach.

#### Krok 1: Utwórz niestandardowy kontroler
Utwórz niestandardową klasę kontrolera `LinkAllFontsHtmlController` który dziedziczy po `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Ustaw katalog, w którym będą przechowywane pliki czcionek
    }
}
```
#### Krok 2: Wdróż metodę pisania czcionek
Ten `WriteFont` Metoda zapisuje dane czcionki do pliku i generuje odpowiadający im kod HTML do osadzenia:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Określ nazwę czcionki, której chcesz użyć, preferując czcionki zastępcze, jeśli są dostępne.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Utwórz ścieżkę do pliku czcionki .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Zapisz dane czcionki w określonej ścieżce pliku.
    File.WriteAllBytes(path, fontData);

    // Wygeneruj blok stylu HTML osadzający czcionkę przy użyciu reguły @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}