---
title: Opanowywanie animacji programu PowerPoint za pomocą Aspose.Slides .NET
linktitle: Powtórz animację na slajdzie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ulepsz prezentacje programu PowerPoint za pomocą Aspose.Slides dla .NET. Steruj animacjami bez wysiłku, zachwyć odbiorców i zostaw trwałe wrażenie.
weight: 12
url: /pl/net/slide-animation-control/repeat-animation-on-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowywanie animacji programu PowerPoint za pomocą Aspose.Slides .NET

## Wstęp
W dynamicznym świecie prezentacji umiejętność kontrolowania animacji odgrywa kluczową rolę w angażowaniu i przyciąganiu uwagi publiczności. Aspose.Slides dla .NET umożliwia programistom przejmowanie kontroli nad typami animacji na slajdach, umożliwiając bardziej interaktywną i atrakcyjną wizualnie prezentację. W tym samouczku odkryjemy krok po kroku, jak kontrolować typy animacji na slajdzie za pomocą Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Biblioteka Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę z[Tutaj](https://releases.aspose.com/slides/net/).
2. Środowisko programistyczne .NET: Skonfiguruj środowisko programistyczne .NET na swoim komputerze.
## Importuj przestrzenie nazw
W projekcie .NET rozpocznij od zaimportowania niezbędnych przestrzeni nazw, aby wykorzystać funkcje zapewniane przez Aspose.Slides:
```csharp
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj projekt
Utwórz nowy katalog dla swojego projektu i utwórz instancję klasy Prezentacja, która będzie reprezentować plik prezentacji.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "AnimationOnSlide.pptx"))
{
    // Twój kod trafia tutaj
}
```
## Krok 2: Sekwencja efektów dostępu
Pobierz sekwencję efektów dla pierwszego slajdu, używając właściwości MainSequence.
```csharp
ISequence effectsSequence = pres.Slides[0].Timeline.MainSequence;
```
## Krok 3: Uzyskaj dostęp do pierwszego efektu
Uzyskaj pierwszy efekt ciągu głównego, aby manipulować jego właściwościami.
```csharp
IEffect effect = effectsSequence[0];
```
## Krok 4: Zmodyfikuj ustawienia powtarzania
Zmień właściwość Timing/Repeat efektu na „Do końca slajdu”.
```csharp
effect.Timing.RepeatUntilEndSlide = true;
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację, aby zwizualizować zmiany.
```csharp
pres.Save(RunExamples.OutPath + "AnimationOnSlide-out.pptx", Aspose.Slides.Export.SaveFormat.Pptx);
```
Powtórz te kroki, aby uzyskać dodatkowe efekty lub dostosuj je do wymagań prezentacji.
## Wniosek
Włączanie dynamicznych animacji do prezentacji programu PowerPoint nigdy nie było łatwiejsze dzięki Aspose.Slides dla .NET. Ten przewodnik krok po kroku wyposaży Cię w wiedzę niezbędną do kontrolowania typów animacji, dzięki czemu Twoje slajdy pozostawią trwałe wrażenie na widzach.
## Często Zadawane Pytania
### Czy mogę zastosować te animacje do określonych obiektów na slajdzie?
Tak, możesz celować w określone obiekty, uzyskując dostęp do ich indywidualnych efektów w sekwencji.
### Czy Aspose.Slides jest kompatybilny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides zapewnia obsługę szerokiej gamy wersji programu PowerPoint, zapewniając kompatybilność zarówno ze starymi, jak i nowymi wersjami.
### Gdzie mogę znaleźć dodatkowe przykłady i zasoby?
 Poznaj[dokumentacja](https://reference.aspose.com/slides/net/) wyczerpujące przykłady i szczegółowe wyjaśnienia.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
 Odwiedzać[Tutaj](https://purchase.aspose.com/temporary-license/) w celu uzyskania informacji na temat uzyskania licencji tymczasowej.
### Potrzebujesz pomocy lub masz więcej pytań?
 Nawiąż kontakt ze społecznością Aspose.Slides na stronie[forum wsparcia](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
