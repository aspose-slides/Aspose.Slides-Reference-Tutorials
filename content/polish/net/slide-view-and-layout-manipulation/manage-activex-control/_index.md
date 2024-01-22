---
title: Zarządzaj formantem ActiveX w programie PowerPoint
linktitle: Zarządzaj formantem ActiveX w programie PowerPoint
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ulepszyć prezentacje programu PowerPoint za pomocą kontrolek ActiveX przy użyciu Aspose.Slides dla .NET. Nasz przewodnik krok po kroku obejmuje wstawianie, manipulację, dostosowywanie, obsługę zdarzeń i nie tylko.
type: docs
weight: 13
url: /pl/net/slide-view-and-layout-manipulation/manage-activex-control/
---
Kontrolki ActiveX to potężne elementy, które mogą zwiększyć funkcjonalność i interaktywność prezentacji programu PowerPoint. Te elementy sterujące umożliwiają osadzanie obiektów takich jak odtwarzacze multimedialne, formularze wprowadzania danych i manipulowanie nimi bezpośrednio w slajdach. W tym artykule zbadamy, jak zarządzać kontrolkami ActiveX w programie PowerPoint przy użyciu Aspose.Slides dla .NET, wszechstronnej biblioteki, która umożliwia bezproblemową integrację i manipulowanie plikami programu PowerPoint w aplikacjach .NET.

## Dodawanie kontrolek ActiveX do slajdów programu PowerPoint

Aby rozpocząć dołączanie kontrolek ActiveX do prezentacji programu PowerPoint, wykonaj następujące kroki:

