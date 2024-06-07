---
title: Соедините фигуры с помощью сайтов подключения в PowerPoint
linktitle: Соедините фигуры с помощью сайтов подключения в PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как соединять фигуры в PowerPoint с помощью Aspose.Slides для Java. Автоматизируйте свои презентации без особых усилий.
type: docs
weight: 19
url: /ru/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---
## Введение
В этом уроке мы рассмотрим, как соединить фигуры с помощью сайтов соединения в PowerPoint с помощью Aspose.Slides для Java. Эта мощная библиотека позволяет нам программно манипулировать презентациями PowerPoint, делая такие задачи, как соединение фигур, простыми и эффективными.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1.  Комплект разработки Java (JDK): убедитесь, что в вашей системе установлена Java. Вы можете скачать и установить его с сайта[Веб-сайт](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides для Java: Загрузите и установите Aspose.Slides для Java с сайта[страница загрузки](https://releases.aspose.com/slides/java/).
3. Интегрированная среда разработки (IDE): выберите IDE для разработки на Java, например IntelliJ IDEA, Eclipse или NetBeans.

## Импортировать пакеты
Для начала импортируйте необходимые пакеты в свой Java-проект:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Шаг 1. Доступ к коллекции фигур
Доступ к коллекции фигур для выбранного слайда:
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать экземпляр класса Presentation, представляющего файл PPTX.
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Шаг 2. Добавление формы соединителя
Добавьте фигуру соединителя в коллекцию фигур слайда:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Шаг 3. Добавление автофигур
Добавьте автофигуры, такие как эллипс и прямоугольник:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Шаг 4. Соединение фигур с соединителями
Присоедините фигуры к соединителю:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Шаг 5. Настройка индекса сайта подключения
Установите желаемый индекс места соединения для фигур:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Заключение
В этом уроке мы научились соединять фигуры с помощью сайтов соединения в PowerPoint с помощью Aspose.Slides для Java. Благодаря этим знаниям вы теперь можете с легкостью автоматизировать и настраивать презентации PowerPoint.
## Часто задаваемые вопросы
### Можно ли использовать Aspose.Slides for Java для других задач манипуляции с PowerPoint?
Да, Aspose.Slides for Java предоставляет широкий спектр функций для создания, редактирования и преобразования презентаций PowerPoint.
### Можно ли использовать Aspose.Slides для Java бесплатно?
 Aspose.Slides for Java — это коммерческая библиотека, но вы можете изучить ее возможности, воспользовавшись бесплатной пробной версией. Посещать[здесь](https://releases.aspose.com/) для начала.
### Могу ли я получить поддержку, если у меня возникнут какие-либо проблемы при использовании Aspose.Slides для Java?
 Да, вы можете получить поддержку на форумах сообщества Aspose.[здесь](https://forum.aspose.com/c/slides/11).
### Доступны ли временные лицензии для Aspose.Slides для Java?
 Да, временные лицензии доступны для тестирования и оценки. Вы можете получить один[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу приобрести лицензию на Aspose.Slides для Java?
Вы можете приобрести лицензию на сайте Aspose.[здесь](https://purchase.aspose.com/buy).