---
title: Aspose.Slides — Создание групповых фигур в .NET
linktitle: Создание групповых фигур на слайдах презентации с помощью Aspose.Slides
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Узнайте, как создавать групповые фигуры в PowerPoint с помощью Aspose.Slides для .NET. Следуйте нашему пошаговому руководству для создания визуально привлекательных презентаций.
type: docs
weight: 11
url: /ru/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Введение
Если вы хотите повысить визуальную привлекательность слайдов презентации и более эффективно организовать контент, включение групповых фигур — мощное решение. Aspose.Slides for .NET обеспечивает простой способ создания групповых фигур и управления ими в презентациях PowerPoint. В этом уроке мы рассмотрим процесс создания групповых фигур с помощью Aspose.Slides, разбив его на простые для выполнения шаги.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующее:
-  Aspose.Slides для .NET: убедитесь, что у вас установлена библиотека Aspose.Slides. Вы можете скачать его с сайта[Веб-сайт](https://releases.aspose.com/slides/net/).
- Среда разработки: настройте рабочую среду с помощью .NET-совместимой IDE, например Visual Studio.
- Базовые знания C#: ознакомьтесь с основами языка программирования C#.
## Импортировать пространства имен
В своем проекте C# начните с импорта необходимых пространств имен:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Шаг 1. Создание экземпляра класса представления

 Создайте экземпляр`Presentation` class и укажите каталог, в котором хранятся ваши документы:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Продолжайте выполнять следующие шаги в этом блоке использования.
}
```

## Шаг 2. Доступ к первому слайду

Получите первый слайд из презентации:

```csharp
ISlide sld = pres.Slides[0];
```

## Шаг 3. Доступ к коллекции фигур

Доступ к коллекции фигур на слайде:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Шаг 4. Добавление фигуры группы

Добавьте фигуру группы на слайд:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Шаг 5. Добавление фигур внутри фигуры группы

Заполните фигуру группы отдельными фигурами:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Шаг 6: Добавление рамки формы группы

Определите рамку для всей формы группы:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Шаг 7. Сохраните презентацию

Сохраните измененную презентацию в указанном вами каталоге:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Повторите эти шаги в своем приложении C#, чтобы успешно создать групповые фигуры на слайдах презентации с помощью Aspose.Slides.

## Заключение
В этом уроке мы рассмотрели процесс создания групповых фигур с помощью Aspose.Slides для .NET. Выполнив эти шаги, вы сможете повысить визуальную привлекательность и организацию своих презентаций PowerPoint.
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides с последней версией .NET?
 Да, Aspose.Slides регулярно обновляется для поддержки последних версий .NET. Проверить[документация](https://reference.aspose.com/slides/net/) для получения подробной информации о совместимости.
### Могу ли я попробовать Aspose.Slides перед покупкой?
 Абсолютно! Вы можете скачать бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Где я могу найти поддержку для запросов, связанных с Aspose.Slides?
 Посетите Aspose.Slides[Форум](https://forum.aspose.com/c/slides/11) за поддержку сообщества и обсуждения.
### Как получить временную лицензию на Aspose.Slides?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу приобрести полную лицензию на Aspose.Slides?
 Вы можете купить лицензию на сайте[страница покупки](https://purchase.aspose.com/buy).
