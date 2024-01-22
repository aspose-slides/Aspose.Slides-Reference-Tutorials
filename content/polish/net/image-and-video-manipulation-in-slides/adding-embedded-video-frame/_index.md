---
title: Aspose.Slides - Dodawanie osadzonych filmów wideo w prezentacjach .NET
linktitle: Aspose.Slides - Dodawanie osadzonych filmów wideo w prezentacjach .NET
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ulepsz swoje prezentacje dzięki osadzonym filmom za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 19
url: /pl/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Wstęp
W dynamicznym świecie prezentacji integracja elementów multimedialnych może znacząco zwiększyć zaangażowanie. Aspose.Slides dla .NET zapewnia potężne rozwiązanie do włączania osadzonych klatek wideo do slajdów prezentacji. Ten samouczek przeprowadzi Cię przez cały proces, szczegółowo opisując każdy krok, aby zapewnić płynną obsługę.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
-  Biblioteka Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę z[strona wydania](https://releases.aspose.com/slides/net/).
- Treść multimedialna: Przygotuj plik wideo (np. „Wildlife.mp4”), który chcesz umieścić w swojej prezentacji.
## Importuj przestrzenie nazw
Rozpocznij od zaimportowania niezbędnych przestrzeni nazw do projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj katalogi
Upewnij się, że Twój projekt zawiera wymagane katalogi na pliki dokumentów i multimediów:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Utwórz katalog, jeśli jeszcze nie istnieje.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 2: Utwórz instancję klasy prezentacji
Utwórz instancję klasy Prezentacja reprezentującą plik PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Zdobądź pierwszy slajd
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
Gratulacje! Pomyślnie dodałeś osadzoną klatkę wideo do swojej prezentacji za pomocą Aspose.Slides dla .NET. Ta dynamiczna funkcja może wynieść Twoje prezentacje na nowy poziom, urzekając odbiorców elementami multimedialnymi płynnie zintegrowanymi ze slajdami.
## Często zadawane pytania
### Czy mogę osadzić filmy w dowolnym slajdzie prezentacji?
 Tak, możesz wybrać dowolny slajd, modyfikując indeks w`pres.Slides[index]`.
### Jakie formaty wideo są obsługiwane?
Aspose.Slides obsługuje wiele formatów wideo, w tym MP4, AVI i WMV.
### Czy mogę dostosować rozmiar i położenie klatki wideo?
 Absolutnie! Dostosuj parametry w`AddVideoFrame(x, y, width, height, video)` w razie potrzeby.
### Czy istnieje ograniczenie liczby filmów, które mogę umieścić?
Liczba osadzonych filmów jest zazwyczaj ograniczona możliwościami oprogramowania do prezentacji.
### Jak mogę uzyskać dalszą pomoc lub podzielić się swoim doświadczeniem?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności i dyskusje.