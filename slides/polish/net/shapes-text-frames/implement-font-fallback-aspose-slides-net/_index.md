---
"date": "2025-04-16"
"description": "Dowiedz się, jak wdrożyć reguły zapasowego stosowania czcionek w Aspose.Slides dla platformy .NET, aby mieć pewność, że tekst w prezentacjach będzie wyświetlany poprawnie w różnych językach i skryptach."
"title": "Jak ustawić reguły zapasowe czcionek w Aspose.Slides dla .NET&#58; Kompleksowy przewodnik"
"url": "/pl/net/shapes-text-frames/implement-font-fallback-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić reguły zapasowe czcionek w Aspose.Slides dla .NET: kompleksowy przewodnik

## Wstęp

Tworzenie prezentacji za pomocą Aspose.Slides dla .NET czasami wymaga obsługi znaków, których konkretne czcionki nie obsługują, takich jak Tamil lub japońska Hiragana. Ustawienie reguł zapasowych czcionek jest niezbędne, aby zapewnić, że prezentacja wyświetla tekst poprawnie w różnych językach i symbolach.

W tym samouczku przeprowadzimy Cię przez implementację reguł zapasowych czcionek przy użyciu Aspose.Slides dla .NET. Od instalacji do praktycznych zastosowań, ten przewodnik zapewnia, że Twoje prezentacje zachowują spójność wizualną niezależnie od treści.

**Czego się nauczysz:**
- Zdefiniuj zakresy Unicode dla różnych skryptów.
- Skonfiguruj czcionki zapasowe dla nieobsługiwanych znaków.
- Zastosuj czcionki zapasowe w scenariuszach prezentacji z życia wziętych.
- Wskazówki dotyczące optymalizacji wydajności i integracji z innymi systemami.

Zacznijmy od przeglądu warunków wstępnych.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- **Aspose.Slides dla .NET** biblioteka zainstalowana. Zainstaluj za pomocą dowolnej z tych metod:
  - **Interfejs wiersza poleceń .NET**: Uruchomić `dotnet add package Aspose.Slides`
  - **Menedżer pakietów**: Wykonać `Install-Package Aspose.Slides`
  - **Interfejs użytkownika menedżera pakietów NuGet**: Wyszukaj i zainstaluj najnowszą wersję.
- Środowisko programistyczne skonfigurowane przy użyciu .NET Core lub .NET Framework (wersja 4.5 lub nowsza).
- Podstawowa znajomość programowania w języku C#.

## Konfigurowanie Aspose.Slides dla .NET

Aby rozpocząć korzystanie z Aspose.Slides, należy nabyć licencję od [Strona internetowa Aspose](https://purchase.aspose.com/buy)Oto jak to skonfigurować:

1. **Instalacja**: Postępuj zgodnie z krokami instalacji opisanymi powyżej.
2. **Konfiguracja licencji**:
   - Wczytaj plik licencji do projektu za pomocą:
     ```csharp
     License license = new License();
     license.SetLicense("path_to_your_license_file.lic");
     ```

Ta konfiguracja umożliwia rozpoczęcie pracy z Aspose.Slides dla .NET.

## Przewodnik wdrażania

W tej sekcji przedstawimy w przejrzysty sposób proces ustalania reguł zapasowych czcionek.

### 1. Zdefiniuj zakresy Unicode i czcionki zapasowe

Każdy skrypt lub zestaw symboli wymaga określonych zakresów Unicode i odpowiadających im czcionek zapasowych w celu zapewnienia prawidłowego wyświetlania.

#### Pismo tamilskie

- **Przegląd**: Użyj „Vijaya” dla znaków tamilskich, jeśli podstawowa czcionka nie jest obsługiwana.

**Etapy wdrażania:**

##### Krok 1: Zdefiniuj zakres Unicode
```csharp
uint startUnicodeIndexTamil = 0x0B80; // Początek zasięgu języka tamilskiego
uint endUnicodeIndexTamil = 0x0BFF;   // Koniec zasięgu języka tamilskiego
```
Ten fragment kodu definiuje zakres Unicode dla znaków języka tamilskiego.

##### Krok 2: Utwórz regułę zapasową
```csharp
IFontFallBackRule tamilFallbackRule = new FontFallBackRule(startUnicodeIndexTamil, endUnicodeIndexTamil, "Vijaya");
```
Tutaj tworzymy regułę awaryjną, używając „Vijaya” jako czcionki alternatywnej.

#### japoński hiragana

- **Przegląd**: W przypadku nieobsługiwanych znaków Hiragana należy używać skrótu „MS Mincho” lub „MS Gothic”.

**Etapy wdrażania:**

##### Krok 1: Zdefiniuj zakres Unicode
```csharp
uint startUnicodeIndexHiragana = 0x3040; // Początek zakresu Hiragana
uint endUnicodeIndexHiragana = 0x309F;   // Koniec zakresu Hiragana
```
Ten fragment kodu ustala granice Unicode dla znaków Hiragana.

##### Krok 2: Utwórz regułę zapasową
```csharp
IFontFallBackRule hiraganaFallbackRule = new FontFallBackRule(startUnicodeIndexHiragana, endUnicodeIndexHiragana, "MS Mincho, MS Gothic");
```
Ta reguła określa wiele czcionek zapasowych dla znaków Hiragana.

#### Znaki Emoji

- **Przegląd**: Upewnij się, że emotikony są wyświetlane przy użyciu odpowiednich czcionek, takich jak „Segoe UI Emoji”.

**Etapy wdrażania:**

##### Krok 1: Zdefiniuj zakres Unicode
```csharp
uint startUnicodeIndexEmoji = 0x1F300; // Początek zakresu emoji
uint endUnicodeIndexEmoji = 0x1F64F;   // Koniec zakresu emoji
```
Definiuje zakres Unicode dla emoji.

##### Krok 2: Utwórz regułę zapasową
```csharp
string[] fontNamesEmoji = { "Segoe UI Emoji, Segoe UI Symbol\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}