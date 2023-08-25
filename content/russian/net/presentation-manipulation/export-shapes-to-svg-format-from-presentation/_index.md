---
title: Экспорт фигур в формат SVG из презентации
linktitle: Экспорт фигур в формат SVG из презентации
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как экспортировать фигуры из презентации PowerPoint в формат SVG с помощью Aspose.Slides для .NET. Пошаговое руководство с исходным кодом. Эффективно извлекайте формы для различных приложений.
type: docs
weight: 16
url: /ru/net/presentation-manipulation/export-shapes-to-svg-format-from-presentation/
---
Это руководство проведет вас через процесс экспорта фигур из презентации в формат SVG с использованием библиотеки Aspose.Slides для .NET. Aspose.Slides — это мощный API, который позволяет программно работать с файлами Microsoft PowerPoint. В этом уроке вы узнаете, как извлекать фигуры из презентации и сохранять их в формате SVG с помощью C#.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующие предварительные условия:

- Visual Studio установлена
- Базовое понимание программирования на C#.
-  Aspose.Slides для библиотеки .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/slides/net/).

## Пошаговое руководство

Выполните следующие действия, чтобы экспортировать фигуры в формат SVG из презентации:

### 1. Создайте новый проект

Откройте Visual Studio и создайте новый проект C#.

### 2. Добавьте ссылку на Aspose.Slides

В своем проекте щелкните правой кнопкой мыши «Ссылки» в обозревателе решений, затем нажмите «Добавить ссылку». Найдите и выберите загруженную DLL Aspose.Slides.

### 3. Загрузите презентацию

```csharp
using Aspose.Slides;

// Загрузите презентацию
Presentation presentation = new Presentation("presentation.pptx");
```

### 4. Перебор фигур

```csharp
foreach (IShape shape in presentation.Slides[0].Shapes)
{
    // Проверьте, является ли фигура фигурой группы
    if (shape is IGroupShape groupShape)
    {
        foreach (IShape groupChildShape in groupShape.Shapes)
        {
            // Экспортируйте фигуру в SVG.
            string svgFileName = $"shape_{groupChildShape.Id}.svg";
            groupChildShape.WriteAsSvg(svgFileName);
        }
    }
    else
    {
        // Экспортируйте фигуру в SVG.
        string svgFileName = $"shape_{shape.Id}.svg";
        shape.WriteAsSvg(svgFileName);
    }
}
```

### 5. Сохраните файлы SVG

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx); // Сохранить изменения в презентации
```

## Часто задаваемые вопросы

### Как установить Aspose.Slides для .NET?

 Вы можете загрузить библиотеку Aspose.Slides для .NET с сайта[здесь](https://releases.aspose.com/slides/net/). Следуйте инструкциям по установке, приведенным в документации.

### Как загрузить презентацию PowerPoint с помощью Aspose.Slides?

 Вы можете загрузить презентацию с помощью`Presentation` конструктор класса. Укажите путь к файлу PowerPoint в качестве параметра.

### Как экспортировать фигуру в формат SVG?

 Вы можете использовать`WriteAsSvg` метод на`IShape` объект, чтобы экспортировать его в формат SVG. Вам необходимо указать имя файла для вывода SVG.

## Заключение

В этом уроке вы узнали, как экспортировать фигуры из презентации PowerPoint в формат SVG с помощью библиотеки Aspose.Slides для .NET. Это может быть полезно, когда вам нужно извлечь отдельные фигуры для использования в других приложениях или платформах, поддерживающих графику SVG. Aspose.Slides предоставляет простой и эффективный способ добиться этого программно.

 Более подробную информацию и расширенные функции см.[Справочник по API Aspose.Slides для .NET](https://reference.aspose.com/slides/net/).