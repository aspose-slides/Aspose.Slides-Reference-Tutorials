---
"description": "Dowiedz się, jak ulepszyć prezentacje PowerPoint za pomocą kontrolek ActiveX przy użyciu Aspose.Slides dla .NET. Nasz przewodnik krok po kroku obejmuje wstawianie, manipulację, dostosowywanie, obsługę zdarzeń i wiele więcej."
"linktitle": "Zarządzanie kontrolką ActiveX w programie PowerPoint"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Zarządzanie kontrolką ActiveX w programie PowerPoint"
"url": "/pl/net/slide-view-and-layout-manipulation/manage-activex-control/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzanie kontrolką ActiveX w programie PowerPoint

Kontrolki ActiveX to potężne elementy, które mogą zwiększyć funkcjonalność i interaktywność prezentacji PowerPoint. Kontrolki te umożliwiają osadzanie i manipulowanie obiektami, takimi jak odtwarzacze multimedialne, formularze wprowadzania danych i wiele innych, bezpośrednio w slajdach. W tym artykule przyjrzymy się sposobowi zarządzania kontrolkami ActiveX w programie PowerPoint przy użyciu Aspose.Slides for .NET, wszechstronnej biblioteki, która umożliwia bezproblemową integrację i manipulowanie plikami PowerPoint w aplikacjach .NET.

## Dodawanie kontrolek ActiveX do slajdów programu PowerPoint

Aby rozpocząć dodawanie kontrolek ActiveX do prezentacji programu PowerPoint, wykonaj następujące kroki:

