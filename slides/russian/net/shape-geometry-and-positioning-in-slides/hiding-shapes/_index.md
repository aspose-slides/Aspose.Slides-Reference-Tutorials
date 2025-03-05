---
title: Скройте фигуры в PowerPoint с помощью руководства Aspose.Slides .NET
linktitle: Скрытие фигур на слайдах презентации с помощью Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как скрыть фигуры в слайдах PowerPoint с помощью Aspose.Slides для .NET. Настраивайте презентации программно с помощью этого пошагового руководства.
type: docs
weight: 21
url: /ru/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Введение
В динамичном мире презентаций ключевое значение имеет настройка. Aspose.Slides for .NET предоставляет мощное решение для программного управления презентациями PowerPoint. Одним из общих требований является возможность скрывать определенные фигуры на слайде. Это руководство проведет вас через процесс скрытия фигур на слайдах презентации с помощью Aspose.Slides для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
-  Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides. Вы можете скачать его[здесь](https://releases.aspose.com/slides/net/).
- Среда разработки: настройте предпочитаемую среду разработки для .NET.
- Базовые знания C#. Ознакомьтесь с C#, поскольку приведенные примеры кода написаны на этом языке.
## Импортировать пространства имен
Чтобы начать работу с Aspose.Slides, импортируйте необходимые пространства имен в свой проект C#. Это гарантирует, что у вас есть доступ к необходимым классам и методам.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Теперь давайте разобьем пример кода на несколько шагов для ясного и краткого понимания.
## Шаг 1. Настройте свой проект
Создайте новый проект C# и обязательно включите библиотеку Aspose.Slides.
## Шаг 2. Создайте презентацию
 Создайте экземпляр`Presentation` класс, представляющий файл PowerPoint. Добавьте слайд и получите ссылку на него.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Шаг 3. Добавьте фигуры на слайд
Добавьте на слайд автофигуры, например прямоугольники и луны, с определенными размерами.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Шаг 4. Скройте фигуры на основе альтернативного текста
Укажите альтернативный текст и скройте фигуры, соответствующие этому тексту.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Шаг 5. Сохраните презентацию
Сохраните измененную презентацию на диск в формате PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Заключение
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides с .NET Core?
Да, Aspose.Slides поддерживает .NET Core, обеспечивая гибкость вашей среды разработки.
### Могу ли я скрыть фигуры на основе условий, отличных от альтернативного текста?
Абсолютно! Вы можете настроить логику скрытия на основе различных атрибутов, таких как тип фигуры, цвет или положение.
### Где я могу найти дополнительную документацию по Aspose.Slides?
 Изучите документацию[здесь](https://reference.aspose.com/slides/net/)для более подробной информации и примеров.
### Доступны ли временные лицензии для Aspose.Slides?
 Да, вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/)в целях тестирования.
### Как я могу получить поддержку сообщества для Aspose.Slides?
 Присоединяйтесь к сообществу Aspose.Slides на[Форум](https://forum.aspose.com/c/slides/11) за обсуждения и помощь.