---
"description": "Dowiedz się, jak ustawić Root Directory ClsId w Aspose.Slides dla prezentacji Java. Dostosuj zachowanie hiperłącza za pomocą CLSID."
"linktitle": "Katalog główny ClsId w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Katalog główny ClsId w slajdach Java"
"url": "/pl/java/media-controls/root-directory-clsid-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Katalog główny ClsId w slajdach Java


## Wprowadzenie do ustawiania ClsId katalogu głównego w Aspose.Slides dla Java

Aspose.Slides for Java możesz ustawić Root Directory ClsId, czyli CLSID (Class Identifier) używany do określania aplikacji, która ma być używana jako katalog główny, gdy hiperłącze w prezentacji zostanie aktywowane. W tym przewodniku przeprowadzimy Cię przez proces krok po kroku.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została dodana do Twojego projektu. Możesz ją pobrać z [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).
- Edytor kodu lub zintegrowane środowisko programistyczne (IDE) przeznaczone do programowania w języku Java.

## Krok 1: Utwórz nową prezentację

Najpierw utwórzmy nową prezentację za pomocą Aspose.Slides dla Java. W tym przykładzie utworzymy pustą prezentację.

```java
// Nazwa pliku wyjściowego
String resultPath = "your_output_path/pres.ppt"; // Zastąp „your_output_path” żądanym katalogiem wyjściowym.
Presentation pres = new Presentation();
```

powyższym kodzie definiujemy ścieżkę do pliku prezentacji wyjściowej i tworzymy nowy `Presentation` obiekt.

## Krok 2: Ustaw ClsId katalogu głównego

Aby ustawić identyfikator ClsId katalogu głównego, należy utworzyć wystąpienie `PptOptions` i ustaw żądany CLSID. CLSID reprezentuje aplikację, która będzie używana jako katalog główny, gdy hiperłącze zostanie aktywowane.

```java
PptOptions pptOptions = new PptOptions();
// Ustaw CLSID na 'Microsoft Powerpoint.Show.8'
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

W powyższym kodzie tworzymy `PptOptions` obiekt i ustaw CLSID na 'Microsoft Powerpoint.Show.8'. Możesz go zastąpić CLSID aplikacji, której chcesz użyć jako katalogu głównego.

## Krok 3: Zapisz prezentację

Teraz zapiszmy prezentację z ustawionym parametrem ClsId katalogu głównego.

```java
// Zapisz prezentację
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

W tym kroku zapisujemy prezentację do wskazanego miejsca `resultPath` z `PptOptions` stworzyliśmy wcześniej.

## Krok 4: Czyszczenie

Nie zapomnij pozbyć się `Presentation` sprzeciwić się zwolnieniu przydzielonych zasobów.

```java
if (pres != null) {
    pres.dispose();
}
```

## Kompletny kod źródłowy dla katalogu głównego ClsId w slajdach Java

```java
// Nazwa pliku wyjściowego
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	// ustaw CLSID na 'Microsoft Powerpoint.Show.8'
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Zapisz prezentację
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Wniosek

Udało Ci się ustawić Root Directory ClsId w Aspose.Slides dla Java. Pozwala to określić aplikację, która będzie używana jako katalog główny, gdy hiperłącza zostaną aktywowane w prezentacji. Możesz dostosować CLSID zgodnie ze swoimi konkretnymi wymaganiami.

## Najczęściej zadawane pytania

### Jak znaleźć identyfikator CLSID konkretnej aplikacji?

Aby znaleźć CLSID dla konkretnej aplikacji, możesz zapoznać się z dokumentacją lub zasobami dostarczonymi przez dewelopera aplikacji. CLSID to unikalne identyfikatory przypisane do obiektów COM i są zazwyczaj specyficzne dla każdej aplikacji.

### Czy mogę ustawić niestandardowy identyfikator CLSID dla katalogu głównego?

Tak, możesz ustawić niestandardowy identyfikator CLSID dla katalogu głównego, określając żądaną wartość identyfikatora CLSID za pomocą `setRootDirectoryClsid` metoda, jak pokazano w przykładzie kodu. Pozwala to na użycie konkretnej aplikacji jako katalogu głównego, gdy hiperłącza są aktywowane w prezentacji.

### Co się stanie, jeśli nie ustawię ClsId katalogu głównego?

Jeśli nie ustawisz Root Directory ClsId, domyślne zachowanie będzie zależeć od przeglądarki lub aplikacji użytej do otwarcia prezentacji. Może ona używać własnej domyślnej aplikacji jako katalogu głównego, gdy hiperłącza są aktywowane.

### Czy mogę zmienić identyfikator ClsId katalogu głównego dla poszczególnych hiperłączy?

Nie, Root Directory ClsId jest zazwyczaj ustawiany na poziomie prezentacji i dotyczy wszystkich hiperłączy w prezentacji. Jeśli musisz określić różne aplikacje dla poszczególnych hiperłączy, może być konieczne oddzielne obsłużenie tych hiperłączy w kodzie.

### Czy istnieją jakieś ograniczenia co do identyfikatorów CLSID, których mogę używać?

Identyfikatory CLSID, których możesz użyć, są zazwyczaj określane przez aplikacje zainstalowane w systemie. Powinieneś używać identyfikatorów CLSID odpowiadających prawidłowym aplikacjom, które mogą obsługiwać hiperłącza. Pamiętaj, że użycie nieprawidłowego identyfikatora CLSID może skutkować nieoczekiwanym zachowaniem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}