---
date: '2026-02-09'
description: Изучите, как рисовать рамки вокруг текста и добавлять текст в ячейки
  таблицы в PowerPoint с помощью Aspose.Slides для Java. В этом руководстве рассматривается
  создание таблиц, настройка выравнивания текста и сохранение презентации в формате
  pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Как рисовать рамки и добавлять текст в таблицу с помощью Aspose.Slides для
  Java
url: /ru/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как рисовать рамки и добавлять текст в таблицу в презентациях с Aspose.Slides для Java

## Введение

Представление данных в PowerPoint часто представляет собой настоящую проблему, особенно когда нужно **добавлять текст в ячейки таблицы** и выделять важные значения визуальными подсказками. В этом руководстве вы узнаете, **как рисовать рамки** вокруг определённых абзацев, задавать выравнивание текста внутри фигур и, наконец, **сохранять презентацию в формате pptx** — всё с помощью Aspose.Slides для Java. К концу вы получите отшлифованный набор слайдов, который привлекает внимание аудитории именно туда, куда вы хотите.

Готовы сделать ваши слайды более выразительными? Давайте пройдём процесс шаг за шагом.

## Быстрые ответы
- **Что означает “add text to table”?** Это вставка или обновление текстового содержимого отдельных ячеек таблицы программным способом.  
- **Какой метод сохраняет файл?** `pres.save("output.pptx", SaveFormat.Pptx)` — этот шаг **save presentation as pptx** завершает ваши изменения.  
- **Как выровнять текст внутри фигуры?** Используйте `TextAlignment.Left` (или Center/Right) через `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Можно ли нарисовать прямоугольник вокруг абзаца?** Да — пройдитесь по абзацам, получите их ограничивающий прямоугольник и добавьте `IAutoShape` без заливки и с чёрной линией.  
- **Нужна ли лицензия?** Временная лицензия подходит для оценки; полная лицензия требуется для использования в продакшене.  

## Зачем рисовать рамки вокруг текста?

Рисование рамки (или прямоугольника) вокруг абзаца или конкретной части (например, любого текста, содержащего символ **'0'**) мгновенно привлекает внимание. Эта техника идеальна для:

- Выделения ключевых финансовых показателей в таблице.  
- Подчёркивания предупреждений или важных заметок на слайде.  
- Создания визуальных разделителей без необходимости вручную добавлять дополнительные фигуры.

## Предварительные требования

Прежде чем погрузиться в код, убедитесь, что у вас есть следующее:

### Необходимые библиотеки
Вам понадобится Aspose.Slides для Java. Ниже показано, как подключить её с помощью Maven или Gradle:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Настройка окружения
Убедитесь, что установлен Java Development Kit (JDK), желательно JDK 16 или новее, так как в примере используется классификатор `jdk16`.

### Требования к знаниям
- Базовое понимание программирования на Java.  
- Знакомство с программным обеспечением для презентаций, таким как PowerPoint.  
- Опыт работы в интегрированной среде разработки (IDE), например IntelliJ IDEA или Eclipse.

## Настройка Aspose.Slides для Java

Чтобы начать использовать Aspose.Slides, выполните следующие шаги:

1. **Установите библиотеку**: используйте Maven или Gradle для управления зависимостями, либо скачайте её напрямую с [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **Получение лицензии**:
   - Начните с бесплатной пробной версии, загрузив временную лицензию с [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Для полного доступа рассмотрите покупку лицензии на странице [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Базовая инициализация**:
Инициализируйте среду презентаций с помощью следующего фрагмента кода:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Как добавить текст в таблицу в Aspose.Slides для Java

### Функция 1: Создать таблицу и добавить текст в ячейки

#### Обзор
Эта функция демонстрирует, как **create table**, затем **add text to table** в ячейки и в конце **save presentation as pptx**.

#### Шаги

**1. Создать таблицу**  
Сначала инициализируйте презентацию и добавьте таблицу в позицию (50, 50) с указанными ширинами столбцов и высотами строк.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Добавить текст в ячейки**  
Создайте абзацы с частями текста и добавьте их в конкретную ячейку.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Сохранить презентацию**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Функция 2: Добавить TextFrame к AutoShape и задать выравнивание

#### Обзор
Узнайте, как добавить текстовый фрейм с определённым выравниванием к автофигуре — пример **set text alignment java**.

#### Шаги

**1. Добавить AutoShape**  
Добавьте прямоугольник как AutoShape в позицию (400, 100) с заданными размерами.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Задать выравнивание текста**  
Установите текст «Text in shape» и выровняйте его по левому краю.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Сохранить презентацию**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Функция 3: Рисовать рамки вокруг абзацев и частей в ячейках таблицы

#### Обзор
Эта функция сосредоточена на **draw frames around text** и даже **draw rectangle around paragraph** для частей, содержащих символ ‘0’.

#### Шаги

**1. Создать таблицу**  
Повторно используйте код из «Create Table and Add Text to Cells» для начальной настройки.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Добавить абзацы**  
Повторно используйте код создания абзацев из предыдущей функции.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Рисовать рамки**  
Итерируйте по абзацам и частям, чтобы рисовать рамки вокруг них.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```

**4. Сохранить презентацию**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Общие подводные камни и советы

- **Проверка на null** — всегда оборачивайте использование `Presentation` в блок `try‑finally`, чтобы гарантировать вызов `pres.dispose()` и освобождение нативных ресурсов.  
- **Точность ограничивающего прямоугольника** — прямоугольник, возвращаемый `para.getRect()`, отражает текущую раскладку; если вы меняете размер шрифта или отступы, пересчитайте прямоугольник перед рисованием рамки.  
- **Производительность** — при работе с очень большими таблицами рассматривайте пакетное добавление фигур или повторное использование одного экземпляра `IAutoShape` с обновлённой геометрией, чтобы снизить нагрузку на память.

## Часто задаваемые вопросы

**В: Можно ли использовать эти API с более старыми версиями JDK?**  
О: Библиотека поддерживает JDK 8 и выше, но классификатор `jdk16` обеспечивает лучшую производительность на новых средах выполнения.

**В: Как изменить цвет рамки?**  
О: Измените цвет заливки линии, например `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**В: Можно ли экспортировать финальный слайд как изображение?**  
О: Да — используйте `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` и затем сохраните полученный массив байтов.

**В: Как выделить только слово «Total» внутри ячейки?**  
О: Пройдитесь по `cell.getTextFrame().getParagraphs()`, найдите часть, содержащую «Total», и нарисуйте прямоугольник вокруг ограничивающего бокса этой части.

**В: Эффективно ли Aspose.Slides работает с большими презентациями?**  
О: API потоково обрабатывает данные и освобождает ресурсы при вызове `pres.dispose()`, что помогает управлять памятью при работе с крупными файлами.

---

{{< blocks/products/products-backtop-button >}}

**Последнее обновление:** 2026-02-09  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}