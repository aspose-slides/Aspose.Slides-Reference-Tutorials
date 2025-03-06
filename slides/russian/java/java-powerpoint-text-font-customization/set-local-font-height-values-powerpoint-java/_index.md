---
title: Установите локальные значения высоты шрифта в PowerPoint с помощью Java
linktitle: Установите локальные значения высоты шрифта в PowerPoint с помощью Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как настроить высоту шрифта в презентациях PowerPoint с помощью Java с Aspose.Slides. Улучшите форматирование текста на слайдах без особых усилий.
weight: 17
url: /ru/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Введение
В этом уроке вы узнаете, как управлять высотой шрифта на разных уровнях в презентациях PowerPoint с помощью Aspose.Slides для Java. Управление размером шрифта имеет решающее значение для создания визуально привлекательных и структурированных презентаций. Мы рассмотрим пошаговые примеры, чтобы проиллюстрировать, как устанавливать высоту шрифта для различных текстовых элементов.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
- Комплект разработки Java (JDK), установленный в вашей системе.
-  Aspose.Slides для библиотеки Java. Вы можете скачать его[здесь](https://releases.aspose.com/slides/java/).
- Базовое понимание программирования Java и презентаций PowerPoint.
## Импортировать пакеты
Обязательно включите необходимые пакеты Aspose.Slides в ваш Java-файл:
```java
import com.aspose.slides.*;
```
## Шаг 1. Инициализация объекта презентации
Сначала создайте новый объект презентации PowerPoint:
```java
Presentation pres = new Presentation();
```
## Шаг 2. Добавьте фигуру и текстовый фрейм
Добавьте автофигуру с текстовой рамкой на первый слайд:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Шаг 3. Создайте части текста
Определите части текста с разной высотой шрифта:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Шаг 4. Установите высоту шрифта
Установите высоту шрифта на разных уровнях:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Шаг 5. Сохраните презентацию
Сохраните измененную презентацию в файл:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Заключение
В этом руководстве показано, как программно настроить высоту шрифта в слайдах PowerPoint с помощью Aspose.Slides для Java. Управляя размерами шрифтов на разных уровнях (в рамках всей презентации, абзаца и части), вы можете добиться точного контроля над форматированием текста в своих презентациях.
## Часто задаваемые вопросы
### Что такое Aspose.Slides для Java?
Aspose.Slides for Java — это мощный API для программного управления презентациями PowerPoint.
### Где я могу найти документацию по Aspose.Slides для Java?
 Вы можете найти документацию[здесь](https://reference.aspose.com/slides/java/).
### Могу ли я попробовать Aspose.Slides для Java перед покупкой?
 Да, вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Как я могу получить поддержку Aspose.Slides для Java?
 Для получения поддержки посетите[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Где я могу приобрести лицензию на Aspose.Slides для Java?
 Вы можете приобрести лицензию[здесь](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
