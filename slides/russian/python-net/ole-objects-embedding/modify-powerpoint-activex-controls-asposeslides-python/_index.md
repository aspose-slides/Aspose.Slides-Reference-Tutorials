---
"date": "2025-04-22"
"description": "Узнайте, как изменять текст TextBox, подписи кнопок и изображения в PowerPoint с помощью Aspose.Slides с Python. Улучшите свои презентации с помощью интерактивных элементов."
"title": "Мастер Aspose.Slides для Python&#58; легко изменяйте элементы управления PowerPoint ActiveX"
"url": "/ru/python-net/ole-objects-embedding/modify-powerpoint-activex-controls-asposeslides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Освоение Aspose.Slides для Python: изменение элементов управления PowerPoint ActiveX

В сегодняшнем динамичном цифровом ландшафте настройка презентаций Microsoft PowerPoint имеет важное значение для создания увлекательного контента. Независимо от того, разрабатываете ли вы интерактивные учебные модули или улучшаете бизнес-презентации с помощью возможностей пользовательского ввода, изменение элементов управления PowerPoint ActiveX может значительно повысить функциональность вашей презентации. В этом руководстве рассматривается использование Aspose.Slides для Python для изменения текста TextBox и подписей кнопок, замены изображений, перемещения или удаления элементов управления ActiveX со слайдов.

## Что вы узнаете
- Как изменить текст TextBox и подписи к кнопкам в презентациях PowerPoint.
- Методы замены изображений в элементах управления ActiveX.
- Методы эффективного перемещения или удаления элементов управления ActiveX.
- Практическое применение этих функций в реальных сценариях.

Прежде чем углубляться в Aspose.Slides для Python, давайте рассмотрим предварительные требования.

## Предпосылки
Чтобы следовать этому руководству, убедитесь, что у вас есть:
- **Питон**: В вашей системе установлена версия 3.6 или выше.
- **Aspose.Slides для Python через .NET**: Это можно установить с помощью pip.
- Базовые знания программирования на Python и знакомство со структурой PowerPoint.

### Требования к настройке среды
1. **Установить Aspose.Slides**:
   Используйте следующую команду для установки Aspose.Slides для Python через .NET:

   ```bash
   pip install aspose.slides
   ```

2. **Приобретение лицензии**: 
   Начните с получения [бесплатная пробная лицензия](https://releases.aspose.com/slides/python-net/) или подайте заявку на временную лицензию, чтобы изучить все возможности без ограничений.

3. **Базовая инициализация**:
   Импортируйте необходимые модули и загрузите документ PowerPoint, как показано ниже:

   ```python
   import aspose.slides as slides

   with slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") as presentation:
       pass  # Ваш код будет здесь.
   ```

## Руководство по внедрению
### Функция: изменение текста в текстовом поле и замена изображения
#### Обзор
Эта функция позволяет обновлять текст в элементе управления ActiveX TextBox и заменять связанное с ним изображение, что полезно для персонализации презентаций или динамического обновления контента.

##### Пошаговое руководство
1. **Загрузить презентацию**:
   Начните с загрузки презентации PowerPoint, содержащей элементы управления ActiveX.

   ```python
определение change_textbox_and_image():
    с slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") в качестве презентации:
        слайд = презентация.слайды[0]
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
3. **Создать заменяющее изображение**:
   Создайте изображение для замены исходного содержимого во время активации ActiveX.

   ```python
            import aspose.pydrawing as drawing

            # Создать изображение с указанными размерами
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)
                  
                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    graphics.draw_string(new_text, font, brush, 10.0, 4.0)

                # Добавьте линии границ для придания изысканного вида
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
### Функция: изменение заголовка кнопки и замена изображения
#### Обзор
Обновляйте подписи кнопок в элементах управления ActiveX вашей презентации, предоставляя возможности динамического взаимодействия с пользователем.

##### Пошаговое руководство
1. **Загрузить презентацию**:
   Как и прежде, начните с загрузки файла PowerPoint.

   ```python
определение изменения_подписи_кнопки_и_изображения():
    с slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") в качестве презентации:
        слайд = презентация.слайды[0]
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
3. **Создать заменяющее изображение**:
   Создайте изображение для визуальной замены.

   ```python
            # Создайте растровое изображение для размеров кнопки.
            image = drawing.Bitmap(int(control.frame.width), int(control.frame.height))
            with drawing.Graphics.from_image(image) as graphics:
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.CONTROL)) as brush:
                    graphics.fill_rectangle(brush, 0, 0, image.width, image.height)

                font = drawing.Font("Arial", 14.0)
                with drawing.SolidBrush(drawing.Color.from_known_color(drawing.KnownColor.WINDOW_TEXT)) as brush:
                    textSize = graphics.measure_string(new_caption, font, 1000)
                    graphics.draw_string(new_caption, font, brush, (image.width - textSize.width) / 2, (image.height - textSize.height) / 2)

                # Добавьте линии границ для эстетики
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
### Функция: Переместить элементы управления ActiveX вниз и сохранить презентацию
#### Обзор
Узнайте, как изменять положение элементов управления ActiveX на слайде, повышая гибкость макета.

##### Пошаговое руководство
1. **Загрузить презентацию**:
   Откройте документ PowerPoint для редактирования.

   ```python
определение move_active_x_controls_and_save():
    с slides.Presentation("YOUR_DOCUMENT_DIRECTORY/activex_master.pptm") в качестве презентации:
        слайд = презентация.слайды[0]
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
**Заключение:**
Следуя этому руководству, вы сможете эффективно изменять элементы управления PowerPoint ActiveX с помощью Aspose.Slides для Python. Это повышает интерактивность и настраиваемость ваших презентаций, делая их более интересными для вашей аудитории.

## Рекомендации по ключевым словам
- «Изменение элементов управления PowerPoint ActiveX»
- «Aspose.Slides для Python»
- «Изменить текст TextBox в PowerPoint»
- «Замена изображений в элементах управления ActiveX»

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}