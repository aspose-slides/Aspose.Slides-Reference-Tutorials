---
"date": "2025-04-23"
"description": "Узнайте, как настроить угол поворота заголовков диаграмм в презентациях с помощью Aspose.Slides для Python, улучшив читабельность и эстетичность."
"title": "Как установить поворот заголовка вертикальной оси диаграммы в Aspose.Slides для Python"
"url": "/ru/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как установить поворот заголовка вертикальной оси диаграммы в Aspose.Slides для Python

## Введение

В презентациях данных улучшение читаемости диаграммы имеет решающее значение. Регулировка угла поворота заголовка вертикальной оси диаграммы с помощью Aspose.Slides для Python может сделать заголовки аккуратными или выделяющимися на слайдах. Это руководство поможет вам настроить этот угол поворота для улучшения как функциональности, так и визуальной привлекательности.

**Что вы узнаете:**
- Как установить и настроить Aspose.Slides для Python.
- Действия по добавлению и настройке диаграмм на слайдах.
- Методы установки угла поворота заголовков диаграмм.
- Реальные применения этих функций в визуализации данных.

Давайте начнем с рассмотрения предварительных условий, прежде чем перейдем к реализации.

## Предпосылки

Перед началом убедитесь, что у вас есть:
- **Среда Python**: Установить Python 3.x из [python.org](https://www.python.org/).
- **Библиотека Aspose.Slides**: Установите через pip для эффективного управления презентациями.
- **Базовые знания программирования на Python**: Знакомство с синтаксисом Python и файловыми операциями поможет вам в дальнейшем изучении.

## Настройка Aspose.Slides для Python

Чтобы использовать Aspose.Slides, установите его с помощью pip. Откройте терминал или командную строку и выполните:

```bash
pip install aspose.slides
```

### Этапы получения лицензии

Aspose предлагает различные варианты лицензирования:
- **Бесплатная пробная версия**: Загрузите пробную версию с сайта [Страница релиза Aspose](https://releases.aspose.com/slides/python-net/).
- **Временная лицензия**: Получите временную лицензию на расширенные функции через [портал покупки](https://purchase.aspose.com/temporary-license/).
- **Покупка**: Рассмотрите возможность покупки, если вы считаете этот инструмент незаменимым, его можно приобрести в [Страница покупки Aspose](https://purchase.aspose.com/buy).

#### Базовая инициализация и настройка

Вот как инициализировать Aspose.Slides в вашем скрипте Python:

```python
import aspose.slides as slides

# Создать объект презентации
def main():
    with slides.Presentation() as pres:
        # Ваш код будет здесь
        pass

if __name__ == "__main__":
    main()
```

## Руководство по внедрению

### Добавление и настройка диаграмм

#### Обзор

В этом разделе мы добавим на слайд кластеризованную столбчатую диаграмму и настроим ее, задав угол поворота заголовка ее вертикальной оси.

#### Шаги:

##### Шаг 1: Добавьте кластеризованную столбчатую диаграмму

Начните с добавления диаграммы в определенных координатах с определенными размерами:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Добавьте кластеризованную столбчатую диаграмму на слайд 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Шаг 2: Настройте заголовок вертикальной оси

Включите и задайте угол поворота для заголовка вертикальной оси:

```python
def configure_chart(chart):
    # Включить заголовок вертикальной оси
    chart.axes.vertical_axis.has_title = True
    
    # Установите угол поворота на 90 градусов.
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Шаг 3: Сохраните презентацию

Наконец, сохраните презентацию с изменениями:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Сохранить презентацию
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}