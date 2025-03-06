---
title: Добавьте узел помощника в SmartArt в Java PowerPoint
linktitle: Добавьте узел помощника в SmartArt в Java PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавить узел помощника в SmartArt в презентациях Java PowerPoint с помощью Aspose.Slides. Совершенствуйте свои навыки редактирования PowerPoint.
weight: 17
url: /ru/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте узел помощника в SmartArt в Java PowerPoint

## Введение
В этом уроке мы покажем вам процесс добавления узла-помощника в SmartArt в презентациях Java PowerPoint с использованием Aspose.Slides.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Комплект разработки Java (JDK): убедитесь, что в вашей системе установлена Java. Вы можете загрузить и установить последнюю версию JDK с сайта[здесь](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides для Java: Загрузите и установите библиотеку Aspose.Slides для Java с сайта[эта ссылка](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Для начала импортируйте необходимые пакеты в ваш Java-код:
```java
import com.aspose.slides.*;
```
## Шаг 1. Настройте презентацию
Начните с создания экземпляра Presentation, используя путь к файлу PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Шаг 2. Обход фигур
Просмотрите каждую фигуру на первом слайде презентации:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Шаг 3. Проверьте наличие фигур SmartArt
Проверьте, имеет ли фигура тип SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Шаг 4. Обход узлов SmartArt
Пройдите через все узлы фигуры SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Шаг 5. Проверьте наличие узла помощника
Проверьте, является ли узел узлом-помощником:
```java
if (node.isAssistant())
```
## Шаг 6. Установите для узла помощника значение «Нормальный»
Если узел является узлом-помощником, установите для него обычный узел:
```java
node.setAssistant(false);
```
## Шаг 7: Сохранить презентацию
Сохраните измененную презентацию:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Заключение
Поздравляем! Вы успешно добавили узел помощника в SmartArt в презентации Java PowerPoint с помощью Aspose.Slides.

## Часто задаваемые вопросы
### Могу ли я добавить несколько узлов помощника в SmartArt в презентации?
Да, вы можете добавить несколько узлов-помощников, повторив процесс для каждого узла.
### Подходит ли это руководство как для шаблонов PowerPoint, так и для PowerPoint?
Да, вы можете применить это руководство как к презентациям, так и к шаблонам PowerPoint.
### Совместим ли Aspose.Slides со всеми версиями PowerPoint?
Aspose.Slides поддерживает версии PowerPoint от 97-2003 до последней версии.
### Могу ли я настроить внешний вид узла-помощника?
Да, вы можете настроить внешний вид, используя различные свойства и методы, предоставляемые Aspose.Slides.
### Есть ли какое-либо ограничение на количество узлов в SmartArt?
SmartArt в PowerPoint поддерживает большое количество узлов, но рекомендуется сохранять его разумным для лучшей читаемости.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
