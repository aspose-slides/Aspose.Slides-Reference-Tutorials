---
"date": "2025-04-22"
"description": "Узнайте, как легко отображать процентные метки на диаграммах в презентациях PowerPoint с помощью Aspose.Slides для Python. Идеально подходит для улучшения визуализации данных."
"title": "Как отображать процентные метки на диаграммах с помощью Aspose.Slides для Python&#58; Подробное руководство"
"url": "/ru/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как отображать процентные метки на диаграммах с помощью Aspose.Slides для Python

## Введение

Эффективная визуализация данных имеет решающее значение в презентациях и отчетах, особенно когда вы хотите четко выделить пропорции или распределения. Но что, если вам нужно, чтобы эти проценты отображались непосредственно на ваших диаграммах? Это всеобъемлющее руководство проведет вас через использование **Aspose.Slides для Python** для легкого отображения процентных значений в виде меток на диаграмме.

### Что вы узнаете:
- Как создавать и встраивать диаграммы в презентации PowerPoint с помощью Aspose.Slides для Python.
- Отображение точек данных в виде процентных меток на диаграммах.
- Эффективное сохранение и управление презентациями PowerPoint.

Готовы начать добавлять полезные визуальные эффекты к вашим данным? Давайте сначала посмотрим, что вам нужно, прежде чем погрузиться в код!

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:
- **Aspose.Slides для Python**: Эта библиотека необходима для программного создания и управления презентациями PowerPoint.
- **Среда Python**: Базовые знания программирования на Python и настройки среды.
- **Менеджер пакетов PIP**: Используется для установки Aspose.Slides.

## Настройка Aspose.Slides для Python

Чтобы начать использовать Aspose.Slides, вам сначала необходимо его установить:

```bash
pip install aspose.slides
```

### Этапы получения лицензии:
Вы можете начать с бесплатной пробной версии или получить временную лицензию, чтобы изучить все возможности Aspose.Slides. Для расширенного использования рассмотрите возможность приобретения подписки.

#### Базовая инициализация и настройка

После установки вы инициализируете свою презентационную среду следующим образом:

```python
import aspose.slides as slides

# Инициализация объекта презентации
def create_presentation():
    with slides.Presentation() as presentation:
        # Ваш код здесь
```

## Руководство по внедрению

Теперь, когда все готово, давайте перейдем к отображению процентов на диаграммах.

### Создание диаграммы и добавление данных

#### Обзор
Мы создадим столбчатую диаграмму с накоплением и процентными метками для каждой точки данных, что позволит зрителям сразу увидеть точные пропорции.

##### Шаг 1: Добавьте диаграмму на слайд

```python
# Доступ к первому слайду презентации
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Добавить столбчатую диаграмму с накоплением
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Этот фрагмент кода добавляет простую диаграмму к первому слайду. `add_chart` метод определяет тип диаграммы, ее положение и размер.

##### Шаг 2: Рассчитайте общие значения для категорий

```python
def calculate_totals(chart):
    total_for_category = []
    # Суммируйте значения по всем рядам для каждой категории.
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Этот цикл вычисляет сумму всех точек данных в рядах, что имеет решающее значение для процентных расчетов.

#### Установка процентных меток

##### Шаг 3: Настройте точки данных серии

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Установите параметры метки по умолчанию, чтобы скрыть ненужную информацию
        series.labels.default_data_label_format.show_legend_key = False
        
        # Рассчитать и установить процентные метки
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Создайте текстовую часть с процентным значением
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Очистить существующие метки и добавить новую процентную метку
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Скрыть другие элементы метки данных
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Этот сегмент обрабатывает каждую точку данных, вычисляя ее процент от общего числа, и присваивает ей метку.

### Сохранение презентации

```python
def save_presentation(presentation, output_directory):
    # Сохраните презентацию с изменениями
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}