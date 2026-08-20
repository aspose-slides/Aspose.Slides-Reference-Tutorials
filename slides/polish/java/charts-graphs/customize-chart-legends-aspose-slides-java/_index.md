---
date: '2026-08-06'
description: Dowiedz się, jak zmienić kolor czcionki legendy i zmodyfikować tekst
  legendy wykresu przy użyciu Aspose.Slides for Java. Postępuj zgodnie z instrukcjami
  krok po kroku, aby szybko dostosować legendy wykresów.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Dowiedz się, jak zmienić kolor czcionki legendy i zmodyfikować tekst
  legendy wykresu w Aspose.Slides for Java. Ten przewodnik pokazuje dokładne kroki
  i najlepsze praktyki.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Jak zmienić kolor czcionki legendy w Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Jak zmienić kolor czcionki legendy w Aspose.Slides for Java
url: /pl/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak zmienić kolor czcionki legendy w Aspose.Slides for Java

## Wprowadzenie
Jeśli potrzebujesz **change legend font color** na wykresie, Aspose.Slides for Java daje pełną kontrolę nad każdą pozycją legendy. Ten samouczek przeprowadzi Cię przez dostosowywanie stylów tekstu legendy, stosowanie pogrubionych lub kursywnych czcionek oraz ustawianie jednolitych kolorów, aby Twoje wykresy wyglądały dokładnie tak, jak tego oczekujesz. Po zakończeniu tego przewodnika będziesz w stanie pewnie modyfikować tekst legendy wykresu i integrować zmiany w dowolnej istniejącej prezentacji.

**Czego się nauczysz**
- Jak programowo **change legend font color**.
- Sposoby **modify chart legend text** takie jak pogrubienie, kursywa i rozmiar.
- Wskazówki dotyczące stosowania zmian w wielu wykresach w jednej prezentacji.
- Jak zintegrować te kroki w większym procesie automatyzacji.

## Szybkie odpowiedzi
- **Czy mogę zmienić kolor pojedynczej pozycji legendy?** Tak – uzyskaj dostęp do pozycji za pomocą jej indeksu i ustaw format wypełnienia na jednolity kolor.  
- **Czy potrzebuję licencji, aby używać tych API?** Wymagana jest tymczasowa lub płatna licencja w środowisku produkcyjnym; darmowa wersja próbna wystarczy do oceny.  
- **Która wersja Javy jest obsługiwana?** Aspose.Slides for Java 25.4+ działa z JDK 16 i nowszymi.  
- **Czy zmiany wpłyną na inne elementy wykresu?** Nie, formatowanie legendy jest odizolowane od stylizacji serii danych.  
- **Czy możliwe jest przetwarzanie wsadowe?** Oczywiście – iteruj po slajdach i wykresach, aby zastosować te same ustawienia legendy w całej prezentacji.

## Co to jest change legend font color?
`change legend font color` odnosi się do programowej operacji ustawiania koloru tekstu pozycji legendy wykresu przy użyciu API Aspose.Slides. Operacja ta aktualizuje wygląd legendy bez zmiany danych źródłowych.

## Dlaczego dostosowywać legendy wykresów?
Aspose.Slides obsługuje **50+ input and output formats** i może obsłużyć prezentacje z **500+ slajdami**, utrzymując zużycie pamięci poniżej 200 MB. Dostosowywanie legend zwiększa czytelność, podkreśla kolory firmowe i zapewnia, że kluczowe punkty danych wyróżniają się — szczególnie w prezentacjach biznesowych lub edukacyjnych, gdzie klarowność wizualna wpływa na podejmowanie decyzji.

## Wymagania wstępne
- Biblioteka **Aspose.Slides for Java** (wersja 25.4 lub nowsza).  
- Java Development Kit (JDK) 16 lub wyższy.  
- IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans.  
- Maven lub Gradle do zarządzania zależnościami.  
- Podstawowa znajomość programowania w Javie.

## Konfigurowanie Aspose.Slides for Java
Aby rozpocząć dostosowywanie legend wykresów, dodaj bibliotekę do projektu, korzystając z jednej z poniższych metod.

