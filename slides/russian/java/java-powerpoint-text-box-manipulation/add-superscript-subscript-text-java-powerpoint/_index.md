---
title: Добавить надстрочный и подстрочный текст в Java PowerPoint
linktitle: Добавить надстрочный и подстрочный текст в Java PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавлять надстрочный и подстрочный текст в презентации Java PowerPoint с помощью Aspose.Slides для Java. Идеально подходит для улучшения ваших слайдов.
weight: 13
url: /ru/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Введение
Создание интересных и информативных презентаций PowerPoint часто требует использования функций форматирования, таких как надстрочный и подстрочный текст. Это руководство проведет вас через процесс включения надстрочного и подстрочного текста в презентации Java PowerPoint с использованием Aspose.Slides для Java.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
- В вашей системе установлен Java Development Kit (JDK).
-  Aspose.Slides для библиотеки Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).
- Интегрированная среда разработки (IDE), такая как IntelliJ IDEA или Eclipse, настроенная для разработки на Java.
- Базовые знания программирования на Java и презентаций PowerPoint.

## Импортировать пакеты
Сначала импортируйте необходимые пакеты из Aspose.Slides for Java:
```java
import com.aspose.slides.*;
```
## Шаг 1. Настройте презентацию
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Шаг 2. Доступ к слайду
```java
// Получить первый слайд
ISlide slide = presentation.getSlides().get_Item(0);
```
## Шаг 3. Создайте текстовое поле
```java
// Создайте автофигуру, которая будет служить текстовым полем.
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Шаг 4. Добавьте текст надстрочного индекса
```java
// Создайте абзац для основного текста
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Создайте часть для надстрочного текста.
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Установить спуск для верхнего индекса
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Добавьте основной абзац с надстрочным индексом в текстовое поле.
textFrame.getParagraphs().add(mainParagraph);
```
## Шаг 5: Добавьте текст нижнего индекса
```java
// Создайте еще один абзац для подстрочного текста.
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Создайте часть для текста нижнего индекса
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Установить спуск для нижнего индекса
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Добавьте нижний индекс в текстовое поле
textFrame.getParagraphs().add(subscriptParagraph);
```
## Шаг 6. Сохраните презентацию
```java
// Сохранить презентацию
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Заключение
В этом уроке мы рассмотрели, как улучшить ваши презентации Java PowerPoint с помощью надстрочного и подстрочного текста с помощью Aspose.Slides для Java. Следуя этим шагам, вы сможете создавать более визуально привлекательные и информативные слайды, которые эффективно передают ваш контент.

## Часто задаваемые вопросы
### Что такое Aspose.Slides для Java?
Aspose.Slides for Java — это надежная библиотека, которая позволяет разработчикам программно создавать, манипулировать и конвертировать презентации PowerPoint.
### Где я могу найти дополнительную документацию по Aspose.Slides для Java?
 Подробную документацию можно найти[здесь](https://reference.aspose.com/slides/java/).
### Как я могу получить временную лицензию на Aspose.Slides для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Могу ли я попробовать Aspose.Slides для Java бесплатно?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
### Где я могу получить поддержку Aspose.Slides для Java?
 Для поддержки и обсуждения посетите[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
