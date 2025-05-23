---
"date": "2025-04-15"
"description": "Dowiedz się, jak modyfikować osie kategorii wykresu w programie PowerPoint za pomocą Aspose.Slides dla platformy .NET, zwiększając czytelność danych i atrakcyjność wizualną prezentacji."
"title": "Jak modyfikować oś kategorii wykresu w programie PowerPoint za pomocą Aspose.Slides .NET"
"url": "/pl/net/charts-graphs/modify-chart-category-axis-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak modyfikować oś kategorii wykresu w programie PowerPoint za pomocą Aspose.Slides .NET

## Wstęp

Zwiększ wizualny wpływ wykresów w prezentacjach PowerPoint, modyfikując osie kategorii wykresu. Ten przewodnik opisuje, jak dostosować typ osi kategorii wykresu za pomocą Aspose.Slides dla .NET, poprawiając czytelność danych i jakość prezentacji — szczególnie w przypadku danych szeregów czasowych.

W dzisiejszym świecie opartym na danych konwersja surowych liczb na intuicyjne grafiki jest niezbędna. Dzięki Aspose.Slides dla .NET programiści mogą skutecznie manipulować wykresami PowerPoint, aby zapewnić jasną komunikację w swoich prezentacjach.

**Czego się nauczysz:**
- Modyfikuj typ osi kategorii wykresu za pomocą Aspose.Slides dla .NET.
- Skonfiguruj główne ustawienia jednostek na osi poziomej w celu lepszego przedstawienia danych.
- Zapisz zmiany w łatwy sposób w nowym pliku programu PowerPoint.

## Wymagania wstępne

### Wymagane biblioteki, wersje i zależności
Aby wdrożyć tę funkcję, upewnij się, że posiadasz:
- **Aspose.Slides dla .NET**:Podstawowa biblioteka do edycji prezentacji PowerPoint.
- **.NET Framework lub .NET Core/5+/6+** zainstalowany na Twoim komputerze (sprawdź zgodność z dokumentacją Aspose).

### Wymagania dotyczące konfiguracji środowiska
Upewnij się, że Twoje środowisko programistyczne obsługuje aplikacje .NET, korzystając z programu Visual Studio lub podobnego środowiska IDE.

### Wymagania wstępne dotyczące wiedzy
Podstawowa znajomość języka C# i prezentacja PowerPoint są przydatne. Wcześniejsze doświadczenie z Aspose.Slides dla .NET jest pomocne, ale niekonieczne.

## Konfigurowanie Aspose.Slides dla .NET

Aby rozpocząć, zainstaluj Aspose.Slides w środowisku projektu.

**Opcje instalacji:**

**Interfejs wiersza poleceń .NET**
```shell
dotnet add package Aspose.Slides
```

**Konsola Menedżera Pakietów**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika menedżera pakietów NuGet**
Wyszukaj „Aspose.Slides” i kliknij „Zainstaluj”, aby pobrać najnowszą wersję.

### Nabycie licencji
- **Bezpłatna wersja próbna**:Pobierz bezpłatną wersję próbną z [Strona wydań Aspose](https://releases.aspose.com/slides/net/).
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na rozszerzony dostęp bez ograniczeń pod adresem [Strona tymczasowej licencji Aspose](https://purchase.aspose.com/temporary-license/).
- **Zakup**:Rozważ zakup licencji bezpośrednio od [Strona zakupu Aspose](https://purchase.aspose.com/buy) do długotrwałego stosowania.

**Podstawowa inicjalizacja:**
```csharp
// Utwórz instancję klasy Presentation\using (Presentation presentation = new Presentation())
{
    // Operacje z Aspose.Slides
}
```

## Przewodnik wdrażania

### Zmień oś kategorii wykresu na datę
Funkcja ta umożliwia modyfikację typu osi kategorii wykresu, co jest idealnym rozwiązaniem w przypadku danych szeregów czasowych.

#### Przegląd
Zmienimy oś kategorii istniejącego wykresu w prezentacji PowerPoint na format daty i skonfigurujemy jej główne ustawienia jednostki. Ta korekta sprawi, że osie czasu będą bardziej przejrzyste i intuicyjne dla widzów.

#### Kroki:

**Krok 1: Załaduj swoją prezentację**
Załaduj istniejącą prezentację zawierającą wykres, który chcesz zmodyfikować.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation(dataDir + "/ExistingChart.pptx"))
{
    // Uzyskiwanie dostępu do pierwszego kształtu na pierwszym slajdzie i rzutowanie go do IChart
    IChart chart = presentation.Slides[0].Shapes[0] as IChart;
```

**Krok 2: Modyfikuj typ osi kategorii**
Zmień typ osi kategorii na `Date`, idealne dla zbiorów danych zawierających dane chronologiczne.
```csharp
    // Zmień typ osi kategorii na Data
    chart.Axes.HorizontalAxis.CategoryAxisType = CategoryAxisType.Date;
```

**Krok 3: Skonfiguruj ustawienia głównej jednostki**
Ustaw ręczne sterowanie głównymi odstępami linii siatki, aby zwiększyć przejrzystość i precyzję prezentacji.
```csharp
    // Skonfiguruj główne ustawienia jednostki na osi poziomej
    chart.Axes.HorizontalAxis.IsAutomaticMajorUnit = false; 
    chart.Axes.HorizontalAxis.MajorUnit = 1;
    chart.Axes.HorizontalAxis.MajorUnitScale = TimeUnitType.Months;
```

**Krok 4: Zapisz zmiany**
Na koniec zapisz prezentację ze zmodyfikowanym wykresem w nowym pliku.
```csharp
    // Zapisz zaktualizowaną prezentację
    presentation.Save(dataDir + "/ChangeChartCategoryAxis_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}