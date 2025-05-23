---
"date": "2025-04-16"
"description": "Dowiedz się, jak ustawić atrybuty języka dla tekstu w kształtach za pomocą Aspose.Slides dla .NET. Ten przewodnik obejmuje dodawanie automatycznych kształtów, ustawianie identyfikatorów języka i zapisywanie prezentacji."
"title": "Jak ustawić język w kształtach programu PowerPoint za pomocą Aspose.Slides dla platformy .NET"
"url": "/pl/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić język w kształtach programu PowerPoint za pomocą Aspose.Slides dla platformy .NET

świecie prezentacji cyfrowych zapewnienie dostępności i poprawnego formatowania treści w różnych językach może być wyzwaniem. Dzięki Aspose.Slides for .NET możesz bez wysiłku ustawić atrybuty języka dla tekstu w kształtach na slajdach programu PowerPoint. Ta funkcja jest szczególnie przydatna podczas przygotowywania dokumentów wielojęzycznych lub zapewniania spójności w globalnej komunikacji.

**Czego się nauczysz:**
- Dodawanie kształtów automatycznych i wstawianie do nich tekstu.
- Ustawianie identyfikatora języka dla fragmentów tekstowych za pomocą Aspose.Slides.
- Zapisywanie prezentacji z niestandardowymi konfiguracjami.

Przyjrzyjmy się bliżej, jak można bezproblemowo wdrożyć tę funkcję.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- **Biblioteki i zależności**: Musisz mieć zainstalowany Aspose.Slides dla .NET. Ta biblioteka jest niezbędna do manipulowania prezentacjami PowerPoint w C#.
  
- **Konfiguracja środowiska**:Wymagane jest środowisko programistyczne z platformą .NET Core lub .NET Framework.

- **Wymagania wstępne dotyczące wiedzy**:Przydatna będzie znajomość podstawowych koncepcji programowania w języku C# i zrozumienie zasad programowania obiektowego.

## Konfigurowanie Aspose.Slides dla .NET

Aby rozpocząć, musisz zainstalować bibliotekę Aspose.Slides. Możesz to zrobić, korzystając z jednej z następujących metod:

**Interfejs wiersza poleceń .NET**
```shell
dotnet add package Aspose.Slides
```

**Menedżer pakietów**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika menedżera pakietów NuGet**
Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Nabycie licencji

Możesz rozpocząć bezpłatny okres próbny, pobierając tymczasową licencję ze strony [Tutaj](https://purchase.aspose.com/temporary-license/). W celu ciągłego użytkowania należy rozważyć zakup licencji za pośrednictwem [ten link](https://purchase.aspose.com/buy).

Gdy konfiguracja będzie już gotowa, zainicjuj Aspose.Slides w swoim projekcie:

```csharp
using Aspose.Slides;
```

## Przewodnik wdrażania

Teraz, gdy wszystko jest skonfigurowane, zaimplementujmy funkcję ustawiania języka tekstu kształtu.

### Przegląd funkcji: Ustawianie języka tekstu kształtu

Ta funkcja umożliwia określenie języka tekstu w kształcie programu PowerPoint. Ustawiając identyfikator języka, zapewniasz, że sprawdzanie pisowni i inne funkcje specyficzne dla języka są stosowane poprawnie.

#### Krok 1: Zainicjuj prezentację

Zacznij od utworzenia instancji `Presentation` klasa.

```csharp
using (Presentation pres = new Presentation())
{
    // Twój kod tutaj
}
```

Inicjuje to nowy obiekt prezentacji programu PowerPoint, którym będziemy manipulować.

#### Krok 2: Dodaj kształt automatyczny i ramkę tekstową

Dodaj prostokątny kształt do slajdu i wstaw do niego tekst:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Tutaj, `AddAutoShape` dodaje prostokąt do pierwszego slajdu. Parametry definiują jego pozycję i rozmiar.

#### Krok 3: Ustaw identyfikator języka

Ustaw język dla części tekstowej kształtu:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Językiem sprawdzania pisowni jest język angielski (UK).

#### Krok 4: Zapisz prezentację

Na koniec zapisz prezentację w określonej ścieżce:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}