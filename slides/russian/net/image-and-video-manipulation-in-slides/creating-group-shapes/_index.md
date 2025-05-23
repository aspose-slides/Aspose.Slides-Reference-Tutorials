---
"description": "Узнайте, как создавать групповые фигуры в PowerPoint с помощью Aspose.Slides для .NET. Следуйте нашему пошаговому руководству для создания визуально привлекательных презентаций."
"linktitle": "Создание групповых фигур на слайдах презентации с помощью Aspose.Slides"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Aspose.Slides — Создание групповых фигур в .NET"
"url": "/ru/net/image-and-video-manipulation-in-slides/creating-group-shapes/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — Создание групповых фигур в .NET

## Введение
Если вы хотите улучшить визуальную привлекательность слайдов презентации и организовать контент более эффективно, включение групповых фигур является мощным решением. Aspose.Slides для .NET обеспечивает простой способ создания и управления групповыми фигурами в ваших презентациях PowerPoint. В этом руководстве мы рассмотрим процесс создания групповых фигур с помощью Aspose.Slides, разбив его на простые для выполнения шаги.
## Предпосылки
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующее:
- Aspose.Slides для .NET: Убедитесь, что у вас установлена библиотека Aspose.Slides. Вы можете загрузить ее с [веб-сайт](https://releases.aspose.com/slides/net/).
- Среда разработки: настройте рабочую среду с совместимой с .NET IDE, например Visual Studio.
- Базовые знания C#: ознакомьтесь с основами языка программирования C#.
## Импорт пространств имен
В своем проекте C# начните с импорта необходимых пространств имен:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Шаг 1: Создание экземпляра класса представления

Создайте экземпляр `Presentation` class и укажите каталог, в котором хранятся ваши документы:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Продолжайте выполнять следующие шаги в этом блоке using.
}
```

## Шаг 2: Получите доступ к первому слайду

Извлеките первый слайд из презентации:

```csharp
ISlide sld = pres.Slides[0];
```

## Шаг 3: Доступ к коллекции фигур

Доступ к коллекции фигур на слайде:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Шаг 4: Добавление групповой фигуры

Добавьте на слайд фигуру группы:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Шаг 5: Добавление фигур внутрь групповой фигуры

Заполните групповую фигуру отдельными фигурами:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Шаг 6: Добавление рамки групповой формы

Определите рамку для всей формы группы:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Шаг 7: Сохраните презентацию

Сохраните измененную презентацию в указанном вами каталоге:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Повторите эти шаги в своем приложении C#, чтобы успешно создать групповые фигуры на слайдах презентации с помощью Aspose.Slides.

## Заключение
В этом уроке мы изучили процесс создания групповых фигур с помощью Aspose.Slides для .NET. Выполняя эти шаги, вы можете улучшить визуальную привлекательность и организацию ваших презентаций PowerPoint.
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides с последней версией .NET?
Да, Aspose.Slides регулярно обновляется для поддержки последних версий .NET. Проверьте [документация](https://reference.aspose.com/slides/net/) для получения подробной информации о совместимости.
### Могу ли я попробовать Aspose.Slides перед покупкой?
Конечно! Вы можете скачать бесплатную пробную версию [здесь](https://releases.aspose.com/).
### Где я могу найти поддержку по вопросам, связанным с Aspose.Slides?
Посетите Aspose.Slides [форум](https://forum.aspose.com/c/slides/11) для поддержки сообщества и обсуждений.
### Как получить временную лицензию для Aspose.Slides?
Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу приобрести полную лицензию на Aspose.Slides?
Вы можете купить лицензию у [страница покупки](https://purchase.aspose.com/buy).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}