1.  Utwórz nową prezentację programu PowerPoint: Najpierw utwórz nową prezentację programu PowerPoint za pomocą Aspose.Slides dla .NET. Możesz odwołać się do[Aspose.Slides dla .NET API odniesienia](https://reference.aspose.com/slides/net/) aby uzyskać wskazówki dotyczące pracy z prezentacjami.

2. Dodaj slajd: Użyj biblioteki, aby dodać nowy slajd do swojej prezentacji. Będzie to slajd, w którym chcesz wstawić formant ActiveX.

3. Wstawianie kontrolki ActiveX: Teraz czas na wstawienie kontrolki ActiveX na slajd. Można to osiągnąć, postępując zgodnie z poniższym przykładowym kodem:

```csharp
// Załaduj prezentację
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Pobierz slajd, w którym chcesz wstawić formant ActiveX
ISlide slide = presentation.Slides[0];

// Zdefiniuj właściwości kontrolki ActiveX
int left = 100; // Określ lewą pozycję
int top = 100; // Określ górną pozycję
int width = 200; // Określ szerokość
int height = 100; // Określ wysokość
string progId = "YourActiveXControl.ProgID"; // Określ ProgID kontrolki ActiveX

// Dodaj formant ActiveX do slajdu
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

 Pamiętaj o wymianie`"YourActiveXControl.ProgID"` z rzeczywistym identyfikatorem ProgID kontrolki ActiveX, którą chcesz wstawić.

4. Zapisz prezentację: Po wstawieniu kontrolki ActiveX zapisz prezentację, używając następującego kodu:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Programowe manipulowanie kontrolkami ActiveX

Po dodaniu kontrolki ActiveX do slajdu warto programowo nią manipulować. Oto jak możesz to zrobić:

1. Uzyskaj dostęp do kontrolki ActiveX: Aby uzyskać dostęp do właściwości i metod kontrolki ActiveX, musisz uzyskać do niej odwołanie. Użyj poniższego kodu, aby uzyskać kontrolę ze slajdu:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Wywołaj metody: Możesz wywołać metody kontrolki ActiveX, korzystając z uzyskanego odniesienia. Na przykład, jeśli kontrolka ActiveX ma metodę o nazwie „Odtwórz”, możesz ją nazwać w ten sposób:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Ustaw właściwości: Możesz także programowo ustawić właściwości kontrolki ActiveX. Na przykład, jeśli kontrolka ma właściwość o nazwie „Głośność”, możesz ustawić ją w następujący sposób:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Dostosowywanie właściwości kontrolki ActiveX

Dostosowanie właściwości kontrolki ActiveX może znacznie poprawić komfort korzystania z prezentacji. Oto jak możesz dostosować te właściwości:

1.  Dostęp do właściwości: Jak wspomniano wcześniej, dostęp do właściwości kontrolki ActiveX można uzyskać za pomocą`IOleObjectFrame` odniesienie.

2.  Ustaw właściwości: Użyj`SetProperty`metoda ustawiania różnych właściwości kontrolki ActiveX. Na przykład możesz zmienić kolor tła w następujący sposób:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Obsługa zdarzeń powiązanych z kontrolkami ActiveX

Kontrole ActiveX często mają powiązane zdarzenia, które mogą wyzwalać akcje w oparciu o interakcje użytkownika. Oto jak możesz obsłużyć te zdarzenia:

1. Subskrybuj zdarzenia: Najpierw zasubskrybuj żądane zdarzenie kontrolki ActiveX. Na przykład, jeśli kontrolka zawiera zdarzenie „Kliknięty”, możesz go subskrybować w następujący sposób:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Tutaj znajdziesz kod obsługi zdarzenia
};
```

## Usuwanie kontrolek ActiveX ze slajdów

Jeśli chcesz usunąć formant ActiveX ze slajdu, wykonaj następujące kroki:

1.  Uzyskaj dostęp do kontrolki: Uzyskaj odwołanie do kontrolki ActiveX za pomocą`IOleObjectFrame` odniesienia, jak pokazano wcześniej.

2. Usuń kontrolkę: Użyj poniższego kodu, aby usunąć kontrolkę ze slajdu:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Zapisywanie i eksportowanie zmodyfikowanej prezentacji

Po wprowadzeniu wszystkich niezbędnych zmian w prezentacji możesz ją zapisać i wyeksportować, korzystając z następującego kodu:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Korzyści z używania Aspose.Slides dla .NET

Aspose.Slides dla .NET upraszcza proces pracy z kontrolkami ActiveX w prezentacjach programu PowerPoint, udostępniając przyjazny dla użytkownika interfejs API, który umożliwia bezproblemową integrację i manipulowanie tymi kontrolkami. Niektóre zalety korzystania z Aspose.Slides dla .NET obejmują:

- Łatwe wstawianie kontrolek ActiveX na slajdy.
- Kompleksowe metody programowej interakcji z kontrolkami.
- Uproszczone dostosowywanie właściwości kontrolnych.
- Efektywna obsługa zdarzeń w prezentacjach interaktywnych.
- Usprawnione usuwanie elementów sterujących ze slajdów.

## Wniosek

Włączenie kontrolek ActiveX do prezentacji programu PowerPoint może podnieść poziom interaktywności i zaangażowania odbiorców. Dzięki Aspose.Slides dla .NET masz do dyspozycji potężne narzędzie do płynnego zarządzania kontrolkami ActiveX, umożliwiające tworzenie dynamicznych i wciągających prezentacji, które pozostawiają niezatarte wrażenie.

## Często zadawane pytania

### Jak dodać kontrolkę ActiveX do określonego slajdu?

 Aby dodać kontrolkę ActiveX do określonego slajdu, możesz użyć metody`AddOleObjectFrame` metoda udostępniona przez Aspose.Slides dla .NET. Ta metoda umożliwia określenie położenia, rozmiaru i identyfikatora ProgID kontrolki ActiveX, którą chcesz wstawić.

### Czy mogę programowo manipulować kontrolkami ActiveX?

 Tak, możesz programowo manipulować kontrolkami ActiveX za pomocą Aspose.Slides dla .NET. Uzyskawszy referencje do`IOleObjectFrame` reprezentującą kontrolkę, można wywoływać metody i ustawiać właściwości w celu dynamicznej interakcji z kontrolką.

### Jak radzić sobie ze zdarzeniami

 wyzwalane przez kontrolki ActiveX?

Możesz obsługiwać zdarzenia wyzwalane przez kontrolki ActiveX, subskrybując odpowiednie zdarzenia za pomocą`EventClick` (lub podobny) moduł obsługi zdarzeń. Pozwala to na wykonanie określonych akcji w odpowiedzi na interakcję użytkownika z kontrolką.

### Czy można dostosować wygląd kontrolek ActiveX?

 Oczywiście możesz dostosować wygląd kontrolek ActiveX za pomocą`SetProperty` metoda udostępniona przez Aspose.Slides dla .NET. Ta metoda umożliwia modyfikowanie różnych właściwości, takich jak kolor tła, styl czcionki i inne.

### Czy mogę usunąć formant ActiveX ze slajdu?

 Tak, możesz usunąć formant ActiveX ze slajdu za pomocą`Remove` metoda`Shapes` kolekcja. Przekaż odniesienie do`IOleObjectFrame` reprezentujący formant jako argument metody`Remove` metodę, a element sterujący zostanie usunięty ze slajdu.