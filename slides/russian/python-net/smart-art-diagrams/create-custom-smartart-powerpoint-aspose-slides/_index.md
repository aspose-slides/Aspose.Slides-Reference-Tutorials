---
"date": "2025-04-23"
"description": "Узнайте, как создавать и настраивать графику SmartArt в PowerPoint с помощью Aspose.Slides для Python, улучшая свои презентации с помощью динамических организационных диаграмм."
"title": "Как создать и настроить SmartArt в PowerPoint с помощью Aspose.Slides для Python"
"url": "/ru/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать и настроить SmartArt в PowerPoint с помощью Aspose.Slides для Python

## Введение

Презентации — это важный инструмент для визуального представления организационных структур или мозговых штурмов. С помощью Aspose.Slides для Python вы можете создавать и настраивать графику SmartArt без особых усилий. Это руководство проведет вас через добавление графика SmartArt организационной диаграммы на слайды PowerPoint.

**Что вы узнаете:**
- Добавление графики SmartArt в PowerPoint с помощью Aspose.Slides для Python.
- Настройка макета узла SmartArt.
- Эффективное сохранение и экспорт презентаций.

Давайте начнем с настройки вашей среды!

## Предпосылки

Прежде чем приступить к созданию графики SmartArt, убедитесь, что у вас есть следующие предварительные условия:

### Необходимые библиотеки
- **Aspose.Slides для Python**: Установите эту библиотеку с помощью pip, если вы еще этого не сделали.

### Требования к настройке среды
- Рабочая установка Python (рекомендуется 3.x).
- Базовые знания программирования на Python.
- Знакомство с Microsoft PowerPoint полезно, но не обязательно.

## Настройка Aspose.Slides для Python

Для начала настройте библиотеку Aspose.Slides в своей среде Python:

**Установка пипа:**
```bash
pip install aspose.slides
```

### Этапы получения лицензии
Aspose предлагает различные варианты лицензирования:
- **Бесплатная пробная версия**: Загрузите временную лицензию, чтобы оценить все функции.
- **Временная лицензия**: Получите бесплатную временную лицензию для краткосрочного использования.
- **Покупка**: Рассмотрите возможность приобретения подписки для долгосрочных проектов.

### Базовая инициализация и настройка

После установки инициализируйте свой скрипт Python с помощью Aspose.Slides следующим образом:

```python
import aspose.slides as slides

# Инициализируйте класс Presentation_with_slides.Presentation() как презентацию:
    # Ваш код для добавления SmartArt будет здесь
```

## Руководство по внедрению

Теперь давайте разберем процесс добавления и настройки SmartArt в PowerPoint с помощью Aspose.Slides для Python.

### Добавление графики SmartArt

#### Обзор
Создайте новый слайд и добавьте на него графический элемент SmartArt типа организационной диаграммы:

```python
import aspose.slides as slides

# Создайте экземпляр презентации\со слайдами.Presentation() в качестве презентации:
    # Добавить SmartArt с указанными размерами в позицию (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Параметры и назначение метода
- **х, у**: Положение графического элемента SmartArt на слайде.
- **ширина, высота**: Размеры для хорошей видимости.
- **тип_макета**: Указывает тип макета SmartArt, в данном случае — организационную диаграмму.

### Настройка макета организационной схемы

#### Обзор
Настройте первый узел в нашей графике SmartArt, установив для него макет LEFT_HANGING:

```python
# Установите первый узел в положение левостороннего расположения
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Объяснение основных параметров конфигурации
- **OrganizationChartLayoutType**определяет, как отображаются узлы, улучшая читаемость и эстетическую привлекательность.

### Сохранение презентации

Наконец, сохраните презентацию в указанном каталоге:

```python
# Сохраните презентацию с помощью SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}