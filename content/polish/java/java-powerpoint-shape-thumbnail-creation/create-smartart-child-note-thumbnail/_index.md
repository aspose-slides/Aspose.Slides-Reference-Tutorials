---
title: Utwórz miniaturę notatki podrzędnej SmartArt
linktitle: Utwórz miniaturę notatki podrzędnej SmartArt
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć miniatury notatek podrzędnych SmartArt w Javie za pomocą Aspose.Slides, bez wysiłku ulepszając swoje prezentacje w programie PowerPoint.
type: docs
weight: 15
url: /pl/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---
## Wstęp
W tym samouczku omówimy, jak tworzyć miniatury notatek podrzędnych SmartArt w Javie przy użyciu Aspose.Slides. Aspose.Slides to potężny interfejs API języka Java, który umożliwia programistom programową pracę z prezentacjami programu PowerPoint, umożliwiając im łatwe tworzenie, modyfikowanie i manipulowanie slajdami.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2. Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w Twoim projekcie. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Pamiętaj, aby zaimportować niezbędne pakiety do swojej klasy Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Skonfiguruj swój projekt
Upewnij się, że masz skonfigurowany projekt Java z biblioteką Aspose.Slides.
## Krok 2: Utwórz prezentację
 Utwórz instancję`Presentation` klasa reprezentująca plik PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Krok 3: Dodaj grafikę SmartArt
Dodaj grafikę SmartArt do slajdu prezentacji:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 4: Uzyskaj odniesienie do węzła
Uzyskaj odniesienie do węzła, korzystając z jego indeksu:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Krok 5: Uzyskaj miniaturę
Pobierz miniaturę węzła SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Krok 6: Zapisz miniaturę
Zapisz obraz miniatury do pliku:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
W razie potrzeby powtórz te kroki dla każdego węzła grafiki SmartArt w prezentacji.

## Wniosek
W tym samouczku dowiedzieliśmy się, jak tworzyć miniatury notatek podrzędnych SmartArt w Javie przy użyciu Aspose.Slides. Dzięki tej wiedzy możesz programowo ulepszać swoje prezentacje PowerPoint, z łatwością dodając atrakcyjne wizualnie elementy.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides do manipulowania istniejącymi plikami programu PowerPoint?
Tak, Aspose.Slides umożliwia modyfikowanie istniejących plików programu PowerPoint, w tym dodawanie, usuwanie lub edycję slajdów i ich zawartości.
### Czy Aspose.Slides obsługuje eksportowanie slajdów do różnych formatów plików?
Absolutnie! Aspose.Slides obsługuje eksportowanie slajdów do różnych formatów, w tym między innymi PDF, obrazów i HTML.
### Czy Aspose.Slides nadaje się do automatyzacji programu PowerPoint na poziomie przedsiębiorstwa?
Tak, Aspose.Slides został zaprojektowany do wydajnej i niezawodnej obsługi zadań automatyzacji programu PowerPoint na poziomie przedsiębiorstwa.
### Czy mogę programowo tworzyć złożone diagramy SmartArt za pomocą Aspose.Slides?
Z pewnością! Aspose.Slides zapewnia kompleksowe wsparcie w tworzeniu i manipulowaniu diagramami SmartArt o różnym stopniu złożoności.
### Czy Aspose.Slides oferuje wsparcie techniczne dla programistów?
 Tak, Aspose.Slides zapewnia dedykowane wsparcie techniczne dla programistów za pośrednictwem ich[forum](https://forum.aspose.com/c/slides/11) i inne kanały.