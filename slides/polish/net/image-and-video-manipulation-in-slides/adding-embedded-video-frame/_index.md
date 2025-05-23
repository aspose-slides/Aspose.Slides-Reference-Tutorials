---
"description": "Ulepsz swoje prezentacje za pomocą osadzonych filmów za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację."
"linktitle": "Aspose.Slides — dodawanie osadzonych filmów wideo w prezentacjach .NET"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Aspose.Slides — dodawanie osadzonych filmów wideo w prezentacjach .NET"
"url": "/pl/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — dodawanie osadzonych filmów wideo w prezentacjach .NET

## Wstęp
W dynamicznym świecie prezentacji integrowanie elementów multimedialnych może znacznie zwiększyć zaangażowanie. Aspose.Slides dla .NET zapewnia potężne rozwiązanie do włączania osadzonych ramek wideo do slajdów prezentacji. Ten samouczek przeprowadzi Cię przez proces, rozbijając każdy krok, aby zapewnić płynne działanie.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące rzeczy:
- Biblioteka Aspose.Slides dla platformy .NET: Pobierz i zainstaluj bibliotekę z [strona wydania](https://releases.aspose.com/slides/net/).
- Treść multimedialna: Posiadasz plik wideo (np. „Wildlife.mp4”), który chcesz osadzić w swojej prezentacji.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do swojego projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj katalogi
Upewnij się, że Twój projekt posiada wymagane katalogi dla plików dokumentów i multimediów:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Utwórz katalog, jeśli jeszcze go nie ma.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 2: Utwórz klasę prezentacji
Utwórz instancję klasy Presentation, aby reprezentować plik PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Zobacz pierwszy slajd
    ISlide sld = pres.Slides[0];
```
## Krok 3: Umieść wideo w prezentacji
Użyj poniższego kodu, aby osadzić wideo w prezentacji:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 4: Dodaj klatkę wideo
Teraz dodaj klatkę wideo do slajdu:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## Krok 5: Ustaw właściwości wideo
Ustaw wideo na klatkę wideo i skonfiguruj tryb odtwarzania oraz głośność:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## Krok 6: Zapisz prezentację
Na koniec zapisz plik PPTX na dysku:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Powtórz te kroki dla każdego filmu, który chcesz osadzić w prezentacji.
## Wniosek
Gratulacje! Udało Ci się dodać osadzoną klatkę wideo do prezentacji za pomocą Aspose.Slides dla .NET. Ta dynamiczna funkcja może wznieść Twoje prezentacje na nowe wyżyny, oczarowując odbiorców elementami multimedialnymi płynnie zintegrowanymi ze slajdami.
## Często zadawane pytania
### Czy mogę osadzić filmy w dowolnym slajdzie prezentacji?
Tak, możesz wybrać dowolny slajd, modyfikując indeks w `pres.Slides[index]`.
### Jakie formaty wideo są obsługiwane?
Aspose.Slides obsługuje wiele formatów wideo, w tym MP4, AVI i WMV.
### Czy mogę dostosować rozmiar i położenie klatki wideo?
Oczywiście! Dostosuj parametry w `AddVideoFrame(x, y, width, height, video)` w razie potrzeby.
### Czy istnieje ograniczenie liczby filmów, które mogę osadzić?
Liczba osadzonych filmów wideo jest zazwyczaj ograniczona pojemnością oprogramowania do prezentacji.
### Jak mogę uzyskać dalszą pomoc lub podzielić się swoim doświadczeniem?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania wsparcia społeczności i dyskusji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}