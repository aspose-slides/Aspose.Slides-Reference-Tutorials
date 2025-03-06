---
title: Организация типа макета диаграммы в SmartArt с помощью Java
linktitle: Организация типа макета диаграммы в SmartArt с помощью Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Освойте организацию типов макетов диаграмм в SmartArt, используя Java с Aspose.Slides, легко улучшая визуальные эффекты презентации.
weight: 13
url: /ru/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Организация типа макета диаграммы в SmartArt с помощью Java

## Введение
В этом уроке мы рассмотрим процесс организации типа макета диаграммы в SmartArt с использованием Java, в частности с использованием библиотеки Aspose.Slides. SmartArt в презентациях может значительно повысить визуальную привлекательность и ясность ваших данных, поэтому необходимо освоить их манипулирование.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Slides скачана и настроена. Если вы еще этого не сделали, загрузите его с[здесь](https://releases.aspose.com/slides/java/).
3. Базовое понимание программирования на Java.

## Импортировать пакеты
Сначала импортируйте необходимые пакеты:
```java
import com.aspose.slides.*;
```
Давайте разобьем приведенный пример на несколько этапов:
## Шаг 1. Инициализация объекта презентации
```java
Presentation presentation = new Presentation();
```
Создайте новый объект презентации.
## Шаг 2. Добавьте SmartArt на слайд
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Добавьте SmartArt на нужный слайд с указанными размерами и типом макета.
## Шаг 3. Установите макет организационной диаграммы
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Установите тип макета организационной диаграммы. В этом примере мы используем макет «Висящий слева».
## Шаг 4. Сохраните презентацию
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Сохраните презентацию с организованным макетом диаграммы.

## Заключение
Освоение организации типов макетов диаграмм в SmartArt с использованием Java позволит вам с легкостью создавать визуально привлекательные презентации. С Aspose.Slides этот процесс становится упрощенным и эффективным, что позволяет вам сосредоточиться на создании эффективного контента.
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides с различными средами разработки Java?
Да, Aspose.Slides совместим с различными средами разработки Java, обеспечивая гибкость для разработчиков.
### Могу ли я настроить внешний вид элементов SmartArt с помощью Aspose.Slides?
Безусловно, Aspose.Slides предоставляет широкие возможности настройки элементов SmartArt, что позволяет вам адаптировать их к вашим конкретным требованиям.
### Предлагает ли Aspose.Slides полную документацию для разработчиков?
Да, разработчики могут обратиться к подробной документации, предоставленной Aspose.Slides для Java, где можно получить информацию о его функциях и использовании.
### Доступна ли пробная версия для Aspose.Slides?
Да, вы можете получить доступ к бесплатной пробной версии Aspose.Slides, чтобы изучить ее возможности, прежде чем принимать решение о покупке.
### Где я могу получить поддержку по вопросам, связанным с Aspose.Slides?
 Для получения любой помощи или вопросов относительно Aspose.Slides вы можете посетить форум поддержки.[здесь](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
