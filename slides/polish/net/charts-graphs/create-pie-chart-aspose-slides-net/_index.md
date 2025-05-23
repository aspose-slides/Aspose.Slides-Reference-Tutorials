---
"date": "2025-04-15"
"description": "Dowiedz się, jak programowo dodawać wykresy kołowe do prezentacji za pomocą Aspose.Slides for .NET, co pozwoli Ci bez wysiłku udoskonalić wizualizację danych."
"title": "Utwórz wykres kołowy w programie PowerPoint za pomocą Aspose.Slides dla platformy .NET"
"url": "/pl/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć i dodać wykres kołowy do prezentacji przy użyciu Aspose.Slides dla .NET
## Wstęp
Tworzenie atrakcyjnych prezentacji często obejmuje więcej niż tylko tekst; elementy wizualne, takie jak wykresy, mogą znacznie zwiększyć wpływ opowiadania historii danych. Jeśli chcesz programowo dodać dynamiczne wykresy kołowe do prezentacji PowerPoint, **Aspose.Slides dla .NET** jest potężnym narzędziem, które sprawia, że to zadanie jest płynne i wydajne. Ten samouczek przeprowadzi Cię przez dodawanie wykresu kołowego do slajdu prezentacji i konfigurowanie go z zewnętrznymi źródłami danych.