1. Utwórz nową prezentację PowerPoint: Najpierw utwórz nową prezentację PowerPoint przy użyciu Aspose.Slides dla .NET. Możesz zapoznać się z [Aspose.Slides dla .NET API Reference](https://reference.aspose.com/slides/net/) aby uzyskać wskazówki dotyczące pracy z prezentacjami.

2. Dodaj slajd: Użyj biblioteki, aby dodać nowy slajd do prezentacji. Będzie to slajd, w którym chcesz wstawić kontrolkę ActiveX.

3. Wstaw kontrolkę ActiveX: Teraz czas wstawić kontrolkę ActiveX na slajd. Możesz to zrobić, postępując zgodnie z poniższym przykładowym kodem:

```csharp
// Załaduj prezentację
Presentation presentation = new Presentation("path_to_your_presentation.pptx");

// Wybierz slajd, w którym chcesz wstawić kontrolkę ActiveX
ISlide slide = presentation.Slides[0];

// Zdefiniuj właściwości kontrolki ActiveX
int left = 100; // Określ lewą pozycję
int top = 100; // Określ górną pozycję
int width = 200; // Określ szerokość
int height = 100; // Określ wysokość
string progId = "YourActiveXControl.ProgID"; // Określ ProgID kontrolki ActiveX

// Dodaj kontrolkę ActiveX do slajdu
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(left, top, width, height, progId);
```

Pamiętaj o wymianie `"YourActiveXControl.ProgID"` z rzeczywistym ProgID kontrolki ActiveX, którą chcesz wstawić.

4. Zapisz prezentację: Po wstawieniu kontrolki ActiveX zapisz prezentację, korzystając z następującego kodu:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## Manipulowanie kontrolkami ActiveX programowo

Po dodaniu kontrolki ActiveX do slajdu możesz chcieć manipulować nią programowo. Oto, jak możesz to zrobić:

1. Uzyskaj dostęp do kontrolki ActiveX: Aby uzyskać dostęp do właściwości i metod kontrolki ActiveX, musisz uzyskać do niej odwołanie. Użyj następującego kodu, aby uzyskać kontrolkę ze slajdu:

```csharp
IOleObjectFrame oleObjectFrame = slide.Shapes[0] as IOleObjectFrame;
```

2. Wywołanie metod: Możesz wywołać metody kontrolki ActiveX, używając uzyskanego odniesienia. Na przykład, jeśli kontrolka ActiveX ma metodę o nazwie „Play”, możesz wywołać ją w ten sposób:

```csharp
oleObjectFrame.InvokeMethod("Play");
```

3. Ustaw właściwości: Możesz również programowo ustawić właściwości kontrolki ActiveX. Na przykład, jeśli kontrolka ma właściwość o nazwie „Volume”, możesz ustawić ją w następujący sposób:

```csharp
oleObjectFrame.SetProperty("Volume", 50);
```

## Dostosowywanie właściwości kontrolki ActiveX

Dostosowywanie właściwości kontrolki ActiveX może znacznie poprawić wrażenia użytkownika z prezentacji. Oto, jak możesz dostosować te właściwości:

1. Dostęp do właściwości: Jak wspomniano wcześniej, dostęp do właściwości kontrolki ActiveX można uzyskać za pomocą `IOleObjectFrame` odniesienie.

2. Ustaw właściwości: Użyj `SetProperty` metoda ustawiania różnych właściwości kontrolki ActiveX. Na przykład możesz zmienić kolor tła w następujący sposób:

```csharp
oleObjectFrame.SetProperty("BackColor", Color.Red);
```

## Obsługa zdarzeń związanych z kontrolkami ActiveX

Kontrolki ActiveX często mają powiązane zdarzenia, które mogą wyzwalać akcje na podstawie interakcji użytkownika. Oto, jak możesz obsługiwać te zdarzenia:

1. Subskrybuj zdarzenia: Najpierw zasubskrybuj żądane zdarzenie kontrolki ActiveX. Na przykład, jeśli kontrolka ma zdarzenie „Clicked”, możesz je zasubskrybować w następujący sposób:

```csharp
oleObjectFrame.EventClick += (sender, args) =>
{
    // Tutaj znajduje się kod obsługi zdarzeń
};
```

## Usuwanie kontrolek ActiveX ze slajdów

Jeśli chcesz usunąć kontrolkę ActiveX ze slajdu, wykonaj następujące czynności:

1. Uzyskaj dostęp do kontrolki: Uzyskaj odwołanie do kontrolki ActiveX za pomocą `IOleObjectFrame` odniesienie jak pokazano wcześniej.

2. Usuń kontrolkę: Użyj poniższego kodu, aby usunąć kontrolkę ze slajdu:

```csharp
slide.Shapes.Remove(oleObjectFrame);
```

## Zapisywanie i eksportowanie zmodyfikowanej prezentacji

Po wprowadzeniu wszystkich niezbędnych zmian w prezentacji możesz ją zapisać i wyeksportować, korzystając z poniższego kodu:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Korzyści ze stosowania Aspose.Slides dla .NET

Aspose.Slides for .NET upraszcza proces pracy z kontrolkami ActiveX w prezentacjach PowerPoint, zapewniając przyjazny dla użytkownika interfejs API, który umożliwia bezproblemową integrację i manipulowanie tymi kontrolkami. Niektóre korzyści z używania Aspose.Slides for .NET obejmują:

- Łatwe wstawianie kontrolek ActiveX na slajdy.
- Kompleksowe metody programowej interakcji z kontrolkami.
- Uproszczone dostosowywanie właściwości kontrolek.
- Efektywna obsługa zdarzeń na potrzeby prezentacji interaktywnych.
- Usprawniono usuwanie elementów sterujących ze slajdów.

## Wniosek

Włączenie kontrolek ActiveX do prezentacji PowerPoint może podnieść poziom interaktywności i zaangażowania odbiorców. Dzięki Aspose.Slides dla .NET masz do dyspozycji potężne narzędzie do bezproblemowego zarządzania kontrolkami ActiveX, co pozwala tworzyć dynamiczne i wciągające prezentacje, które pozostawiają trwałe wrażenie.

## Często zadawane pytania

### Jak dodać kontrolkę ActiveX do konkretnego slajdu?

Aby dodać kontrolkę ActiveX do określonego slajdu, możesz użyć `AddOleObjectFrame` metoda dostarczona przez Aspose.Slides dla .NET. Ta metoda pozwala określić pozycję, rozmiar i ProgID kontrolki ActiveX, którą chcesz wstawić.

### Czy mogę programowo manipulować kontrolkami ActiveX?

Tak, możesz manipulować kontrolkami ActiveX programowo, używając Aspose.Slides dla .NET. Uzyskując odwołanie do `IOleObjectFrame` reprezentując kontrolkę, możesz wywoływać metody i ustawiać właściwości, aby dynamicznie wchodzić w interakcję z kontrolką.

### Jak obsługiwać zdarzenia

 wyzwalane przez kontrolki ActiveX?

Możesz obsługiwać zdarzenia wyzwalane przez kontrolki ActiveX, subskrybując odpowiednie zdarzenia za pomocą `EventClick` (lub podobny) program obsługi zdarzeń. Pozwala to na wykonywanie określonych akcji w odpowiedzi na interakcje użytkownika z kontrolką.

### Czy można dostosować wygląd kontrolek ActiveX?

Oczywiście, możesz dostosować wygląd kontrolek ActiveX, korzystając z `SetProperty` metoda dostarczona przez Aspose.Slides dla .NET. Ta metoda umożliwia modyfikowanie różnych właściwości, takich jak kolor tła, styl czcionki i inne.

### Czy mogę usunąć kontrolkę ActiveX ze slajdu?

Tak, możesz usunąć kontrolkę ActiveX ze slajdu za pomocą `Remove` metoda `Shapes` kolekcja. Przekaż odniesienie do `IOleObjectFrame` reprezentując kontrolę jako argument dla `Remove` metody, a kontrolka zostanie usunięta ze slajdu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}