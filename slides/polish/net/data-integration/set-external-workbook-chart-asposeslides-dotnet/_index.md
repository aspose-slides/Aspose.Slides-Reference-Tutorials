---
"date": "2025-04-15"
"description": "Dowiedz się, jak ulepszyć prezentacje, łącząc zewnętrzne dane programu Excel z Aspose.Slides dla .NET. Ten przewodnik przeprowadzi Cię przez proces konfigurowania, konfigurowania i wdrażania dynamicznych wykresów."
"title": "Jak ustawić zewnętrzny skoroszyt dla wykresu w Aspose.Slides .NET? Przewodnik krok po kroku"
"url": "/pl/net/data-integration/set-external-workbook-chart-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić zewnętrzny skoroszyt dla wykresu w Aspose.Slides .NET: przewodnik krok po kroku

## Wstęp

Włączenie danych bezpośrednio ze źródeł zewnętrznych do prezentacji może znacznie zwiększyć ich wartość. Dzięki Aspose.Slides dla .NET możesz bezproblemowo ustawić zewnętrzny skoroszyt dla wykresów w slajdach, umożliwiając dynamiczne i aktualizowane wizualizacje. Ten samouczek przeprowadzi Cię przez proces łączenia pliku Excel opartego na sieci z wykresem w prezentacji.

**Czego się nauczysz:**
- Konfigurowanie środowiska Aspose.Slides .NET.
- Konfigurowanie zewnętrznego skoroszytu z lokalizacji sieciowej dla wykresów.
- Implementacja niestandardowego programu do obsługi ładowania zasobów w języku C#.
- Praktyczne zastosowanie integracji zewnętrznych źródeł danych z prezentacjami.

Zaczynajmy!

## Wymagania wstępne

Zanim zaczniesz kodować, upewnij się, że spełniasz poniższe wymagania:

- **Wymagane biblioteki i zależności**: Zainstaluj Aspose.Slides dla .NET w swoim projekcie.
- **Wymagania dotyczące konfiguracji środowiska**:Skonfiguruj środowisko programistyczne C# (np. Visual Studio).
- **Wymagania wstępne dotyczące wiedzy**: Posiadanie podstawowej wiedzy z zakresu programowania w języku C# i znajomość programu Aspose.Slides.

## Konfigurowanie Aspose.Slides dla .NET

Zacznij od zainstalowania biblioteki Aspose.Slides w swoim projekcie. Możesz użyć dowolnej z tych metod:

**Interfejs wiersza poleceń .NET**
```bash
dotnet add package Aspose.Slides
```

**Konsola Menedżera Pakietów**
```bash
Install-Package Aspose.Slides
```

**Interfejs użytkownika menedżera pakietów NuGet**: Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Nabycie licencji

Aby używać Aspose.Slides, zacznij od bezpłatnego okresu próbnego lub poproś o tymczasową licencję. W przypadku długoterminowego użytkowania rozważ zakup pełnej licencji z ich oficjalnej strony.

### Podstawowa inicjalizacja

Oto jak zainicjować Aspose.Slides w aplikacji:
```csharp
using Aspose.Slides;

// Zainicjuj obiekt prezentacji
Presentation pres = new Presentation();
```

## Przewodnik wdrażania

Podzielmy implementację na najważniejsze funkcje.

### Ustawianie zewnętrznego skoroszytu z sieci

Funkcja ta umożliwia podłączenie pliku programu Excel w sieci jako zewnętrznego skoroszytu dla wykresu w prezentacji.

#### Krok 1: Określ ścieżkę zewnętrznego skoroszytu
Podaj ścieżkę do zewnętrznego skoroszytu znajdującego się na dysku sieciowym:
```csharp
string externalWbPath = "http://TWÓJ_KATALOG_DOKUMENTÓW/styles/2.xlsx";
```
Zastępować `YOUR_DOCUMENT_DIRECTORY` z rzeczywistym katalogiem, w którym znajduje się plik Excela.

#### Krok 2: Skonfiguruj opcje ładowania
Skonfiguruj opcje ładowania i określ niestandardowe wywołanie zwrotne ładowania zasobów:
```csharp
LoadOptions opts = new LoadOptions();
opts.ResourceLoadingCallback = new WorkbookLoadingHandler();
```

#### Krok 3: Utwórz prezentację i dodaj wykres
Utwórz instancję prezentacji i dodaj wykres do pierwszego slajdu:
```csharp
using (Presentation pres = new Presentation(opts))
{
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
    IChartData chartData = chart.ChartData;
    
    // Ustaw ścieżkę zewnętrznego skoroszytu dla danych wykresu
    (chartData as ChartData).SetExternalWorkbook(externalWbPath);
}
```

### Obsługa ładowania skoroszytu

Funkcja ta obejmuje utworzenie niestandardowego programu obsługi ładowania zasobów w celu pobrania pliku Excel ze wskazanej lokalizacji sieciowej.

