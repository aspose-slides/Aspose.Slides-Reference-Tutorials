---
title: Создавайте потрясающие эскизные фигуры с помощью Aspose.Slides
linktitle: Создание эскизных фигур на слайдах презентации с помощью Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как добавлять креативные эскизы фигур к слайдам презентации с помощью Aspose.Slides для .NET. Увеличьте внешнюю привлекательность без особых усилий!
type: docs
weight: 13
url: /ru/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## Введение
Добро пожаловать в наше пошаговое руководство по созданию эскизов фигур в слайдах презентации с помощью Aspose.Slides для .NET. Если вы хотите добавить нотку творчества в свои презентации, наброски фигур придадут уникальную, нарисованную от руки эстетику. В этом уроке мы познакомим вас с процессом, разбив его на простые шаги, чтобы обеспечить удобство работы.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides для .NET. Вы можете скачать его[здесь](https://releases.aspose.com/slides/net/).
- Среда разработки: настройте среду разработки .NET с помощью предпочитаемой вами IDE.
## Импортировать пространства имен
Начните с импорта необходимых пространств имен в ваш проект .NET. Этот шаг гарантирует, что у вас есть доступ к классам и функциям, необходимым для работы с Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Шаг 1. Настройте проект
Начните с создания нового проекта .NET или открытия существующего. Обязательно включите Aspose.Slides в ссылки на свои проекты.
## Шаг 2. Инициализируйте Aspose.Slides
Инициализируйте Aspose.Slides, добавив следующий фрагмент кода. Это настраивает презентацию и определяет пути вывода для файла презентации и миниатюрного изображения.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Перейдите к следующим шагам...
}
```
## Шаг 3: Добавьте нарисованную форму
Теперь давайте добавим на слайд нарисованную фигуру. В этом примере мы добавим прямоугольник с эффектом эскиза от руки.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Преобразование формы в эскиз стиля от руки
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Шаг 4. Создайте миниатюру
Создайте миниатюру слайда, чтобы визуализировать нарисованную форму. Сохраните миниатюру в формате PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Шаг 5: Сохранить презентацию
Сохраните файл презентации с нарисованной формой.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Вот и все! Вы успешно создали презентацию с эскизами фигур, используя Aspose.Slides для .NET.
## Заключение
Добавление эскизов фигур к слайдам презентации может повысить визуальную привлекательность и привлечь аудиторию. С Aspose.Slides для .NET этот процесс становится простым, позволяя вам без труда раскрыть свой творческий потенциал.
## Часто задаваемые вопросы
### 1. Могу ли я настроить эффект эскиза?
Да, Aspose.Slides для .NET предоставляет различные варианты настройки эскизных эффектов. Обратитесь к[документация](https://reference.aspose.com/slides/net/) для получения подробной информации.
### 2. Доступна ли бесплатная пробная версия?
 Конечно! Вы можете изучить бесплатную пробную версию Aspose.Slides для .NET.[здесь](https://releases.aspose.com/).
### 3. Где я могу получить поддержку?
 Для получения любой помощи или вопросов посетите[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Как я могу приобрести Aspose.Slides для .NET?
 Чтобы приобрести Aspose.Slides для .NET, посетите[страница покупки](https://purchase.aspose.com/buy).
### 5. Предлагаете ли вы временные лицензии?
 Да, временные лицензии доступны.[здесь](https://purchase.aspose.com/temporary-license/).