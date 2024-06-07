---
title: Создать миниатюру формы границ
linktitle: Создать миниатюру формы границ
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать миниатюры фигур с границами, используя Aspose.Slides для Java. Это пошаговое руководство проведет вас через этот процесс.
type: docs
weight: 10
url: /ru/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## Введение
Aspose.Slides for Java — это мощная библиотека, которая позволяет разработчикам Java программно создавать, манипулировать и конвертировать презентации PowerPoint. В этом уроке мы научимся создавать миниатюрное изображение фигуры с границами, используя Aspose.Slides для Java.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующее:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Slides для Java загружена и добавлена в ваш проект. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Убедитесь, что вы импортировали необходимые пакеты в свой Java-код:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Шаг 1. Настройте свой проект
Создайте новый проект Java в предпочитаемой вами среде IDE и добавьте библиотеку Aspose.Slides for Java в зависимости вашего проекта.
## Шаг 2. Создайте экземпляр объекта презентации
 Создать экземпляр`Presentation` объект, указав путь к файлу презентации PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Шаг 3. Создайте миниатюру формы границ
Теперь давайте создадим миниатюрное изображение фигуры с границами из презентации.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Заключение
В этом уроке мы узнали, как создать миниатюрное изображение фигуры с границами, используя Aspose.Slides для Java. Выполнив эти шаги, вы сможете легко программно создавать эскизы фигур в презентациях PowerPoint.
## Часто задаваемые вопросы
### Могу ли я создавать миниатюры для определенных фигур на слайде?
Да, вы можете получить доступ к отдельным фигурам внутри слайда и создавать для них миниатюры с помощью Aspose.Slides for Java.
### Совместим ли Aspose.Slides для Java со всеми версиями файлов PowerPoint?
Aspose.Slides для Java поддерживает различные форматы файлов PowerPoint, включая PPT, PPTX, PPS, PPSX и другие.
### Могу ли я настроить внешний вид созданных миниатюр изображений?
Да, вы можете настроить свойства миниатюр изображений, такие как размер и качество, в соответствии с вашими требованиями.
### Поддерживает ли Aspose.Slides for Java другие функции, помимо создания миниатюр?
Да, Aspose.Slides for Java предоставляет обширные функциональные возможности для работы с презентациями PowerPoint, включая манипулирование слайдами, извлечение текста и создание диаграмм.
### Доступна ли пробная версия Aspose.Slides для Java?
 Да, вы можете скачать бесплатную пробную версию с сайта[здесь](https://releases.aspose.com/).