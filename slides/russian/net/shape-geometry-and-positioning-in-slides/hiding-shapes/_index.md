---
"description": "Узнайте, как скрыть фигуры в слайдах PowerPoint с помощью Aspose.Slides для .NET. Настройте презентации программно с помощью этого пошагового руководства."
"linktitle": "Скрытие фигур на слайдах презентации с помощью Aspose.Slides"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Скрытие фигур в PowerPoint с помощью Aspose.Slides .NET Tutorial"
"url": "/ru/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Скрытие фигур в PowerPoint с помощью Aspose.Slides .NET Tutorial

## Введение
В динамичном мире презентаций настройка является ключом. Aspose.Slides для .NET предоставляет мощное решение для программного управления презентациями PowerPoint. Одним из распространенных требований является возможность скрывать определенные фигуры на слайде. Это руководство проведет вас через процесс скрытия фигур на слайдах презентации с помощью Aspose.Slides для .NET.
## Предпосылки
Прежде чем приступить к изучению руководства, убедитесь, что выполнены следующие предварительные условия:
- Aspose.Slides для .NET: Убедитесь, что у вас установлена библиотека Aspose.Slides. Вы можете скачать ее [здесь](https://releases.aspose.com/slides/net/).
- Среда разработки: настройте предпочтительную среду разработки для .NET.
- Базовые знания C#: ознакомьтесь с C#, поскольку примеры кода приведены на этом языке.
## Импорт пространств имен
Чтобы начать работать с Aspose.Slides, импортируйте необходимые пространства имен в свой проект C#. Это гарантирует вам доступ к требуемым классам и методам.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Теперь давайте разберем пример кода на несколько шагов для ясного и краткого понимания.
## Шаг 1: Настройте свой проект
Создайте новый проект C# и обязательно включите в него библиотеку Aspose.Slides.
## Шаг 2: Создайте презентацию
Создайте экземпляр `Presentation` класс, представляющий файл PowerPoint. Добавьте слайд и получите ссылку на него.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Шаг 3: Добавьте фигуры на слайд
Добавьте на слайд автофигуры, такие как прямоугольники и луны, с определенными размерами.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Шаг 4: Скрытие фигур на основе альтернативного текста
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
## Шаг 5: Сохраните презентацию
Сохраните измененную презентацию на диск в формате PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Заключение
Поздравляем! Вы успешно скрыли фигуры в презентации с помощью Aspose.Slides для .NET. Это открывает целый мир возможностей для создания динамических и настраиваемых слайдов программным способом.
---
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides с .NET Core?
Да, Aspose.Slides поддерживает .NET Core, обеспечивая гибкость вашей среды разработки.
### Можно ли скрыть фигуры на основе других условий, помимо альтернативного текста?
Конечно! Вы можете настроить логику скрытия на основе различных атрибутов, таких как тип формы, цвет или положение.
### Где я могу найти дополнительную документацию по Aspose.Slides?
Изучите документацию [здесь](https://reference.aspose.com/slides/net/) для получения подробной информации и примеров.
### Доступны ли временные лицензии для Aspose.Slides?
Да, вы можете получить временную лицензию. [здесь](https://purchase.aspose.com/temporary-license/) для целей тестирования.
### Как я могу получить поддержку сообщества для Aspose.Slides?
Присоединяйтесь к сообществу Aspose.Slides на [форум](https://forum.aspose.com/c/slides/11) для обсуждения и помощи.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}