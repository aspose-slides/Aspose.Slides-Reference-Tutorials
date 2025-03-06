---
title: Tworzenie miniatury notatki podrzędnej SmartArt w Aspose.Slides
linktitle: Tworzenie miniatury notatki podrzędnej SmartArt w Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak tworzyć urzekające miniatury notatek podrzędnych SmartArt za pomocą Aspose.Slides dla .NET. Ulepsz swoje prezentacje dzięki dynamicznym efektom wizualnym!
weight: 15
url: /pl/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
dziedzinie prezentacji dynamicznych Aspose.Slides dla .NET wyróżnia się jako potężne narzędzie, zapewniające programistom możliwość programowego manipulowania i ulepszania prezentacji PowerPoint. Intrygującą funkcją jest możliwość generowania miniatur dla notatek podrzędnych SmartArt, dodając warstwę atrakcyjności wizualnej do prezentacji. Ten przewodnik krok po kroku przeprowadzi Cię przez proces tworzenia miniaturek notatek podrzędnych SmartArt przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Slides dla .NET: Upewnij się, że biblioteka Aspose.Slides jest zintegrowana z projektem .NET. Jeśli nie, pobierz go z[strona z wydaniami](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj działające środowisko programistyczne .NET i posiadaj podstawową wiedzę na temat programowania w języku C#.
- Przykładowa prezentacja: Utwórz lub uzyskaj prezentację programu PowerPoint zawierającą grafikę SmartArt z notatkami podrzędnymi do przetestowania.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do projektu C#. Te przestrzenie nazw zapewniają dostęp do klas i metod potrzebnych do pracy z Aspose.Slides.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## Krok 1: Utwórz instancję klasy prezentacji
 Rozpocznij od utworzenia instancji`Presentation` class, reprezentujący plik PPTX, z którym będziesz pracować.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## Krok 2: Dodaj grafikę SmartArt
 Teraz dodaj grafikę SmartArt do slajdu w prezentacji. W tym przykładzie używamy`BasicCycle` układ.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 3: Uzyskaj odniesienie do węzła
Aby pracować z określonym węzłem w SmartArt, uzyskaj jego odniesienie za pomocą jego indeksu.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## Krok 4: Uzyskaj miniaturę
Pobierz miniaturę notatki podrzędnej w węźle SmartArt.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## Krok 5: Zapisz miniaturę
Zapisz wygenerowaną miniaturę w określonym katalogu.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Powtórz te kroki dla każdego węzła grafiki SmartArt w prezentacji, dostosowując układ i style według potrzeb.
## Wniosek
Podsumowując, Aspose.Slides dla .NET umożliwia programistom łatwe tworzenie angażujących prezentacji. Możliwość generowania miniatur dla notatek podrzędnych SmartArt zwiększa atrakcyjność wizualną prezentacji, zapewniając dynamiczne i interaktywne doświadczenie użytkownika.
## Często Zadawane Pytania
### P: Czy mogę dostosować rozmiar i format wygenerowanej miniatury?
O: Tak, możesz dostosować wymiary i format miniatury, modyfikując odpowiednie parametry w kodzie.
### P: Czy Aspose.Slides obsługuje inne układy SmartArt?
Odp.: Absolutnie! Aspose.Slides oferuje różnorodne układy SmartArt, dzięki czemu możesz wybrać ten, który najlepiej odpowiada Twoim potrzebom w zakresie prezentacji.
### P: Czy dostępna jest licencja tymczasowa do celów testowych?
 Odpowiedź: Tak, możesz uzyskać tymczasową licencję od[Tutaj](https://purchase.aspose.com/temporary-license/) do testowania i oceny.
### P: Gdzie mogę szukać pomocy lub nawiązać kontakt ze społecznością Aspose.Slides?
 O: Odwiedź[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) aby nawiązać kontakt ze społecznością, zadawać pytania i znajdować rozwiązania.
### P: Czy mogę kupić Aspose.Slides dla .NET?
 Odp.: Oczywiście! Poznaj opcje zakupu[Tutaj](https://purchase.aspose.com/buy) aby odblokować pełny potencjał Aspose.Slides w swoich projektach.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
