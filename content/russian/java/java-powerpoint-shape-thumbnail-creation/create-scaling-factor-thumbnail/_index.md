---
title: Создать миниатюру коэффициента масштабирования
linktitle: Создать миниатюру коэффициента масштабирования
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать миниатюры коэффициента масштабирования в Java с помощью Aspose.Slides для Java. Простое и понятное руководство с пошаговыми инструкциями.
type: docs
weight: 12
url: /ru/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## Введение
В этом уроке мы покажем вам процесс создания миниатюры коэффициента масштабирования с помощью Aspose.Slides для Java. Следуйте этим пошаговым инструкциям, чтобы достичь желаемого результата.
## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлен Java Development Kit (JDK).
- Библиотека Aspose.Slides for Java загружена и настроена в вашем Java-проекте.
- Базовое понимание языка программирования Java.

## Импортировать пакеты
Во-первых, импортируйте необходимые пакеты, необходимые для работы с Aspose.Slides, в ваш Java-код. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Теперь давайте разобьем приведенный пример на несколько шагов:
## Шаг 1. Установите каталог документов
Определите путь к каталогу документов, в котором находится файл презентации PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Заменять`"Your Document Directory"` с путем к вашему фактическому каталогу документов.
## Шаг 2. Создайте экземпляр объекта презентации
Создайте экземпляр класса Presentation, который будет представлять файл презентации PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Обязательно замените`"HelloWorld.pptx"` с именем файла презентации PowerPoint.
## Шаг 3. Создайте полномасштабное изображение
Создайте полномасштабное изображение нужного слайда из презентации.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Этот код извлекает миниатюру первой фигуры на первом слайде презентации.
## Шаг 4: Сохраните изображение
Сохраните созданное изображение на диск в формате PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Обязательно замените`"Scaling Factor Thumbnail_out.png"` с желаемым именем выходного файла.

## Заключение
В заключение вы успешно создали миниатюру коэффициента масштабирования с помощью Aspose.Slides для Java. Следуя предоставленным инструкциям, вы сможете легко интегрировать эту функцию в свои приложения Java.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Slides для Java с любой Java IDE?
Да, Aspose.Slides для Java можно использовать с любой интегрированной средой разработки Java (IDE), такой как Eclipse, IntelliJ IDEA или NetBeans.
### Доступна ли бесплатная пробная версия Aspose.Slides для Java?
 Да, вы можете воспользоваться бесплатной пробной версией Aspose.Slides для Java, посетив[Веб-сайт](https://releases.aspose.com/).
### Где я могу найти поддержку Aspose.Slides для Java?
 Вы можете найти поддержку Aspose.Slides для Java на сайте[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Как я могу приобрести Aspose.Slides для Java?
 Вы можете приобрести Aspose.Slides для Java на сайте[страница покупки](https://purchase.aspose.com/buy).
### Нужна ли мне временная лицензия для использования Aspose.Slides для Java?
 Да, вы можете получить временную лицензию в[страница временной лицензии](https://purchase.aspose.com/temporary-license/).