#### Krok 1: Wdróż funkcję zwrotną ładowania zasobów
Utwórz klasę, która implementuje `IResourceLoadingCallback`:
```csharp
class WorkbookLoadingHandler : IResourceLoadingCallback
{
    public ResourceLoadingAction ResourceLoading(IResourceLoadingArgs args)
    {
        string workbookPath = args.OriginalUri;
        
        // Sprawdź, czy ścieżka jest lokalizacją sieciową (a nie ścieżką do pliku lokalnego)
        if (workbookPath.IndexOf(':') > 1 && !workbookPath.StartsWith("file:///"))
        {
            try
            {
                WebRequest request = WebRequest.Create(workbookPath);
                request.Credentials = new NetworkCredential("testuser", "testuser");
                
                using (WebResponse response = request.GetResponse())
                using (Stream responseStream = response.GetResponseStream())
                {
                    // Przekaż pobrane dane do Aspose.Slides
                    return ResourceLoadingAction.UserProvided;
                }
            }
            catch (Exception ex)
            {
                throw new InvalidOperationException(ex.ToString());
            }
        }
        else
        {
            return ResourceLoadingAction.Default;
        }
    }
}
```

## Zastosowania praktyczne

Oto kilka praktycznych przypadków użycia integracji zewnętrznych źródeł danych z prezentacjami Aspose.Slides:
1. **Dynamiczne raportowanie**: Automatyczna aktualizacja wykresów w raportach finansowych i wydajnościowych na podstawie najnowszych danych sieciowych.
2. **Panele biznesowe**:Twórz interaktywne pulpity nawigacyjne, które pobierają dane na żywo z korporacyjnych baz danych lub serwerów zdalnych.
3. **Treści edukacyjne**:Opracowanie materiałów edukacyjnych zawierających aktualne dane statystyczne na tematy takie jak ekonomia czy demografia.

## Rozważania dotyczące wydajności

Podczas pracy z zewnętrznymi skoroszytami należy wziąć pod uwagę następujące wskazówki dotyczące wydajności:
- **Optymalizacja żądań sieciowych**:Zminimalizuj częstotliwość żądań sieciowych, aby zmniejszyć opóźnienia i wykorzystanie przepustowości.
- **Zarządzanie zasobami**:Zapewnij efektywne wykorzystanie pamięci, zwalniając strumienie niezwłocznie po tym, jak nie będą już potrzebne.
- **Obsługa błędów**:Wdrożenie niezawodnej obsługi błędów w przypadku problemów z siecią w celu zapewnienia płynnego działania aplikacji.

## Wniosek

Teraz powinieneś mieć solidne zrozumienie, jak ustawić zewnętrzny skoroszyt z lokalizacji sieciowej przy użyciu Aspose.Slides dla .NET. Ta możliwość może znacznie zwiększyć interaktywność prezentacji i trafność danych. Aby uzyskać dalsze informacje, rozważ integrację innych bibliotek Aspose lub zapoznaj się z dodatkowymi typami wykresów obsługiwanymi przez Aspose.Slides. Spróbuj wdrożyć to rozwiązanie w jednym ze swoich projektów, aby zobaczyć korzyści z pierwszej ręki!

## Sekcja FAQ

**1. Czym jest Aspose.Slides dla .NET?**
Aspose.Slides for .NET to zaawansowana biblioteka umożliwiająca programistom tworzenie, edytowanie i konwertowanie prezentacji PowerPoint w sposób programistyczny.

**2. Czy mogę używać Aspose.Slides z innymi językami programowania?**
Tak, Aspose udostępnia podobne biblioteki dla języków Java, C++, Python i innych.

**3. Jak poradzić sobie z błędami sieciowymi podczas ładowania zewnętrznego skoroszytu?**
Wdróż solidną obsługę wyjątków w swoim `WorkbookLoadingHandler` aby sprawnie zarządzać potencjalnymi problemami sieciowymi.

**4. Czy można używać plików lokalnych zamiast lokalizacji sieciowych?**
Tak, możesz zmodyfikować ścieżkę w `externalWbPath` aby w razie potrzeby wskazać plik lokalny.

**5. Czy mogę automatycznie aktualizować wykresy o nowe dane?**
Tak, dzięki okresowemu ponownemu pobieraniu i konfigurowaniu skoroszytu zewnętrznego wykresy będą odzwierciedlać wszelkie aktualizacje wprowadzone w danych źródłowych.

## Zasoby
- **Dokumentacja**: [Dokumentacja Aspose.Slides .NET](https://reference.aspose.com/slides/net/)
- **Pobierać**: [Wydania Aspose.Slides dla .NET](https://releases.aspose.com/slides/net/)
- **Zakup**: [Kup Aspose.Slides](https://purchase.aspose.com/buy)
- **Bezpłatna wersja próbna**: [Aspose.Slides Bezpłatna wersja próbna](https://releases.aspose.com/slides/net/)
- **Licencja tymczasowa**: [Uzyskaj tymczasową licencję na Aspose.Slides](https://purchase.aspose.com/temporary-license/)
- **Wsparcie**: [Forum wsparcia Aspose](https://forum.aspose.com/c/slides/11)

Dzięki tym zasobom jesteś dobrze wyposażony, aby wykorzystać pełen potencjał Aspose.Slides w swoich projektach .NET. Miłego kodowania!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}