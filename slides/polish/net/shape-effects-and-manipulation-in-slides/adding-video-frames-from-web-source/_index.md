---
title: Samouczek osadzania klatek wideo w Aspose.Slides dla .NET
linktitle: Dodawanie klatek wideo ze źródła internetowego do slajdów prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak bezproblemowo osadzać klatki wideo w slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Bez wysiłku wzbogacaj prezentacje multimediami.
type: docs
weight: 20
url: /pl/net/shape-effects-and-manipulation-in-slides/adding-video-frames-from-web-source/
---
## Wstęp
dynamicznym świecie prezentacji włączenie elementów multimedialnych może znacząco zwiększyć zaangażowanie i dostarczyć wpływowy przekaz. Skutecznym sposobem osiągnięcia tego celu jest osadzanie klatek wideo w slajdach prezentacji. W tym samouczku omówimy, jak bezproblemowo to osiągnąć, używając Aspose.Slides dla .NET. Aspose.Slides to solidna biblioteka, która umożliwia programistom programowe manipulowanie prezentacjami programu PowerPoint, zapewniając szerokie możliwości tworzenia, edytowania i ulepszania slajdów.
## Warunki wstępne
Zanim zagłębisz się w samouczek, upewnij się, że masz następujące elementy:
1.  Biblioteka Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę z[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/).
2. Przykładowy plik wideo: Przygotuj plik wideo, który chcesz umieścić w swojej prezentacji. Możesz użyć podanego przykładu z filmem o nazwie „Wildlife.mp4”.
## Importuj przestrzenie nazw
W swoim projekcie .NET uwzględnij niezbędne przestrzenie nazw, aby wykorzystać funkcjonalności Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Podzielmy proces osadzania klatek wideo na slajdach prezentacji przy użyciu Aspose.Slides dla .NET na łatwe do wykonania kroki:
## Krok 1: Skonfiguruj katalogi
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(RunExamples.OutPath, "VideoFrame_out.pptx");
// Utwórz katalog, jeśli jeszcze nie istnieje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Pamiętaj, aby zastąpić „Twój katalog dokumentów” i „Twój katalog multimediów” odpowiednimi ścieżkami w swoim projekcie.
## Krok 2: Utwórz obiekt prezentacji
```csharp
using (Presentation pres = new Presentation())
{
    // Zdobądź pierwszy slajd
    ISlide sld = pres.Slides[0];
```
Zainicjuj nową prezentację i uzyskaj dostęp do pierwszego slajdu, aby osadzić klatkę wideo.
## Krok 3: Osadź wideo w prezentacji
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
 Skorzystaj z`AddVideo` metoda osadzenia wideo w prezentacji, określająca ścieżkę pliku i zachowanie podczas ładowania.
## Krok 4: Dodaj klatkę wideo
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
Utwórz klatkę wideo na slajdzie, określając jej położenie i wymiary.
## Krok 5: Skonfiguruj ustawienia wideo
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
Powiąż klatkę wideo z osadzonym wideo, ustaw tryb odtwarzania i dostosuj głośność zgodnie ze swoimi preferencjami.
## Krok 6: Zapisz prezentację
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację z osadzoną klatką wideo.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak osadzać klatki wideo w slajdach prezentacji za pomocą Aspose.Slides dla .NET. Ta funkcja otwiera ekscytujące możliwości tworzenia dynamicznych i wciągających prezentacji, które przykuwają uwagę odbiorców.
## Często zadawane pytania
### Czy mogę osadzać filmy w różnych formatach za pomocą Aspose.Slides?
Tak, Aspose.Slides obsługuje różne formaty wideo, zapewniając elastyczność prezentacji.
### Jak mogę kontrolować ustawienia odtwarzania osadzonego wideo?
 Poprawić`PlayMode` I`Volume` właściwości klatki wideo, aby dostosować zachowanie odtwarzania.
### Czy Aspose.Slides jest kompatybilny z najnowszymi wersjami .NET?
Aspose.Slides jest regularnie aktualizowany, aby zachować zgodność z najnowszymi frameworkami .NET.
### Czy mogę osadzić wiele filmów na jednym slajdzie za pomocą Aspose.Slides?
Tak, możesz osadzić wiele filmów, dodając do slajdu dodatkowe klatki wideo.
### Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Slides?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności i dyskusje.