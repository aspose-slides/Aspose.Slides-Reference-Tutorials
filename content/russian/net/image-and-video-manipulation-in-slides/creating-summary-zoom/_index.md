---
title: Создание сводного масштаба на слайдах презентации с помощью Aspose.Slides
linktitle: Создание сводного масштаба на слайдах презентации с помощью Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как создавать увлекательные слайды презентаций с кратким масштабированием, используя Aspose.Slides для .NET. В нашем пошаговом руководстве представлены исходный код и советы по настройке для повышения интерактивности.
type: docs
weight: 16
url: /ru/net/image-and-video-manipulation-in-slides/creating-summary-zoom/
---

## Введение в Aspose.Slides для .NET

Aspose.Slides for .NET — это комплексная библиотека, которая позволяет разработчикам работать с презентациями PowerPoint в своих .NET-приложениях. Он предоставляет широкий спектр функций, включая создание, редактирование и управление слайдами, фигурами, текстом, изображениями и многим другим. В этом руководстве мы сосредоточимся на использовании Aspose.Slides для .NET для создания сводных слайдов с масштабированием в презентационных колодах.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

- Visual Studio установлена.
- Установлен .NET Framework или .NET Core.
-  Aspose.Slides для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).

## Настройка среды разработки

1. Создайте новый проект .NET в Visual Studio.
2. Добавьте ссылку на библиотеку Aspose.Slides в свой проект.

## Загрузка презентации

Для начала давайте загрузим существующую презентацию PowerPoint:

```csharp
using Aspose.Slides;

// Загрузите презентацию
using var presentation = new Presentation("path_to_your_presentation.pptx");
```

## Добавление слайдов в сводное масштабирование

Сводные слайды с масштабированием позволяют предоставить обзор нескольких слайдов на одном слайде. Давайте добавим слайды, которые мы хотим подвести итог:

```csharp
// Добавьте слайды для обобщения
var slideIndexes = new[] { 2, 3, 4 };
var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);
```

## Создание сводных слайдов с масштабированием

Теперь давайте создадим реальный слайд с масштабированием сводки, на котором будет отображаться обзор слайдов, которые мы добавили ранее:

```csharp
//Создать сводный слайд с масштабированием
var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });
```

## Настройка режима масштабирования сводки

Вы можете настроить поведение масштабирования сводки, например макет и внешний вид:

```csharp
// Настройте параметры масштабирования сводки
var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
if (zoomFrame != null)
{
    zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
    zoomFrame.Nodes[0].IsHidden = true; // Скрыть заголовок
    zoomFrame.Nodes[1].IsHidden = true; // Скрыть контент
}
```

## Добавление исходного кода для справки

Для вашего удобства вот полный исходный код для создания слайдов с краткими сведениями:

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        using var presentation = new Presentation("path_to_your_presentation.pptx");

        var slideIndexes = new[] { 2, 3, 4 };
        var summaryZoomSlide = presentation.Slides.AddSummaryZoomSlide(slideIndexes);

        var summaryZoom = presentation.Slides.AddSummaryZoomSlide(new[] { summaryZoomSlide });

        var zoomFrame = summaryZoom.Shapes.OfType<ISmartArt>().FirstOrDefault();
        if (zoomFrame != null)
        {
            zoomFrame.Nodes[0].TextFrame.Text = "Summary Zoom";
            zoomFrame.Nodes[0].IsHidden = true;
            zoomFrame.Nodes[1].IsHidden = true;
        }

        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Заключение

В этом руководстве мы рассмотрели, как использовать Aspose.Slides для .NET для создания сводных слайдов с масштабированием в презентационных колодах. Эта мощная функция может повысить интерактивность и привлекательность ваших презентаций, придавая вашему контенту профессиональный вид.

## Часто задаваемые вопросы

### Как загрузить Aspose.Slides для .NET?

 Вы можете скачать Aspose.Slides для .NET с сайта[Сайт Aspose.Slides](https://releases.aspose.com/slides/net/).

### Могу ли я настроить внешний вид слайдов сводной информации?

Да, вы можете настроить внешний вид сводных слайдов масштабирования, используя различные свойства, предоставляемые библиотекой Aspose.Slides.

### Совместим ли Aspose.Slides с .NET Framework и .NET Core?

Да, Aspose.Slides поддерживает как .NET Framework, так и .NET Core, что дает вам гибкость в выборе платформы разработки.

### Могу ли я создавать сводные слайды с масштабированием для определенных диапазонов слайдов?

Абсолютно! Вы можете выбрать слайды, которые хотите включить в масштаб сводки, используя их индексы слайдов.

### Как скрыть заголовок и содержимое на слайде сводной информации?

 Вы можете использовать`IsHidden` Свойство узлов SmartArt, чтобы скрыть заголовок и содержимое на слайде масштабирования сводки.