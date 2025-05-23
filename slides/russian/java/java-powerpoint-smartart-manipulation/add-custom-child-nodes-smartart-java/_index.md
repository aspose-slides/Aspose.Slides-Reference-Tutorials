---
"description": "Узнайте, как добавлять пользовательские дочерние узлы в SmartArt в презентациях PowerPoint с помощью Java с Aspose.Slides. Улучшайте свои слайды с помощью профессиональной графики без усилий."
"linktitle": "Добавление пользовательских дочерних узлов в SmartArt с помощью Java"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Добавление пользовательских дочерних узлов в SmartArt с помощью Java"
"url": "/ru/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Добавление пользовательских дочерних узлов в SmartArt с помощью Java

## Введение
SmartArt — это мощная функция PowerPoint, которая позволяет пользователям быстро и легко создавать профессионально выглядящую графику. В этом уроке мы узнаем, как добавлять пользовательские дочерние узлы в SmartArt с помощью Java с Aspose.Slides.
## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлена Java.
2. Aspose.Slides для Java: Загрузите и установите Aspose.Slides для Java с сайта [здесь](https://releases.aspose.com/slides/java/).

## Импортные пакеты
Для начала импортируйте необходимые пакеты в ваш проект Java:
```java
import com.aspose.slides.*;
```
## Шаг 1: Загрузите презентацию
Загрузите презентацию PowerPoint, в которую вы хотите добавить пользовательские дочерние узлы к элементу SmartArt:
```java
String dataDir = "Your Document Directory";
// Загрузите нужную презентацию
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Шаг 2: Добавьте SmartArt на слайд
Теперь давайте добавим SmartArt на слайд:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Шаг 3: Перемещение фигуры SmartArt
Переместите фигуру SmartArt на новое место:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Шаг 4: Измените ширину фигуры
Измените ширину фигуры SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Шаг 5: Измените высоту фигуры
Измените высоту фигуры SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Шаг 6: Поверните фигуру
Поверните фигуру SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Шаг 7: Сохраните презентацию
Наконец, сохраните измененную презентацию:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Заключение
В этом уроке мы узнали, как добавлять пользовательские дочерние узлы в SmartArt с помощью Java с Aspose.Slides. Выполнив эти шаги, вы сможете улучшить свои презентации с помощью настраиваемой графики, сделав их более интересными и профессиональными.
## Часто задаваемые вопросы
### Можно ли добавлять различные типы макетов SmartArt с помощью Aspose.Slides для Java?
Да, Aspose.Slides для Java поддерживает различные макеты SmartArt, позволяя вам выбрать тот, который лучше всего соответствует потребностям вашей презентации.
### Совместим ли Aspose.Slides для Java с различными версиями PowerPoint?
Aspose.Slides для Java разработан для бесперебойной работы с различными версиями PowerPoint, обеспечивая совместимость и единообразие на разных платформах.
### Можно ли программно настроить внешний вид фигур SmartArt?
Конечно! С Aspose.Slides для Java вы можете программно настраивать внешний вид, размер, цвет и макет фигур SmartArt в соответствии с вашими предпочтениями в дизайне.
### Предоставляет ли Aspose.Slides для Java документацию и поддержку?
Да, вы можете найти подробную документацию и доступ к форумам поддержки сообщества на веб-сайте Aspose.
### Существует ли пробная версия Aspose.Slides для Java?
Да, вы можете загрузить бесплатную пробную версию Aspose.Slides для Java с веб-сайта, чтобы изучить ее функции и возможности перед покупкой. [здесь](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}