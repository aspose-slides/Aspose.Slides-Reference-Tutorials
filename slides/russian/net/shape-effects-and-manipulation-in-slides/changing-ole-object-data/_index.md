---
title: Изменение данных объекта OLE в презентации с помощью Aspose.Slides
linktitle: Изменение данных объекта OLE в презентации с помощью Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Исследуйте возможности Aspose.Slides для .NET, позволяющие легко изменять данные объектов OLE. Улучшите свои презентации с помощью динамического контента.
weight: 25
url: /ru/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Изменение данных объекта OLE в презентации с помощью Aspose.Slides

## Введение
Создание динамичных и интерактивных презентаций PowerPoint является обычным требованием в современном цифровом мире. Одним из мощных инструментов для достижения этой цели является Aspose.Slides для .NET, надежная библиотека, которая позволяет разработчикам программно манипулировать и улучшать презентации PowerPoint. В этом уроке мы углубимся в процесс изменения данных объекта OLE (связывание и внедрение объектов) в слайдах презентации с помощью Aspose.Slides.
## Предварительные условия
Прежде чем начать работу с Aspose.Slides для .NET, убедитесь, что у вас есть следующие предварительные условия:
1. Среда разработки: настройте среду разработки с установленным .NET.
2.  Библиотека Aspose.Slides: загрузите и установите библиотеку Aspose.Slides для .NET. Вы можете найти библиотеку[здесь](https://releases.aspose.com/slides/net/).
3. Базовые знания: ознакомьтесь с основными понятиями программирования на C# и презентаций PowerPoint.
## Импортировать пространства имен
В свой проект C# импортируйте необходимые пространства имен для использования функций Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Шаг 1. Настройте свой проект
Начните с создания нового проекта C# и импорта библиотеки Aspose.Slides. Убедитесь, что ваш проект настроен правильно и у вас есть необходимые зависимости.
## Шаг 2. Доступ к презентации и слайду
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Шаг 3. Найдите объект OLE
Просмотрите все фигуры на слайде, чтобы найти рамку объекта OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Шаг 4. Чтение и изменение данных книги
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Чтение данных объекта в рабочей книге
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Изменение данных книги
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Изменение данных объекта кадра Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Шаг 5. Сохраните презентацию
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Заключение
Выполнив эти шаги, вы сможете легко изменять данные объекта OLE на слайдах презентации с помощью Aspose.Slides для .NET. Это открывает мир возможностей для создания динамичных и индивидуальных презентаций, адаптированных к вашим конкретным потребностям.
## Часто задаваемые вопросы
### Что такое Aspose.Slides для .NET?
Aspose.Slides для .NET — это мощная библиотека, которая позволяет разработчикам работать с презентациями PowerPoint программным способом, что позволяет легко манипулировать и улучшать их.
### Где я могу найти документацию Aspose.Slides?
 Документацию по Aspose.Slides для .NET можно найти.[здесь](https://reference.aspose.com/slides/net/).
### Как загрузить Aspose.Slides для .NET?
 Скачать библиотеку можно со страницы релиза.[здесь](https://releases.aspose.com/slides/net/).
### Доступна ли бесплатная пробная версия Aspose.Slides?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Где я могу получить поддержку Aspose.Slides для .NET?
 Для поддержки и обсуждения посетите[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
