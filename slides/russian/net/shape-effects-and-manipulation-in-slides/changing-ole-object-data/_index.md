---
"description": "Исследуйте возможности Aspose.Slides для .NET в изменении данных объектов OLE без усилий. Улучшите свои презентации с помощью динамического контента."
"linktitle": "Изменение данных объекта OLE в презентации с помощью Aspose.Slides"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Изменение данных объекта OLE в презентации с помощью Aspose.Slides"
"url": "/ru/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Изменение данных объекта OLE в презентации с помощью Aspose.Slides

## Введение
Создание динамических и интерактивных презентаций PowerPoint является обычным требованием в современном цифровом мире. Одним из мощных инструментов для достижения этого является Aspose.Slides для .NET, надежная библиотека, которая позволяет разработчикам программно управлять презентациями PowerPoint и улучшать их. В этом руководстве мы углубимся в процесс изменения данных объектов OLE (Object Linking and Embedding) в слайдах презентации с помощью Aspose.Slides.
## Предпосылки
Прежде чем начать работу с Aspose.Slides для .NET, убедитесь, что выполнены следующие предварительные условия:
1. Среда разработки: настройте среду разработки с установленным .NET.
2. Библиотека Aspose.Slides: Загрузите и установите библиотеку Aspose.Slides for .NET. Библиотеку можно найти [здесь](https://releases.aspose.com/slides/net/).
3. Базовые знания: ознакомьтесь с основными концепциями программирования на языке C# и презентаций PowerPoint.
## Импорт пространств имен
В вашем проекте C# импортируйте необходимые пространства имен для использования функций Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Шаг 1: Настройте свой проект
Начните с создания нового проекта C# и импорта библиотеки Aspose.Slides. Убедитесь, что ваш проект настроен правильно и у вас есть необходимые зависимости.
## Шаг 2: Доступ к презентации и слайду
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Шаг 3: Найдите объект OLE
Пройдитесь по всем фигурам на слайде, чтобы найти рамку объекта OLE:
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
## Шаг 4: Чтение и изменение данных рабочей книги
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Чтение данных объекта в рабочей книге
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Изменение данных рабочей книги
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Изменение данных объекта Ole Frame
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Шаг 5: Сохраните презентацию
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Заключение
Выполнив эти шаги, вы сможете легко изменять данные объектов OLE в слайдах презентации с помощью Aspose.Slides для .NET. Это открывает целый мир возможностей для создания динамических и настраиваемых презентаций, соответствующих вашим конкретным потребностям.
## Часто задаваемые вопросы
### Что такое Aspose.Slides для .NET?
Aspose.Slides для .NET — это мощная библиотека, которая позволяет разработчикам работать с презентациями PowerPoint программным способом, обеспечивая легкое управление и улучшение.
### Где я могу найти документацию по Aspose.Slides?
Документацию по Aspose.Slides для .NET можно найти здесь [здесь](https://reference.aspose.com/slides/net/).
### Как загрузить Aspose.Slides для .NET?
Вы можете загрузить библиотеку со страницы релиза [здесь](https://releases.aspose.com/slides/net/).
### Существует ли бесплатная пробная версия Aspose.Slides?
Да, вы можете получить доступ к бесплатной пробной версии. [здесь](https://releases.aspose.com/).
### Где я могу получить поддержку по Aspose.Slides для .NET?
Для поддержки и обсуждений посетите [Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}