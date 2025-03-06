---
title: Sformatuj style łączenia w programie PowerPoint
linktitle: Sformatuj style łączenia w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ulepszyć swoje prezentacje programu PowerPoint, ustawiając różne style łączenia linii dla kształtów za pomocą Aspose.Slides dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku.
weight: 15
url: /pl/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji programu PowerPoint może być trudnym zadaniem, zwłaszcza jeśli chcesz, aby każdy szczegół był doskonały. Tutaj przydaje się Aspose.Slides dla Java. Jest to potężny interfejs API, który umożliwia programowe tworzenie prezentacji, manipulowanie nimi i zarządzanie nimi. Jedną z funkcji, z których możesz skorzystać, jest ustawienie różnych stylów łączenia linii dla kształtów, co może znacznie poprawić estetykę slajdów. W tym samouczku omówimy, jak używać Aspose.Slides dla Java do ustawiania stylów łączenia kształtów w prezentacjach programu PowerPoint. 
## Warunki wstępne
Zanim zaczniemy, musisz spełnić kilka warunków wstępnych:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK na swoim komputerze. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Biblioteka Aspose.Slides for Java: Musisz pobrać i dołączyć Aspose.Slides for Java do swojego projektu. Możesz to dostać od[Tutaj](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Użyj IDE, takiego jak IntelliJ IDEA, Eclipse lub NetBeans, aby pisać i wykonywać kod Java.
4. Podstawowa znajomość języka Java: Podstawowa znajomość programowania w języku Java pomoże w podążaniu za tutorialem.
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety dla Aspose.Slides. Jest to niezbędne, aby uzyskać dostęp do klas i metod wymaganych do manipulacji naszą prezentacją.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Konfiguracja katalogu projektu
Zacznijmy od utworzenia katalogu do przechowywania plików naszych prezentacji. Dzięki temu wszystkie nasze pliki są uporządkowane i łatwo dostępne.
```java
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
W tym kroku definiujemy ścieżkę do katalogu i sprawdzamy, czy istnieje. Jeśli nie, tworzymy katalog. Jest to prosty, ale skuteczny sposób na uporządkowanie plików.
## Krok 2: Zainicjuj prezentację
 Następnie tworzymy instancję`Presentation` class, która reprezentuje nasz plik PowerPoint. To jest podstawa, na której będziemy budować nasze slajdy i kształty.
```java
Presentation pres = new Presentation();
```
Ta linia kodu tworzy nową prezentację. Pomyśl o tym jak o otwarciu pustego pliku programu PowerPoint, do którego dodasz całą zawartość.
## Krok 3: Dodaj kształty do slajdu
### Zdobądź pierwszy slajd
Przed dodaniem kształtów musimy uzyskać odniesienie do pierwszego slajdu w naszej prezentacji. Domyślnie nowa prezentacja zawiera jeden pusty slajd.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Dodaj kształty prostokątów
Dodajmy teraz do naszego slajdu trzy prostokątne kształty. Kształty te pokażą różne style łączenia linii.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
W tym kroku dodajemy trzy prostokąty w określonych miejscach na slajdzie. Każdy prostokąt zostanie później stylizowany inaczej, aby zaprezentować różne style łączenia.
## Krok 4: Stylizuj kształty
### Ustaw kolor wypełnienia
Chcemy, żeby nasze prostokąty były wypełnione jednolitym kolorem. Tutaj jako kolor wypełnienia wybieramy kolor czarny.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Ustaw szerokość i kolor linii
Następnie definiujemy szerokość linii i kolor każdego prostokąta. Pomaga to w wizualnym różnicowaniu stylów łączenia.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Krok 5: Zastosuj style łączenia
Najważniejszym elementem tego samouczka jest ustawienie stylów łączenia linii. Będziemy używać trzech różnych stylów: Ukośny, Skos i Okrągły.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Każdy styl łączenia linii nadaje kształtom niepowtarzalny wygląd w narożnikach, w których spotykają się linie. Może to być szczególnie przydatne przy tworzeniu wizualnie odrębnych diagramów lub ilustracji.
## Krok 6: Dodaj tekst do kształtów
Aby było jasne, co reprezentuje każdy kształt, do każdego prostokąta dodajemy tekst opisujący zastosowany styl łączenia.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Dodanie tekstu pomaga zidentyfikować różne style podczas prezentacji lub udostępniania slajdu.
## Krok 7: Zapisz prezentację
Na koniec zapisujemy naszą prezentację we wskazanym katalogu.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
To polecenie zapisuje prezentację do pliku PPTX, który można otworzyć za pomocą programu Microsoft PowerPoint lub innego kompatybilnego oprogramowania.
## Wniosek
I masz to! Właśnie utworzyłeś slajd programu PowerPoint składający się z trzech prostokątów, z których każdy przedstawia inny styl łączenia linii przy użyciu Aspose.Slides dla Java. Ten samouczek nie tylko pomaga zrozumieć podstawy Aspose.Slides, ale także pokazuje, jak ulepszyć swoje prezentacje za pomocą unikalnych stylów. Miłej prezentacji!
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API do programowego tworzenia, manipulowania i zarządzania prezentacjami programu PowerPoint.
### Czy mogę używać Aspose.Slides dla Java w dowolnym IDE?
Tak, możesz używać Aspose.Slides for Java w dowolnym środowisku IDE obsługującym Javę, takim jak IntelliJ IDEA, Eclipse lub NetBeans.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla Java?
 Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### Jakie są style łączenia linii w programie PowerPoint?
Style łączenia linii odnoszą się do kształtu narożników, w których spotykają się dwie linie. Typowe style obejmują ukosowanie, fazowanie i zaokrąglenie.
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
 Można znaleźć szczegółową dokumentację[Tutaj](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
