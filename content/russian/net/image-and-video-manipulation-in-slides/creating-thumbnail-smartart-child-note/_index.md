---
title: Создание миниатюры для дочерней заметки SmartArt в Aspose.Slides
linktitle: Создание миниатюры для дочерней заметки SmartArt в Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как создавать миниатюры для дочерних заметок SmartArt с помощью Aspose.Slides для .NET. Пошаговое руководство с полным исходным кодом.
type: docs
weight: 15
url: /ru/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

## Введение в создание миниатюр для дочерней заметки SmartArt

В этом уроке мы рассмотрим процесс создания миниатюры дочерней заметки SmartArt с использованием библиотеки Aspose.Slides в .NET. Aspose.Slides — это мощный API, который позволяет разработчикам программно работать с презентациями PowerPoint. Мы будем идти шаг за шагом, демонстрируя код и объясняя каждую часть процесса.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

- Установлена Visual Studio (или любая другая среда разработки .NET).
-  Aspose.Slides для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).

## Настройка проекта

1. Создайте новый проект C# в Visual Studio.
2. Добавьте ссылку на библиотеку Aspose.Slides для .NET.

## Загрузка презентации

```csharp
using Aspose.Slides;

class Program
{
    static void Main(string[] args)
    {
        // Загрузите презентацию
        using (Presentation presentation = new Presentation("presentation.pptx"))
        {
            // Ваш код здесь
        }
    }
}
```

## Доступ к фигурам SmartArt

```csharp
// Предположим, у нас есть фигура SmartArt на первом слайде.
ISlide slide = presentation.Slides[0];
ISmartArt smartArt = (ISmartArt)slide.Shapes[0];

// Доступ к дочерним узлам
ISmartArtNodeCollection nodes = smartArt.AllNodes;
```

## Создание миниатюры для дочерней заметки

```csharp
foreach (ISmartArtNode node in nodes)
{
    // Предполагая, что узел имеет дочерние узлы
    ISmartArtNodeCollection childNodes = node.ChildNodes;

    // Создание миниатюры
    using (Bitmap thumbnail = childNodes.GenerateThumbnail(new Size(200, 150)))
    {
        //Сохраните миниатюру или выполните другие операции.
        thumbnail.Save($"thumbnail_{node.Text}.png");
    }
}
```

## Сохранение презентации с миниатюрами

```csharp
// Сохраните презентацию с миниатюрами
presentation.Save("presentation_with_thumbnails.pptx", SaveFormat.Pptx);
```

## Заключение

В этом уроке мы узнали, как создавать миниатюры для дочерних заметок SmartArt с помощью Aspose.Slides для .NET. Мы рассмотрели весь процесс: от загрузки презентации до доступа к фигурам SmartArt, создания миниатюр и сохранения презентации с миниатюрами.

## Часто задаваемые вопросы

### Как установить Aspose.Slides для .NET?

 Вы можете скачать Aspose.Slides для .NET с их сайта.[здесь](https://releases.aspose.com/slides/net/).

### Могу ли я создавать миниатюры и для других фигур?

Да, Aspose.Slides предоставляет различные методы для создания миниатюр для разных типов фигур, включая изображения, диаграммы и многое другое.

### Подходит ли Aspose.Slides как для личных, так и для коммерческих проектов?

Да, Aspose.Slides можно использовать как в личных, так и в коммерческих проектах. Однако перед развертыванием обязательно ознакомьтесь с условиями лицензирования.

### Могу ли я настроить внешний вид создаваемых миниатюр?

Абсолютно! Aspose.Slides позволяет вам настроить размер, качество и другие свойства создаваемых миниатюр в соответствии с вашими требованиями.

### Поддерживает ли Aspose.Slides другие языки программирования, кроме .NET?

Да, Aspose.Slides доступен для нескольких языков программирования, включая Java, Python и другие, что делает его универсальным для различных сред разработки.