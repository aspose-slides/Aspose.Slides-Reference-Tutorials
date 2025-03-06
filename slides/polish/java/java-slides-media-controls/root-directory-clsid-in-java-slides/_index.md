---
title: Katalog główny ClsId w slajdach Java
linktitle: Katalog główny ClsId w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić ClsId katalogu głównego w Aspose.Slides dla prezentacji Java. Dostosuj zachowanie hiperłącza za pomocą identyfikatora CLSID.
type: docs
weight: 10
url: /pl/java/media-controls/root-directory-clsid-in-java-slides/
---

## Wprowadzenie do ustawiania katalogu głównego ClsId w Aspose.Slides dla Java

W Aspose.Slides for Java możesz ustawić Root Directory ClsId, który jest identyfikatorem CLSID (identyfikatorem klasy) używanym do określenia aplikacji, która ma być używana jako katalog główny po aktywowaniu hiperłącza w prezentacji. W tym przewodniku przeprowadzimy Cię krok po kroku, jak to zrobić.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Do Twojego projektu dodano bibliotekę Aspose.Slides for Java. Można go pobrać z[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).
- Edytor kodu lub zintegrowane środowisko programistyczne (IDE) skonfigurowane do programowania w języku Java.

## Krok 1: Utwórz nową prezentację

Najpierw utwórzmy nową prezentację za pomocą Aspose.Slides dla Java. W tym przykładzie utworzymy pustą prezentację.

```java
// Nazwa pliku wyjściowego
String resultPath = "your_output_path/pres.ppt"; // Zastąp „twoja_ścieżka_wyjściowa” żądanym katalogiem wyjściowym.
Presentation pres = new Presentation();
```

 powyższym kodzie definiujemy ścieżkę do wyjściowego pliku prezentacji i tworzymy nowy`Presentation` obiekt.

## Krok 2: Ustaw katalog główny ClsId

 Aby ustawić ClsId katalogu głównego, musisz utworzyć instancję`PptOptions` i ustaw żądany identyfikator CLSID. Identyfikator CLSID reprezentuje aplikację, która będzie używana jako katalog główny po aktywowaniu hiperłącza.

```java
PptOptions pptOptions = new PptOptions();
// Ustaw CLSID na „Microsoft Powerpoint.Show.8”
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 W powyższym kodzie tworzymy plik`PptOptions` obiekt i ustaw identyfikator CLSID na „Microsoft Powerpoint.Show.8”. Możesz zastąpić go identyfikatorem CLSID aplikacji, której chcesz używać jako katalogu głównego.

## Krok 3: Zapisz prezentację

Teraz zapiszmy prezentację z ustawionym identyfikatorem ClsId katalogu głównego.

```java
// Zapisz prezentację
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 W tym kroku zapisujemy prezentację w określonym formacie`resultPath` z`PptOptions` stworzyliśmy wcześniej.

## Krok 4: Oczyszczanie

 Nie zapomnij pozbyć się`Presentation` sprzeciwić się zwolnieniu przydzielonych zasobów.

```java
if (pres != null) {
    pres.dispose();
}
```

## Kompletny kod źródłowy katalogu głównego ClsId w slajdach Java

```java
// Nazwa pliku wyjściowego
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//ustaw CLSID na „Microsoft Powerpoint.Show.8”
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Zapisz prezentację
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Wniosek

Pomyślnie ustawiłeś katalog główny ClsId w Aspose.Slides dla Java. Dzięki temu możesz określić aplikację, która będzie używana jako katalog główny, gdy w Twojej prezentacji zostaną aktywowane hiperłącza. Możesz dostosować identyfikator CLSID zgodnie ze swoimi konkretnymi wymaganiami.

## Często zadawane pytania

### Jak znaleźć identyfikator CLSID dla konkretnej aplikacji?

Aby znaleźć identyfikator CLSID dla konkretnej aplikacji, możesz zapoznać się z dokumentacją lub zasobami dostarczonymi przez programistę aplikacji. Identyfikatory CLSID to unikalne identyfikatory przypisane do obiektów COM i zazwyczaj są specyficzne dla każdej aplikacji.

### Czy mogę ustawić niestandardowy identyfikator CLSID dla katalogu głównego?

 Tak, możesz ustawić niestandardowy identyfikator CLSID dla katalogu głównego, określając żądaną wartość CLSID za pomocą`setRootDirectoryClsid` metodę, jak pokazano w przykładzie kodu. Dzięki temu możesz użyć określonej aplikacji jako katalogu głównego, gdy w prezentacji zostaną aktywowane hiperłącza.

### Co się stanie, jeśli nie ustawię ClsId katalogu głównego?

Jeśli nie ustawisz identyfikatora katalogu głównego ClsId, domyślne zachowanie będzie zależeć od przeglądarki lub aplikacji użytej do otwarcia prezentacji. Może używać własnej domyślnej aplikacji jako katalogu głównego, gdy aktywowane są hiperłącza.

### Czy mogę zmienić identyfikator ClsId katalogu głównego dla poszczególnych hiperłączy?

Nie, identyfikator ClsId katalogu głównego jest zwykle ustawiany na poziomie prezentacji i ma zastosowanie do wszystkich hiperłączy w prezentacji. Jeśli chcesz określić różne zastosowania dla poszczególnych hiperłączy, może być konieczne osobne obsłużenie tych hiperłączy w kodzie.

### Czy są jakieś ograniczenia dotyczące identyfikatorów CLSID, których mogę używać?

Identyfikatory CLSID, których można użyć, są zazwyczaj określane przez aplikacje zainstalowane w systemie. Należy używać identyfikatorów CLSID odpowiadających prawidłowym aplikacjom obsługującym hiperłącza. Należy pamiętać, że użycie nieprawidłowego identyfikatora CLSID może spowodować nieoczekiwane zachowanie.