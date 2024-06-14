---
title: Добавьте пользовательские дочерние узлы в SmartArt с помощью Java
linktitle: Добавьте пользовательские дочерние узлы в SmartArt с помощью Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как добавлять пользовательские дочерние узлы в SmartArt в презентациях PowerPoint с помощью Java с Aspose.Slides. Улучшите свои слайды с помощью профессиональной графики без особых усилий.
type: docs
weight: 11
url: /ru/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---
## Введение
SmartArt — это мощная функция PowerPoint, которая позволяет пользователям быстро и легко создавать профессионально выглядящую графику. В этом уроке мы научимся добавлять пользовательские дочерние узлы в SmartArt с помощью Java с помощью Aspose.Slides.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. Комплект разработки Java (JDK): убедитесь, что в вашей системе установлена Java.
2.  Aspose.Slides для Java: Загрузите и установите Aspose.Slides для Java с сайта[здесь](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Для начала импортируйте необходимые пакеты в ваш Java-проект:
```java
import com.aspose.slides.*;
```
## Шаг 1. Загрузите презентацию
Загрузите презентацию PowerPoint, в которую вы хотите добавить пользовательские дочерние узлы в SmartArt:
```java
String dataDir = "Your Document Directory";
// Загрузите нужную презентацию
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Шаг 2. Добавьте SmartArt на слайд
Теперь давайте добавим SmartArt на слайд:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Шаг 3. Переместите фигуру SmartArt
Переместите фигуру SmartArt в новое положение:
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
В этом уроке мы узнали, как добавлять пользовательские дочерние узлы в SmartArt с помощью Java с Aspose.Slides. Следуя этим шагам, вы сможете улучшить свои презентации с помощью индивидуальной графики, сделав их более привлекательными и профессиональными.
## Часто задаваемые вопросы
### Могу ли я добавлять различные типы макетов SmartArt с помощью Aspose.Slides для Java?
Да, Aspose.Slides для Java поддерживает различные макеты SmartArt, что позволяет вам выбрать тот, который лучше всего соответствует вашим потребностям в презентации.
### Совместим ли Aspose.Slides для Java с различными версиями PowerPoint?
Aspose.Slides для Java разработан для бесперебойной работы с различными версиями PowerPoint, обеспечивая совместимость и согласованность на разных платформах.
### Могу ли я программно настроить внешний вид фигур SmartArt?
Абсолютно! С помощью Aspose.Slides для Java вы можете программно настроить внешний вид, размер, цвет и расположение фигур SmartArt в соответствии с вашими дизайнерскими предпочтениями.
### Предоставляет ли Aspose.Slides для Java документацию и поддержку?
Да, вы можете найти подробную документацию и доступ к форумам поддержки сообщества на веб-сайте Aspose.
### Доступна ли пробная версия Aspose.Slides для Java?
 Да, вы можете загрузить бесплатную пробную версию Aspose.Slides для Java с веб-сайта, чтобы изучить ее функции и возможности перед покупкой.[здесь](https://releases.aspose.com/slides/java/).