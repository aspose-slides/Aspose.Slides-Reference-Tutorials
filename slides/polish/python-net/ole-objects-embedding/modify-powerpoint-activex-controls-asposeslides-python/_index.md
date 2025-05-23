---
"date": "2025-04-22"
"description": "Dowiedz się, jak modyfikować tekst TextBox, podpisy przycisków i obrazy w programie PowerPoint za pomocą Aspose.Slides z Pythonem. Ulepsz swoje prezentacje za pomocą interaktywnych elementów."
"title": "Mistrz Aspose.Slides dla Pythona – łatwa modyfikacja kontrolek ActiveX programu PowerPoint"
"url": "/pl/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie Aspose.Slides dla języka Python: Modyfikowanie kontrolek ActiveX programu PowerPoint

W dzisiejszym dynamicznym cyfrowym krajobrazie dostosowywanie prezentacji Microsoft PowerPoint jest niezbędne do tworzenia angażujących treści. Niezależnie od tego, czy opracowujesz interaktywne moduły szkoleniowe, czy ulepszasz prezentacje biznesowe o możliwości wprowadzania danych przez użytkownika, modyfikacja kontrolek ActiveX programu PowerPoint może znacznie zwiększyć funkcjonalność prezentacji. Ten samouczek bada użycie Aspose.Slides for Python do zmiany tekstu TextBox i podpisów przycisków, zastępowania obrazów, zmiany położenia lub usuwania kontrolek ActiveX ze slajdów.

## Czego się nauczysz
- Jak modyfikować tekst w polu tekstowym i podpisy przycisków w prezentacjach programu PowerPoint.
- Techniki podstawiania obrazków w kontrolkach ActiveX.
- Metody efektywnej zmiany położenia lub usuwania kontrolek ActiveX.
- Praktyczne zastosowania tych funkcji w scenariuszach z życia wziętych.

Zanim zagłębimy się w temat Aspose.Slides dla języka Python, przyjrzyjmy się wymaganiom wstępnym.

## Wymagania wstępne
Aby skorzystać z tego samouczka, upewnij się, że posiadasz:
- **Pyton**:W systemie zainstalowana jest wersja 3.6 lub nowsza.
- **Aspose.Slides dla Pythona przez .NET**: Można zainstalować za pomocą pip.
- Podstawowa znajomość programowania w języku Python i struktura programu PowerPoint.

### Wymagania dotyczące konfiguracji środowiska
1. **Zainstaluj Aspose.Slides**:
   Aby zainstalować Aspose.Slides dla języka Python za pośrednictwem .NET, użyj następującego polecenia:

   ```bash
   pip install aspose.slides
   ```