### Czego się nauczysz
- Jak utworzyć nową prezentację przy użyciu Aspose.Slides dla .NET
- Dodawanie wykresu kołowego do pierwszego slajdu
- Ustawianie zewnętrznego adresu URL skoroszytu jako źródła danych dla wykresu
- Zapisywanie prezentacji w formacie PPTX
Przyjrzyjmy się teraz, jak możesz to łatwo osiągnąć, zaczynając od wymagań wstępnych.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz przygotowane następujące rzeczy:
- **Aspose.Slides dla .NET** biblioteka zainstalowana. Będziesz potrzebować wersji zgodnej z .NET Framework lub .NET Core/.NET 5+.
- Podstawowa znajomość programowania w języku C# i znajomość środowiska IDE Visual Studio.
- Środowisko programistyczne skonfigurowane na Twoim komputerze (Windows, macOS lub Linux).
## Konfigurowanie Aspose.Slides dla .NET
### Instrukcje instalacji
Aspose.Slides dla .NET można dodać do projektu na różne sposoby:
**Interfejs wiersza poleceń .NET**
```shell
dotnet add package Aspose.Slides
```
**Konsola Menedżera Pakietów**
```powershell
Install-Package Aspose.Slides
```
**Interfejs użytkownika menedżera pakietów NuGet**
1. Otwórz Menedżera pakietów NuGet w programie Visual Studio.
2. Wyszukaj „Aspose.Slides”.
3. Zainstaluj najnowszą wersję.
### Nabycie licencji
Aby korzystać z Aspose.Slides, możesz zacząć od bezpłatnej licencji próbnej, aby eksplorować jego funkcje bez ograniczeń. W środowiskach produkcyjnych rozważ zakup licencji komercyjnej lub uzyskanie licencji tymczasowej do rozszerzonego testowania. Odwiedź [Strona zakupu Aspose](https://purchase.aspose.com/buy) po więcej szczegółów.
### Podstawowa inicjalizacja
Aby użyć Aspose.Slides w swoim projekcie, musisz go zainicjować za pomocą swojej licencji, o ile jest dostępna:
```csharp
// Zainicjuj bibliotekę
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Przewodnik wdrażania
Teraz, gdy wszystko jest już skonfigurowane, omówimy krok po kroku każdą funkcję.
### Utwórz i dodaj wykres do prezentacji
#### Przegląd
Zaczniemy od utworzenia prezentacji i dodania wykresu kołowego do pierwszego slajdu.
#### Kroki:
1. **Zainicjuj prezentację**
   Zacznij od utworzenia instancji `Presentation` Klasa, która reprezentuje plik programu PowerPoint.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Tutaj dodamy nasz wykres.
   }
   ```
2. **Dodaj wykres kołowy**
   Użyj `Shapes.AddChart` metoda wstawiania wykresu kołowego w określonych współrzędnych na slajdzie.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Ustaw zewnętrzny skoroszyt dla danych wykresu
#### Przegląd
Teraz skonfigurujemy wykres kołowy tak, aby wykorzystywał dane z zewnętrznego skoroszytu.
#### Kroki:
1. **Dostęp do danych wykresu**
   Pobierz interfejs danych wykresu, w którym możesz określić adres URL zewnętrznego źródła danych.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Ustaw adres URL zewnętrznego skoroszytu**
   Ustaw adres URL dla swojego źródła danych za pomocą `SetExternalWorkbook`. W tym przykładzie użyto zastępczego adresu URL, który należy zastąpić rzeczywistą ścieżką źródła danych.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://ścieżka/nie/istnieje", false);
   ```
### Zapisz prezentację do pliku
#### Przegląd
Na koniec zapisz prezentację w formacie PPTX w wybranej lokalizacji.
#### Kroki:
1. **Zapisz prezentację**
   Użyj `Save` metoda `Presentation` klasa do zapisu pliku na dysku.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Zastosowania praktyczne
- **Raporty biznesowe**:Automatycznie generuj wykresy na potrzeby kwartalnych ocen wyników.
- **Panele danych**: Integracja ze źródłami danych w celu aktualizowania raportów wizualnych w czasie rzeczywistym.
- **Treści edukacyjne**:Tworzenie dynamicznych prezentacji wykorzystujących najnowsze dane z zewnętrznych badań lub prac naukowych.
Dzięki integracji Aspose.Slides możesz zautomatyzować i udoskonalić proces tworzenia prezentacji w różnych domenach.
## Rozważania dotyczące wydajności
Podczas pracy z dużymi zbiorami danych lub wieloma wykresami:
- Optymalizacja wykorzystania zasobów poprzez efektywne zarządzanie pamięcią w środowisku .NET.
- Pozbyć się `Presentation` obiekty prawidłowo zwalniają zasoby.
- W miarę możliwości należy stosować operacje asynchroniczne, aby zwiększyć responsywność aplikacji.
## Wniosek
Dzięki temu samouczkowi nauczyłeś się programowo tworzyć prezentacje z wykresami kołowymi przy użyciu Aspose.Slides dla .NET. Teraz masz narzędzia do automatyzacji tworzenia wykresów i efektywnego zarządzania zewnętrznymi źródłami danych.
### Następne kroki
Możesz dowiedzieć się więcej, dostosowując style wykresów, dodając więcej typów wykresów lub integrując inne komponenty Aspose, takie jak Aspose.Cells, aby uzyskać rozszerzone możliwości manipulowania danymi.
## Sekcja FAQ
1. **Czym jest Aspose.Slides?**  
   Solidna biblioteka umożliwiająca programowe modyfikowanie prezentacji PowerPoint w środowisku .NET.
2. **Czy mogę używać Aspose.Slides bez licencji?**  
   Tak, ale z ograniczeniami. Rozważ uzyskanie bezpłatnej wersji próbnej lub zakup licencji na pełne funkcje.
3. **Jak dynamicznie aktualizować dane na wykresie?**  
   Użyj zewnętrznych skoroszytów i ustaw ich adresy URL w `SetExternalWorkbook` metoda.
4. **Czy Aspose.Slides można używać na wielu platformach?**  
   Tak, obsługuje .NET Framework i .NET Core/.NET 5+ w systemach Windows, macOS i Linux.
5. **Jakie inne typy wykresów są obsługiwane?**  
   Oprócz wykresów kołowych za pomocą Aspose.Slides można tworzyć także wykresy słupkowe, wykresy liniowe i inne.
## Zasoby
- [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/)
- [Pobierz najnowszą wersję](https://releases.aspose.com/slides/net/)
- [Kup licencję](https://purchase.aspose.com/buy)
- [Bezpłatna wersja próbna](https://releases.aspose.com/slides/net/)
- [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/)
- [Forum wsparcia](https://forum.aspose.com/c/slides/11)
Zacznij już dziś integrować Aspose.Slides ze swoimi projektami, aby udoskonalić i zautomatyzować prezentacje PowerPoint!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}