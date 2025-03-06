---
title: Создать миниатюру дочерней заметки SmartArt
linktitle: Создать миниатюру дочерней заметки SmartArt
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как создавать миниатюры дочерних заметок SmartArt на Java с помощью Aspose.Slides, что позволяет легко улучшить ваши презентации PowerPoint.
weight: 15
url: /ru/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создать миниатюру дочерней заметки SmartArt

## Введение
В этом уроке мы рассмотрим, как создавать миниатюры дочерних заметок SmartArt в Java с помощью Aspose.Slides. Aspose.Slides — это мощный Java API, который позволяет разработчикам программно работать с презентациями PowerPoint, позволяя им с легкостью создавать, изменять слайды и манипулировать ими.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующее:
1. В вашей системе установлен Java Development Kit (JDK).
2.  Библиотека Aspose.Slides for Java скачана и настроена в вашем проекте. Вы можете скачать библиотеку с[здесь](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Обязательно импортируйте необходимые пакеты в свой класс Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Шаг 1. Настройте свой проект
Убедитесь, что у вас настроен и настроен проект Java с использованием библиотеки Aspose.Slides.
## Шаг 2. Создайте презентацию
 Создайте экземпляр`Presentation` класс для представления файла PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Шаг 3. Добавьте SmartArt
Добавьте SmartArt на слайд презентации:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Шаг 4. Получите ссылку на узел
Получите ссылку на узел, используя его индекс:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Шаг 5. Получите миниатюру
Получите миниатюру узла SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Шаг 6. Сохраните миниатюру
Сохраните миниатюру изображения в файл:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Повторите эти шаги для каждого узла SmartArt по мере необходимости в вашей презентации.

## Заключение
В этом уроке мы узнали, как создавать миниатюры дочерних заметок SmartArt в Java с помощью Aspose.Slides. Обладая этими знаниями, вы можете программно улучшить свои презентации PowerPoint, с легкостью добавляя визуально привлекательные элементы.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Slides для управления существующими файлами PowerPoint?
Да, Aspose.Slides позволяет вам изменять существующие файлы PowerPoint, включая добавление, удаление или редактирование слайдов и их содержимого.
### Поддерживает ли Aspose.Slides экспорт слайдов в разные форматы файлов?
Абсолютно! Aspose.Slides поддерживает экспорт слайдов в различные форматы, включая PDF, изображения и HTML и другие.
### Подходит ли Aspose.Slides для автоматизации PowerPoint на уровне предприятия?
Да, Aspose.Slides предназначен для эффективного и надежного решения задач автоматизации PowerPoint на уровне предприятия.
### Могу ли я программно создавать сложные диаграммы SmartArt с помощью Aspose.Slides?
Конечно! Aspose.Slides обеспечивает комплексную поддержку для создания и управления диаграммами SmartArt различной сложности.
### Предлагает ли Aspose.Slides техническую поддержку для разработчиков?
 Да, Aspose.Slides предоставляет разработчикам специальную техническую поддержку через свои[Форум](https://forum.aspose.com/c/slides/11) и другие каналы.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
