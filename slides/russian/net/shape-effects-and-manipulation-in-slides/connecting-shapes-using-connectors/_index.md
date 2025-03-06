---
title: Aspose.Slides — плавное соединение фигур в .NET
linktitle: Соединение фигур с помощью соединителей в презентации
second_title: Aspose.Slides .NET API обработки PowerPoint
description: Исследуйте возможности Aspose.Slides для .NET, легко соединяя фигуры в своих презентациях. Улучшите свои слайды с помощью динамических соединителей.
weight: 29
url: /ru/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — плавное соединение фигур в .NET

## Введение
В динамичном мире презентаций возможность соединять фигуры с помощью соединителей придает слайдам изысканность. Aspose.Slides для .NET позволяет разработчикам легко добиться этого. Это руководство проведет вас через весь процесс, разбив каждый шаг, чтобы обеспечить четкое понимание.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующее:
- Базовые знания C# и .NET framework.
-  Установлен Aspose.Slides для .NET. Если нет, скачайте его[здесь](https://releases.aspose.com/slides/net/).
- Создана среда разработки.
## Импортировать пространства имен
В своем коде C# начните с импорта необходимых пространств имен:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Настройте каталог документов.
Начните с определения каталога для вашего документа:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Создать экземпляр класса представления
Создайте экземпляр класса Presentation для представления вашего файла PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Доступ к коллекции фигур для выбранного слайда
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Добавьте фигуры на слайд
Добавьте на слайд необходимые фигуры, например эллипс и прямоугольник:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Добавьте форму соединителя
Включите фигуру соединителя в коллекцию фигур слайда:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Соедините фигуры с помощью соединителя
Укажите фигуры, которые необходимо соединить соединителем:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Соединитель перенаправления
Вызовите метод reroute, чтобы установить автоматический кратчайший путь между фигурами:
```csharp
connector.Reroute();
```
## 7. Сохранить презентацию
Сохраните презентацию, чтобы просмотреть связанные фигуры:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Заключение
Поздравляем! Вы успешно соединили фигуры с помощью соединителей в слайдах презентации с помощью Aspose.Slides для .NET. Улучшите свои презентации с помощью этой расширенной функции и увлеките свою аудиторию.
## Часто задаваемые вопросы
### Совместим ли Aspose.Slides для .NET с последней версией .NET Framework?
Да, Aspose.Slides для .NET регулярно обновляется, чтобы обеспечить совместимость с последними версиями .NET framework.
### Могу ли я соединить более двух фигур с помощью одного соединителя?
Конечно, вы можете соединить несколько фигур, расширив логику соединителя в своем коде.
### Есть ли какие-либо ограничения на фигуры, которые я могу соединить?
Aspose.Slides для .NET поддерживает соединение различных фигур, включая базовые фигуры, интеллектуальные рисунки и пользовательские фигуры.
### Как настроить внешний вид разъема?
Изучите документацию Aspose.Slides, чтобы узнать о методах настройки внешнего вида соединителя, таких как стиль и цвет линий.
### Есть ли форум сообщества для поддержки Aspose.Slides?
 Да, вы можете найти помощь и поделиться своим опытом в[Форум Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