2. **Nabycie licencji**: 
   Zacznij od uzyskania [bezpłatna licencja próbna](https://releases.aspose.com/slides/python-net/) lub ubiegać się o tymczasową licencję, aby móc korzystać ze wszystkich funkcji bez ograniczeń.

3. **Podstawowa inicjalizacja**:
   Zaimportuj niezbędne moduły i załaduj dokument PowerPoint, jak pokazano poniżej:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Twój kod będzie tutaj.
   ```

## Przewodnik wdrażania
### Funkcja: Zmień tekst pola tekstowego i zamień obraz
#### Przegląd
Funkcja ta umożliwia aktualizację tekstu w kontrolce ActiveX TextBox i zastąpienie powiązanego z nią obrazu. Jest to przydatne przy personalizowaniu prezentacji lub dynamicznej aktualizacji zawartości.

##### Przewodnik krok po kroku
1. **Załaduj prezentację**:
   Zacznij od załadowania prezentacji PowerPoint zawierającej kontrolki ActiveX.

   ```python
def change_textbox_and_image():
    ze slajdami.Presentation("TWOJ_KATALOG_DOKUMENTÓW/activex_master.pptm") jako prezentacją:
        slajd = prezentacja.slajdy[0]
```
2. **Access the TextBox Control**:
   Access the specific control you intend to modify.

   ```python
        control = slide.controls[0]
        if control.name == "TextBox1" and control.properties is not None:
            new_text = "Changed text"
            # Remove existing property value for 'Value'
            control.properties.remove("Value")
            # Add the new text as a property
            control.properties.add("Value", new_text)
```
3. **Utwórz zastępczy obraz**:
   Wygeneruj obraz, który zastąpi oryginalną zawartość podczas aktywacji ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Utwórz obraz o określonych wymiarach
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Dodaj linie obramowania, aby uzyskać dopracowany wygląd
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_DARK), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Finally, add this image as a substitute for the ActiveX control.

   ```python
                # Add the created image to presentation images
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funkcja: Zmień podpis przycisku i zamień obraz
#### Przegląd
Aktualizuj podpisy przycisków w kontrolkach ActiveX prezentacji, zapewniając dynamiczne możliwości interakcji z użytkownikiem.

##### Przewodnik krok po kroku
1. **Załaduj prezentację**:
   Jak poprzednio, zacznij od załadowania pliku PowerPoint.

   ```python
def change_button_caption_and_image():
    ze slajdami.Presentation("TWOJ_KATALOG_DOKUMENTÓW/activex_master.pptm") jako prezentacją:
        slajd = prezentacja.slajdy[0]
```
2. **Access the Button Control**:
   Identify and modify the button control's caption.

   ```python
        control = slide.controls[1]
        if control.name == "CommandButton1" and control.properties is not None:
            new_caption = "MessageBox"
            control.properties.remove("Caption")
            control.properties.add("Caption", new_caption)
```
3. **Utwórz zastępczy obraz**:
   Wygeneruj obraz do wizualnej zamiany.

   ```python
            # Utwórz mapę bitową dla wymiarów przycisku
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Dodaj linie obramowania dla estetyki
                with drawing.Pen(drawing.Color.from_known_color(drawing.KnownColor.CONTROL_LIGHT_LIGHT), 1.0) as pen:
                    graphics.draw_lines(pen, [
                        drawing.PointF(0, image.height - 1),
                        drawing.PointF(0, 0),
                        drawing.PointF(image.width - 1, 0)
                    ])
```
4. **Add the Image to Presentation**:
   Save the newly created image in your presentation.

   ```python
                control.substitute_picture_format.picture.image = presentation.images.add_image(image)
```
### Funkcja: Przenieś kontrolki ActiveX w dół i zapisz prezentację
#### Przegląd
Dowiedz się, jak zmieniać położenie kontrolek ActiveX w obrębie slajdu, zwiększając elastyczność układu.

##### Przewodnik krok po kroku
1. **Załaduj prezentację**:
   Otwórz dokument programu PowerPoint do edycji.

   ```python
def move_active_x_controls_and_save():
    ze slajdami.Presentation("TWOJ_KATALOG_DOKUMENTÓW/activex_master.pptm") jako prezentacją:
        slajd = prezentacja.slajdy[0]
```
2. **Reposition Controls**:
   Iterate through controls to adjust their positions.

   ```python
        for ctl in slide.controls:
            frame = ctl.frame
            # Move each control down by 100 points on the y-axis
            ctl.frame = slides.ShapeFrame(
                frame.x, frame.y + 100, frame.width, frame.height,
                # Rest of your code to move and save controls
```
**Wniosek:**
Postępując zgodnie z tym przewodnikiem, możesz skutecznie modyfikować kontrolki ActiveX programu PowerPoint za pomocą Aspose.Slides dla Pythona. Zwiększa to interaktywność i personalizację prezentacji, czyniąc je bardziej angażującymi dla odbiorców.

## Rekomendacje słów kluczowych
- „Modyfikuj kontrolki ActiveX programu PowerPoint”
- „Aspose.Slides dla Pythona”
- „Zmień tekst pola tekstowego w programie PowerPoint”
- „Podmiana obrazów w kontrolkach ActiveX”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}