---
date: '2026-02-17'
description: Узнайте, как добавлять круговые диаграммы в презентации PowerPoint с
  помощью Aspose.Slides для Java. Следуйте этому пошаговому руководству, чтобы создавать
  и настраивать профессиональные круговые диаграммы.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Как добавить круговую диаграмму в PowerPoint с помощью Aspose.Slides для Java
url: /ru/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Создание и настройка круговых диаграмм в PowerPoint с помощью Aspose.Slides for Java

## Введение

Трудно визуализировать данные эффективно в ваших презентациях PowerPoint? **Добавление слайда с круговой диаграммой PowerPoint** может мгновенно превратить сырые цифры в понятную визуальную историю. С помощью Aspose.Slides for Java вы можете программно **добавлять файлы с круговой диаграммой PowerPoint**, получая полный контроль над дизайном и данными без необходимости открывать PowerPoint вручную. В этом руководстве мы пройдем весь процесс — от настройки библиотеки до настройки отдельных точек данных — чтобы вы могли за считанные минуты создавать отшлифованные слайды, основанные на данных.

### Быстрые ответы
- **Какую библиотеку мне нужно?** Aspose.Slides for Java (latest version).  
- **Можно ли создать диаграмму без установленного PowerPoint?** Yes, the API works completely offline.  
- **Какая версия Java требуется?** JDK 16 or later is recommended.  
- **Как изменить цвет сектора?** Use the `setFillType` and `setSolidFillColor` methods on the data point.  
- **Обязательна ли лицензия?** A trial works for development; a permanent license removes evaluation limits.

### Что вы узнаете
- Как программно **add pie chart PowerPoint** с помощью Java.  
- Способы настройки взрыва сектора, цветов и других визуальных свойств.  
- Лучшие практики управления ресурсами и производительностью при работе с большими презентациями.

## Почему добавлять круговую диаграмму PowerPoint с помощью Aspose.Slides for Java?
Встраивание круговой диаграммы непосредственно из кода позволяет генерировать актуальные отчёты, автоматизировать ежемесячные панели мониторинга или создавать персонализированные наборы слайдов «на лету». Это устраняет ошибки ручного копирования‑вставки, обеспечивает согласованность между презентациями и плавно интегрируется с существующими Java‑бэкендами.

## Предварительные требования

- **Aspose.Slides for Java library** – the tutorial references version 25.4 (the latest release at the time of writing).  
- A compatible **Java Development Kit (JDK)** – JDK 16+ is preferred.  
- Basic familiarity with **Maven** or **Gradle** for dependency management.  

## Настройка Aspose.Slides for Java

Чтобы начать, включите библиотеку Aspose.Slides в ваш проект.

### Maven
Добавьте эту зависимость в ваш файл `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Добавьте следующее в ваш файл `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatively, download the latest version directly from [релизы Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Лицензирование
- Start with a **free trial** to evaluate the API.  
- Request a **temporary license** for extended testing at the [Временная лицензия](https://purchase.aspose.com/temporary-license/) page.  
- Purchase a full subscription via the [страница покупки](https://purchase.aspose.com/buy).

## Как добавить круговую диаграмму PowerPoint с помощью Aspose.Slides for Java

Ниже представлено пошаговое руководство, показывающее, как создать и настроить круговую диаграмму.

### Шаг 1: Инициализация презентации
First, create a new `Presentation` object. This represents an empty PowerPoint file.
```java
Presentation pres = new Presentation();
```

### Шаг 2: Добавление круговой диаграммы
Insert a pie chart onto the first slide. The coordinates (50, 50) and size (600 × 400) work well for a standard 16:9 slide.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Шаг 3: Сохранение презентации
Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the folder where you want the file saved.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Шаг 4: Очистка ресурсов
Dispose of the `Presentation` object to free native resources.
```java
if (pres != null) pres.dispose();
```

## Настройка взрыва сектора и цвета

Настройка отдельных секторов делает вашу диаграмму более читаемой, особенно когда нужно выделить конкретное значение.

### Шаг 1: Загрузка существующей презентации (или повторное использование только что созданной)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Шаг 2: Доступ к диаграмме и целевой точке данных
Here we retrieve the second data point (index 1) from the first series.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Шаг 3: Применение взрыва и цвета
Separate the slice visually and change its fill color to blue.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Шаг 4: Сохранение и очистка
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Практические применения
- **Отчеты о продажах:** Highlight top‑selling products with exploded slices.  
- **Анализ бюджета:** Assign distinct colors to departments for quick visual comparison.  
- **Образовательные слайды:** Break down complex concepts into easily digestible chart segments.  

## Соображения по производительности
- **Dispose objects** быстро освобождать объекты, чтобы избежать утечек памяти, особенно при генерации большого количества слайдов в цикле.  
- **Monitor heap usage** для больших презентаций; рассмотрите потоковый вывод с перегрузками `Save`, принимающими `OutputStream`.  
- Оставайтесь на **JDK 16+**, чтобы воспользоваться последними улучшениями сборки мусора.

## Заключение
You now have a complete, production‑ready workflow to **add pie chart PowerPoint** files using Aspose.Slides for Java. Experiment with different explosion distances, colors, and data sets to match your branding. When you’re ready, explore other chart types—bar, line, or scatter—to build a full analytics dashboard inside PowerPoint.

## Раздел FAQ
1. **What is the primary advantage of using Aspose.Slides for Java?**  
   - It simplifies the creation and manipulation of PowerPoint files programmatically, offering a wide array of features.  
2. **Can I customize other chart types with Aspose.Slides?**  
   - Absolutely! Aspose.Slides supports various chart types such as bar, line, and scatter charts.  
3. **How do I handle multiple slides when creating charts?**  
   - Access each slide by index using `get_Item()` method to apply changes across different slides.  
4. **What if my pie chart doesn't display correctly after customization?**  
   - Verify the coordinates and dimensions used in `addChart()`, ensuring they fit within your slide layout.  
5. **Where can I find more advanced features for Aspose.Slides?**  
   - Explore the [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) to learn about additional functionalities and options.

## Ресурсы
- **Documentation:** [Документация Aspose.Slides Java](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Релизы Aspose](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Купить Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Попробовать Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Запросить временную лицензию](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Поддержка Aspose](https://forum.aspose.com/c/slides/11)

---

**Последнее обновление:** 2026-02-17  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}