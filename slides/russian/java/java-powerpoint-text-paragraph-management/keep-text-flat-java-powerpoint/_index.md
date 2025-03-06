---
title: Сохраняйте текст плоским в Java PowerPoint
linktitle: Сохраняйте текст плоским в Java PowerPoint
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как сделать текст плоским в презентациях Java PowerPoint с помощью Aspose.Slides для Java. Следуйте нашему пошаговому руководству для эффективного манипулирования текстом.
type: docs
weight: 11
url: /ru/java/java-powerpoint-text-paragraph-management/keep-text-flat-java-powerpoint/
---
## Введение
В области манипуляций с PowerPoint на основе Java Aspose.Slides for Java представляет собой надежный и универсальный набор инструментов. Являетесь ли вы опытным разработчиком или новичком, желающим улучшить свои презентации программным способом, Aspose.Slides for Java предлагает полный набор функций для беспрепятственного создания, изменения и управления презентациями PowerPoint. В этом руководстве рассматривается конкретная функциональность: сохранение плоского текста в слайдах PowerPoint с помощью Aspose.Slides для Java. Следуя этому руководству, вы узнаете, как манипулировать форматированием текста для достижения точных результатов презентации.
## Предварительные условия
Прежде чем углубляться в это руководство, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлен Java Development Kit (JDK).
- Базовое понимание языка программирования Java.
- Знакомство с интегрированной средой разработки (IDE), такой как Eclipse или IntelliJ IDEA.
-  Скачал и установил библиотеку Aspose.Slides for Java. Вы можете получить его от[здесь](https://releases.aspose.com/slides/java/).

## Импортировать пакеты
Начните с импорта необходимых пакетов из Aspose.Slides for Java в ваш файл Java:
```java
import com.aspose.slides.AutoShape;
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import javax.imageio.ImageIO;
import java.io.File;
import java.io.IOException;
```
### Шаг 1. Загрузите презентацию PowerPoint
Начните с загрузки файла презентации PowerPoint (`pptxFileName`) и определите выходной путь (`resultPath`) для миниатюры обработанного слайда:
```java
String pptxFileName = "Your Document Directory";
String resultPath = "Your Output Directory" + "KeepTextFlat_out.png";
Presentation pres = new Presentation(pptxFileName);
```
## Шаг 2. Доступ к текстовым фигурам и манипулирование ими
Доступ к текстовым фигурам на первом слайде загруженной презентации (`pres` ). Настроить`KeepTextFlat` свойство для каждой фигуры соответственно:
```java
try {
    IAutoShape shape1 = (AutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);
    IAutoShape shape2 = (AutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(1);
    // Установите свойство KeepTextFlat для каждой фигуры.
    shape1.getTextFrame().getTextFrameFormat().setKeepTextFlat(false);
    shape2.getTextFrame().getTextFrameFormat().setKeepTextFlat(true);
    // Создайте миниатюру слайда и сохраните ее в формате PNG.
    ImageIO.write(pres.getSlides().get_Item(0).getThumbnail(4 / 3f, 4 / 3f), "PNG", new File(resultPath));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```

## Заключение
Овладение искусством управления презентациями PowerPoint программным способом открывает двери для безграничных творческих возможностей. С Aspose.Slides for Java задачи, которые когда-то казались сложными, становятся простыми и эффективными. Понимая, как сохранить текст на слайдах плоским с помощью Aspose.Slides for Java, вы сможете адаптировать презентации точно к своим потребностям, обеспечивая ясность и эффектность.
## Часто задаваемые вопросы
### Что такое Aspose.Slides для Java?
Aspose.Slides for Java — это Java API, который позволяет разработчикам программно создавать, изменять и конвертировать презентации PowerPoint.
### Где я могу найти документацию по Aspose.Slides для Java?
Вы можете изучить подробную документацию[здесь](https://reference.aspose.com/slides/java/).
### Как я могу получить бесплатную пробную версию Aspose.Slides для Java?
 Посещать[здесь](https://releases.aspose.com/) чтобы загрузить бесплатную пробную версию.
### Подходит ли Aspose.Slides для Java для коммерческого использования?
 Да, вы можете приобрести лицензию[здесь](https://purchase.aspose.com/buy).
### Где я могу получить поддержку сообщества для Aspose.Slides для Java?
 Присоединяйтесь к форуму сообщества Aspose.Slides.[здесь](https://forum.aspose.com/c/slides/11).