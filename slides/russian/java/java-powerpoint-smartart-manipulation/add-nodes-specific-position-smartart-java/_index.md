---
title: Добавьте узлы в определенную позицию в SmartArt с помощью Java
linktitle: Добавьте узлы в определенную позицию в SmartArt с помощью Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавлять узлы в определенные позиции в SmartArt с помощью Java с Aspose.Slides. Создавайте динамичные презентации без особых усилий.
weight: 16
url: /ru/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Введение
В этом уроке мы покажем вам процесс добавления узлов в определенные позиции в SmartArt с использованием Java с Aspose.Slides. SmartArt — это функция PowerPoint, которая позволяет создавать визуально привлекательные диаграммы и диаграммы.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Скачана библиотека Aspose.Slides для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).
3. Базовые знания языка программирования Java.

## Импортировать пакеты
Сначала давайте импортируем необходимые пакеты в наш Java-код:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Шаг 1. Создайте экземпляр презентации
Начните с создания экземпляра класса Presentation:
```java
Presentation pres = new Presentation();
```
## Шаг 2. Доступ к слайду презентации
Откройте слайд, на который вы хотите добавить SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Шаг 3. Добавьте фигуру SmartArt
Добавьте фигуру SmartArt на слайд:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Шаг 4. Доступ к узлу SmartArt
Получите доступ к узлу SmartArt по нужному индексу:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Шаг 5. Добавьте дочерний узел в определенную позицию
Добавьте новый дочерний узел в определенную позицию родительского узла:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Шаг 6. Добавьте текст в узел
Задайте текст для вновь добавленного узла:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Шаг 7: Сохраните презентацию
Сохраните измененную презентацию:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Заключение
В этом уроке вы узнали, как добавлять узлы в определенные позиции в SmartArt с помощью Java с Aspose.Slides. Выполнив эти действия, вы сможете программно манипулировать фигурами SmartArt для создания динамических презентаций.
## Часто задаваемые вопросы
### Могу ли я добавить несколько узлов одновременно?
Да, вы можете добавить несколько узлов программно, перебирая нужные позиции.
### Совместим ли Aspose.Slides со всеми версиями PowerPoint?
Aspose.Slides поддерживает различные форматы PowerPoint, обеспечивая совместимость с большинством версий.
### Могу ли я настроить внешний вид узлов SmartArt?
Да, вы можете настроить внешний вид узлов, включая их размер, цвет и стиль.
### Предлагает ли Aspose.Slides поддержку других языков программирования?
Да, Aspose.Slides предоставляет библиотеки для нескольких языков программирования, включая .NET и Python.
### Доступна ли пробная версия для Aspose.Slides?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
