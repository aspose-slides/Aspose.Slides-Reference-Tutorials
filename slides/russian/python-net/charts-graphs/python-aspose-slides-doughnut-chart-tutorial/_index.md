---
"date": "2025-04-22"
"description": "Узнайте, как создавать кольцевые диаграммы с помощью Python и Aspose.Slides. Это пошаговое руководство охватывает настройку, настройку и лучшие практики для улучшения ваших презентаций."
"title": "Как создать кольцевые диаграммы в Python с помощью Aspose.Slides&#58; Пошаговое руководство"
"url": "/ru/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать кольцевые диаграммы в Python с помощью Aspose.Slides: пошаговое руководство

В сфере визуализации данных эффективное представление информации может существенно повлиять на понимание и принятие решений. Независимо от того, создаете ли вы бизнес-презентацию или анализируете сложные наборы данных, диаграммы являются важнейшими инструментами. Среди различных типов диаграмм кольцевые диаграммы предоставляют привлекательный способ представления пропорциональных данных с интуитивно понятным отверстием в центре. Это пошаговое руководство проведет вас через создание кольцевой диаграммы в Python с использованием Aspose.Slides — мощной библиотеки для управления презентациями.

## Что вы узнаете
- Как настроить и использовать Aspose.Slides для Python
- Процесс добавления кольцевой диаграммы на слайды презентации
- Настройка серий и категорий в диаграмме
- Настройка визуальных элементов, таких как метки, цвета и эффекты взрыва
- Лучшие практики по оптимизации производительности с помощью Aspose.Slides

## Предпосылки
Перед началом убедитесь, что у вас есть:
- **Среда Python**: На вашем компьютере установлен Python 3.x.
- **Aspose.Slides для Python**: Установите эту библиотеку с помощью pip.
- **Базовое понимание программирования на Python**: Знакомство с циклами и объектно-ориентированным программированием будет полезным.

## Настройка Aspose.Slides для Python
Для начала установите библиотеку Aspose.Slides через pip:

```bash
pip install aspose.slides
```

### Приобретение лицензии
Aspose предлагает бесплатную пробную версию для тестирования функций без ограничений в течение ограниченного времени. Чтобы получить ее:
1. Посетите [Бесплатная пробная версия](https://releases.aspose.com/slides/python-net/) страница.
2. Следуйте инструкциям по загрузке и применению временной лицензии.

Для дальнейшего использования рассмотрите возможность приобретения подписки у [Страница покупки](https://purchase.aspose.com/buy).

### Базовая инициализация
После настройки Aspose.Slides инициализируйте его следующим образом:

```python
import aspose.slides as slides

# Создайте экземпляр класса Presentation.
with slides.Presentation() as pres:
    # Ваш код для управления презентациями находится здесь.

# Сохраните презентацию после внесения изменений.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Руководство по внедрению
Настроив Aspose.Slides, выполните следующие действия, чтобы добавить кольцевую диаграмму в презентацию слайд за слайдом.

### Создание новой презентации и добавление слайда
Начните с создания экземпляра `Presentation` сорт:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Получайте доступ к слайдам или создавайте их в этом контексте.
```

### Добавление кольцевой диаграммы на первый слайд
Откройте первый слайд и используйте `add_chart` Метод. Укажите тип диаграммы как `DOUGHNUT`, а также положение и размер:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Настройка данных диаграммы
Очистите существующие данные и настройте параметры, такие как скрытие легенды:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Добавление серий и категорий
Добавьте несколько серий и категорий для кольцевой диаграммы. Вот как создать 15 серий с определенными свойствами:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Аналогично добавьте категории:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Добавьте точки данных для каждой серии.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Настройте внешний вид каждой точки данных.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Настройте параметры метки для последней серии.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Сохранение презентации
Наконец, сохраните презентацию в указанном каталоге:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Практические применения
Кольцевые диаграммы универсальны и могут использоваться в различных сценариях, таких как:
1. **Распределение бюджета**: Отображение того, как различные департаменты используют выделенные им средства.
2. **Анализ доли рынка**: Сравнение доли рынка конкурирующих продуктов или компаний.
3. **Результаты опроса**: Визуализация ответов на вопросы опроса о предпочтениях или уровнях удовлетворенности.

## Соображения производительности
Для обеспечения оптимальной производительности при использовании Aspose.Slides:
- Минимизируйте использование памяти, правильно утилизируя объекты после использования.
- Загружайте презентации в память только при необходимости и закрывайте их как можно скорее.
- Рассмотрите возможность пакетной обработки слайдов, если вы работаете с большим количеством диаграмм.

## Заключение
Следуя этому руководству, вы узнали, как создавать динамические кольцевые диаграммы с помощью Aspose.Slides для Python. Эти визуализации могут улучшить ваши презентации, сделав данные более усвояемыми и интересными. Продолжайте изучать функции библиотеки, чтобы еще больше настраивать и оптимизировать ваши диаграммы.

## Раздел часто задаваемых вопросов
1. **Могу ли я использовать Aspose.Slides без покупки лицензии?**
   - Да, вы можете начать с бесплатной пробной лицензии в целях оценки.
2. **Как изменить цвета диаграммы в Aspose.Slides?**
   - Используйте `fill_format` свойство, чтобы задать желаемый цвет для элементов диаграммы.
3. **Можно ли экспортировать диаграммы в виде изображений?**
   - Да, вы можете преобразовывать слайды, содержащие диаграммы, в форматы изображений, используя возможности рендеринга библиотеки.
4. **Какие проблемы чаще всего возникают при добавлении диаграмм?**
   - Прежде чем сохранять или отображать диаграмму, убедитесь, что все точки данных и категории добавлены правильно.
5. **Могу ли я интегрировать Aspose.Slides с другими библиотеками Python?**
   - Конечно! Вы можете использовать его вместе с библиотеками, такими как Pandas, для расширенных возможностей манипулирования данными.

## Ресурсы
- [Документация Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Скачать Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Купить лицензию](https://purchase.aspose.com/buy)
- [Бесплатная пробная версия и временная лицензия](https://releases.aspose.com/slides/python-net/)
- [Форум сообщества Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}