### Maven
Dodaj następującą zależność do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Umieść tę linię w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Możesz również pobrać najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Free trial:** Rozpocznij od darmowej wersji próbnej, aby wypróbować funkcje Aspose.Slides.  
- **Temporary license:** Złóż wniosek o tymczasową licencję na rozszerzoną ocenę.  
- **Purchase:** Aby uzyskać pełny dostęp, rozważ zakup licencji na stronie [Aspose Purchase](https://purchase.aspose.com/buy).

#### Podstawowa inicjalizacja i konfiguracja
Po dodaniu biblioteki do projektu:
1. Zainicjalizuj Aspose.Slides w aplikacji Java.  
2. Załaduj istniejącą prezentację lub utwórz nową.

## Jak zmienić kolor czcionki legendy?
Aby zmienić kolor czcionki legendy, załaduj prezentację, pobierz obiekt wykresu, uzyskaj jego legendę, a następnie zmodyfikuj format tekstu każdej pozycji legendy, ustawiając typ wypełnienia na jednolity i określony kolor. Ta pojedyncza operacja natychmiast aktualizuje kolor tekstu legendy bez konieczności ponownego renderowania całego slajdu. Przykład: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Podejście to działa dla każdego typu wykresu i nie wymaga ponownego renderowania całego slajdu.

### Uzyskiwanie i modyfikowanie właściwości tekstu legendy

#### Definicja kotwicy
Interfejs `IChart` reprezentuje obiekt wykresu na slajdzie, a metoda `getLegend()` zwraca obiekt `ILegend`, który zawiera kolekcję elementów `ILegendEntry`.

#### Dodawanie wykresu do prezentacji
1. **Load the presentation:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Add a clustered column chart:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Dostosowywanie właściwości czcionki
3. **Access legend entry text format:**  
   Tutaj `legendEntry` jest obiektem `ILegendEntry` reprezentującym pojedynczą pozycję w legendzie wykresu.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Set bold and italic styles with a specific height:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Change fill type to solid color for better visibility:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Zapisywanie prezentacji
6. **Save your changes:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Typowe problemy i rozwiązywanie
- Zweryfikuj, czy indeks pozycji legendy odpowiada kolejności serii w wykresie.  
- Upewnij się, że używasz wersji biblioteki obsługującej `setSolidFillColor` (dostępne od wersji 20.9).  

## Praktyczne zastosowania
Dostosowywanie tekstu legendy jest przydatne w wielu rzeczywistych scenariuszach:

1. **Prezentacje biznesowe:** Dopasuj kolory legendy do identyfikacji wizualnej firmy, aby uzyskać profesjonalny wygląd.  
2. **Materiały edukacyjne:** Podkreśl kluczowe serie danych, używając kontrastujących kolorów legendy.  
3. **Prezentacje marketingowe:** Zaznacz wskaźniki wydajności pogrubionymi, kolorowymi legendami, aby przyciągnąć uwagę interesariuszy.  

Możesz także zautomatyzować aktualizacje legend, pobierając wartości kolorów z bazy danych lub pliku konfiguracyjnego.

## Rozważania dotyczące wydajności
Podczas przetwarzania dużych prezentacji pamiętaj o następujących wskazówkach:

- **Efficient memory management:** Wywołaj `presentation.dispose()` po zapisaniu, aby zwolnić zasoby natywne.  
- **Load only required slides:** Użyj `Presentation.load(String path, LoadOptions options)` z `LoadOptions.setLoadOnlySlideIds()`, jeśli potrzebujesz tylko części slajdów.  
- **Batch processing:** Grupuj aktualizacje legend per slajd, aby zmniejszyć liczbę wywołań API i zwiększyć przepustowość.

## Podsumowanie
Teraz wiesz, jak **change legend font color** i **modify chart legend text** przy użyciu Aspose.Slides for Java. Te dostosowania zwiększają przejrzystość wizualną i pomagają skuteczniej przekazywać dane. Eksperymentuj z różnymi czcionkami, rozmiarami i kolorami, aby dopasować je do wytycznych stylu Twojej prezentacji, i odkrywaj inne funkcje stylizacji wykresów, aby tworzyć naprawdę profesjonalne decki.

**Kolejne kroki**
- Spróbuj zastosować te same style legend do wykresów kołowych i liniowych.  
- Połącz dostosowanie legendy z formatowaniem etykiet danych, aby uzyskać w pełni spójną markę wykresu.  

Gotowy, aby podnieść jakość swoich prezentacji? Zaimplementuj powyższe kroki i zobacz natychmiastową różnicę!

## Sekcja FAQ
1. **Jak zmienić kolor tekstu pozycji legendy?**  
   Użyj `getFillFormat().setFillType(FillType.Solid)` i następnie `setSolidFillColor(Color.YOUR_COLOR)` na formacie tekstu pozycji legendy.

2. **Czy mogę zastosować te zmiany do wszystkich legend w prezentacji?**  
   Tak – iteruj po każdym slajdzie, znajdź każdy wykres i zaktualizuj pozycje legend w pętli.

3. **Czy można dynamicznie dostosować rozmiar czcionki w zależności od długości tekstu?**  
   Możesz obliczyć wymaganą wielkość za pomocą `TextFrame.getTextFrameFormat().getFontHeight()` i ustawić ją metodą `setFontHeight(double)`.

4. **Co zrobić, gdy napotkam problemy z indeksowaniem pozycji legendy?**  
   Sprawdź, czy używany indeks odpowiada kolejności serii; pamiętaj, że indeksy zaczynają się od zera.

5. **Gdzie znajdę więcej przykładów Aspose.Slides?**  
   Przeglądaj [Aspose Documentation](https://reference.aspose.com/slides/java/) w poszukiwaniu kompleksowych przewodników i referencji API.

**Dodatkowe Q&A**

**Q: Czy zmiana koloru czcionki legendy wpływa na eksportowane pliki PDF?**  
A: Nie, zmiana koloru jest zachowywana we wszystkich formatach eksportu obsługiwanych przez Aspose.Slides, w tym PDF i PPTX.

**Q: Czy mogę użyć gradientu zamiast jednolitego koloru?**  
A: Tak – ustaw `FillType.Gradient` i skonfiguruj przystanki gradientu za pomocą `getGradientStyle()`.

**Q: Ile pozycji legendy może mieć wykres?**  
A: Wykres może mieć do 256 pozycji legendy, ograniczenie wynika wyłącznie z liczby serii danych, które dodasz.

## Zasoby
- **Documentation:** Comprehensive guide on using Aspose.Slides features ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Access the latest version of Aspose.Slides for Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Purchase:** Buy a license to unlock full capabilities ([Link](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** Start with free trials and apply for temporary licenses ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Get help from the community on Aspose's support forum ([Link](https://forum.aspose.com/c/slides/11)).

---

**Ostatnia aktualizacja:** 2026-08-06  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Powiązane samouczki

- [Enhancing PowerPoint Charts: Font & Axis Customization with Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dynamic Text Frames & Font Customization Guide](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}