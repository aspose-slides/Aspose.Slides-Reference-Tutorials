---
title: Создать сводный масштаб в PowerPoint
linktitle: Создать сводный масштаб в PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создать сводный масштаб в PowerPoint с помощью Aspose.Slides для Java, с помощью этого подробного пошагового руководства.
weight: 16
url: /ru/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Введение
Добро пожаловать в наше подробное руководство по созданию сводного масштаба в PowerPoint с использованием Aspose.Slides для Java. Если вы хотите добавить в свои презентации динамичный и интерактивный элемент, Summary Zoom — фантастическая функция. Он позволяет вам создать один слайд, который может масштабировать различные разделы вашей презентации, предлагая вашей аудитории более привлекательный и удобный для навигации опыт.
В этом пошаговом руководстве мы проведем вас через весь процесс: от настройки среды разработки до создания и настройки фрейма Summary Zoom. Независимо от того, являетесь ли вы опытным разработчиком Java или только начинаете, вы найдете это руководство простым для понимания и наполненным ценной информацией.
## Предварительные условия
Прежде чем углубиться в код, давайте убедимся, что у вас есть все необходимое для начала работы:
1.  Комплект разработки Java (JDK): убедитесь, что на вашем компьютере установлен JDK. Вы можете скачать его с сайта[веб-сайт Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides для Java: Загрузите библиотеку с сайта[Страница релизов Aspose](https://releases.aspose.com/slides/java/).
3. Интегрированная среда разработки (IDE). Используйте IDE, например IntelliJ IDEA, Eclipse или NetBeans, для более удобной разработки.
4. Базовые знания Java. Знакомство с концепциями программирования Java поможет вам понять и реализовать шаги, описанные в этом руководстве.
## Импортировать пакеты
Прежде чем мы начнем, вам необходимо импортировать необходимые пакеты. Убедитесь, что вы включили Aspose.Slides for Java в зависимости вашего проекта.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Шаг 1. Настройте свой проект
Во-первых, убедитесь, что ваша среда разработки настроена правильно. Выполните следующие шаги, чтобы настроить проект:
### Создать новый проект
1. Откройте свою IDE.
2. Создайте новый проект Java.
3.  Добавьте библиотеку Aspose.Slides for Java в путь сборки вашего проекта. Вы можете скачать JAR-файл с сайта[Страница релизов Aspose](https://releases.aspose.com/slides/java/) и включите его в свой проект.
### Инициализируйте презентацию
Затем инициализируйте новый объект презентации, куда вы добавите слайды и разделы.
```java
Presentation pres = new Presentation();
```
## Шаг 2. Добавьте слайды и разделы
На этом этапе мы добавим слайды в презентацию и разобьем их на разделы. Эта организация имеет решающее значение для создания сводного масштаба.
### Добавить новый слайд и раздел
1. Добавить пустой слайд: добавьте в презентацию новый слайд.
2. Настройка фона слайда: установите сплошной цвет заливки для фона слайда.
3. Добавить раздел: сгруппируйте слайд в раздел.
Вот код для достижения этой цели:
```java
// Добавьте первый слайд
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// Добавьте первый раздел
pres.getSections().addSection("Section 1", slide);
```
### Повторите для дополнительных разделов.
Повторите процесс, чтобы добавить больше слайдов и разделов:
```java
// Добавьте второй слайд и раздел
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// Добавьте третий слайд и раздел
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// Добавьте четвертый слайд и раздел
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## Шаг 3. Создайте рамку масштабирования сводки
Теперь мы создадим рамку сводного масштабирования на первом слайде. Этот кадр будет действовать как интерактивный элемент, который позволит пользователям увеличивать различные разделы.

1. Найдите первый слайд: получите первый слайд, на который вы добавите рамку масштабирования сводки.
2.  Добавьте рамку масштабирования сводки: используйте`addSummaryZoomFrame` метод добавления кадра.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## Шаг 4. Сохраните презентацию
Наконец, сохраните презентацию в нужном месте. Этот шаг гарантирует, что все ваши изменения будут записаны в файл.
### Сохраните файл
1. Определите путь вывода: укажите путь, по которому будет сохранена презентация.
2.  Сохраните презентацию: используйте`save` метод сохранения файла в формате PPTX.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### Удалить объект презентации
Удалите объект презентации, чтобы освободить все ресурсы, которые он использует:
```java
if (pres != null) pres.dispose();
```
## Заключение
 Поздравляем! Вы успешно создали сводный масштаб в PowerPoint с помощью Aspose.Slides для Java. Эта функция улучшает ваши презентации, делая их более интерактивными и привлекательными. Следуя этому руководству, вы теперь обладаете навыками реализации этой функции в своих собственных проектах. Не забудьте изучить[Документация Aspose.Slides для Java](https://reference.aspose.com/slides/java/)для получения более продвинутых функций и возможностей настройки.
## Часто задаваемые вопросы
### Что такое Aspose.Slides для Java?
Aspose.Slides for Java — это мощная библиотека, которая позволяет разработчикам создавать, изменять и манипулировать презентациями PowerPoint программным способом с использованием Java.
### Могу ли я использовать Aspose.Slides для Java для создания других типов контента в PowerPoint?
Да, Aspose.Slides for Java поддерживает широкий спектр функций, включая создание слайдов, добавление фигур, диаграмм, таблиц и многое другое.
### Доступна ли бесплатная пробная версия Aspose.Slides для Java?
Да, вы можете загрузить бесплатную пробную версию Aspose.Slides для Java с сайта[Веб-сайт](https://releases.aspose.com/).
### Как получить временную лицензию на Aspose.Slides для Java?
 Вы можете получить временную лицензию в[Aspose страница покупки](https://purchase.aspose.com/temporary-license/).
### Где я могу найти дополнительные примеры и поддержку Aspose.Slides для Java?
 Вы можете найти больше примеров и обратиться за поддержкой на[Форум поддержки Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
