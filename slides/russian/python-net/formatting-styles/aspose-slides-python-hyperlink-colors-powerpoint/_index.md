---
"date": "2025-04-23"
"description": "Узнайте, как настраивать цвета гиперссылок в презентациях PowerPoint с помощью Aspose.Slides для Python. Эффективно улучшайте свои слайды с помощью персонализированных стилей ссылок."
"title": "Как установить цвета гиперссылок в PowerPoint с помощью Aspose.Slides для Python"
"url": "/ru/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как установить цвета гиперссылок в PowerPoint с помощью Aspose.Slides для Python

## Введение

Улучшение визуальной привлекательности ваших презентаций PowerPoint путем настройки цветов гиперссылок становится простым с Aspose.Slides для Python. Это руководство проведет вас через настройку гиперссылок с определенными цветами в ваших слайдах с помощью Python.

**Что вы узнаете:**
- Как установить цвет гиперссылки в текстовых фигурах в PowerPoint.
- Этапы создания визуально привлекательной презентации.
- Ключевые функции Aspose.Slides для Python, облегчающие эту настройку.

Давайте рассмотрим необходимые предварительные условия, прежде чем начать.

## Предпосылки

Прежде чем начать, убедитесь, что ваша среда готова к работе, выполнив следующие действия:
- **Библиотеки и версии:** Установить `aspose.slides` библиотека. Убедитесь, что Python установлен на вашем компьютере.
- **Требования к настройке среды:** В этом руководстве предполагается базовая настройка Python на Windows, Mac или Linux.
- **Необходимые знания:** Знакомство с программированием на Python будет преимуществом.

## Настройка Aspose.Slides для Python

Чтобы начать использовать Aspose.Slides для Python, установите пакет через pip:

```bash
pip install aspose.slides
```

**Этапы получения лицензии:**
- **Бесплатная пробная версия:** Загрузите пробную версию с сайта [Страница релиза Aspose](https://releases.aspose.com/slides/python-net/).
- **Временная лицензия:** Запросить временную лицензию на [страница покупки](https://purchase.aspose.com/temporary-license/) для расширенного доступа.
- **Покупка:** Чтобы полностью разблокировать функции без ограничений, рассмотрите возможность приобретения лицензии у [Страница покупки Aspose](https://purchase.aspose.com/buy).

**Базовая инициализация:**
После установки и лицензирования импортируйте Aspose.Slides в свой скрипт:

```python
import aspose.slides as slides
```

## Руководство по внедрению

В этом разделе вы узнаете, как настроить цвета гиперссылок в презентации PowerPoint.

### Установить функцию цвета гиперссылки

#### Обзор

Настройте цвет гиперссылок, встроенных в текстовые фигуры, используя Aspose.Slides для Python. Это повышает читабельность и визуальную привлекательность.

##### Шаг 1: Создайте новую презентацию

Создайте экземпляр презентации:

```python
with slides.Presentation() as presentation:
    # Ваш код здесь
```

##### Шаг 2: Добавьте фигуру с текстом

Добавьте к первому слайду прямоугольник и вставьте текст, содержащий гиперссылку.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Шаг 3: Задайте свойства гиперссылки

Назначьте гиперссылку и задайте ее цвет. `hyperlink_click` свойство указывает, куда должна вести ссылка при нажатии.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Установите источник цвета для формата гиперссылки на часть и определите тип и цвет заливки.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Шаг 4: Сохраните презентацию

Сохраните презентацию в указанном каталоге:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}