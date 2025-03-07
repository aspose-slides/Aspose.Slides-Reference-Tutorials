---
title: Создание миниатюры с коэффициентом масштабирования формы в Aspose.Slides
linktitle: Создание миниатюры с коэффициентом масштабирования формы в Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Научитесь создавать миниатюры изображений PowerPoint с определенными границами, используя Aspose.Slides для .NET. Следуйте нашему пошаговому руководству для бесшовной интеграции.
weight: 12
url: /ru/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание миниатюры с коэффициентом масштабирования формы в Aspose.Slides

## Введение
Добро пожаловать в наше подробное руководство по созданию миниатюр с границами фигур в Aspose.Slides для .NET. Aspose.Slides — это мощная библиотека, которая позволяет разработчикам беспрепятственно работать с презентациями PowerPoint в своих .NET-приложениях. В этом уроке мы углубимся в процесс создания миниатюр с конкретными границами фигур в презентации с помощью Aspose.Slides.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).
- Среда разработки: на вашем компьютере должна быть установлена подходящая среда разработки для .NET, например Visual Studio.
## Импортировать пространства имен
В вашем .NET-приложении начните с импорта необходимых пространств имен для доступа к функциям Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Шаг 1. Настройте презентацию
Начните с создания экземпляра класса Presentation, который представляет файл презентации PowerPoint, с которым вы хотите работать:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Здесь находится ваш код для создания миниатюр.
}
```
## Шаг 2. Создайте полномасштабное изображение
В блоке «Презентация» создайте полномасштабное изображение фигуры, для которой вы хотите создать миниатюру:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    // Здесь находится ваш код для сохранения изображения.
}
```
## Шаг 3. Сохраните изображение на диск.
Сохраните созданное изображение на диск, указав формат (в данном случае PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Заключение
Поздравляем! Вы успешно научились создавать миниатюры фигур с границами с помощью Aspose.Slides для .NET. Эта функция может быть невероятно полезна, когда вам нужно программно создавать изображения фигур определенного размера в презентациях PowerPoint.
## Часто задаваемые вопросы
### Вопрос 1: Могу ли я использовать Aspose.Slides с другими платформами .NET?
Да, Aspose.Slides совместим с различными платформами .NET, обеспечивая гибкость интеграции с различными типами приложений.
### Вопрос 2: Существует ли пробная версия для Aspose.Slides?
 Да, вы можете изучить функциональность Aspose.Slides, загрузив пробную версию.[здесь](https://releases.aspose.com/).
### В3: Как я могу получить временную лицензию на Aspose.Slides?
 Вы можете приобрести временную лицензию на Aspose.Slides, посетив[эта ссылка](https://purchase.aspose.com/temporary-license/).
### Вопрос 4. Где я могу найти дополнительную поддержку для Aspose.Slides?
 По любым вопросам или помощи посетите форум поддержки Aspose.Slides.[здесь](https://forum.aspose.com/c/slides/11).
### Вопрос 5: Могу ли я приобрести Aspose.Slides для .NET?
 Конечно! Чтобы приобрести Aspose.Slides для .NET, посетите страницу покупки.[здесь](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
