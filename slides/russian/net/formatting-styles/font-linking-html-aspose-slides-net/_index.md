---
"date": "2025-04-15"
"description": "Узнайте, как обеспечить единообразную визуализацию шрифтов при конвертации презентаций в HTML с помощью Aspose.Slides для .NET путем непосредственного внедрения шрифтов."
"title": "Как связать шрифты в HTML с помощью Aspose.Slides для .NET&#58; Пошаговое руководство"
"url": "/ru/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как связать шрифты в HTML с помощью Aspose.Slides для .NET

## Введение

Преобразование презентаций в HTML с сохранением единообразия отображения шрифтов на разных платформах может оказаться непростой задачей. **Aspose.Slides для .NET** предлагает комплексное решение, позволяя вам связывать все шрифты, используемые в презентации, непосредственно в выходном HTML-файле с помощью встроенных файлов шрифтов.

В этом уроке мы рассмотрим, как реализовать привязку шрифтов с помощью Aspose.Slides для .NET и обеспечить единообразие дизайна на разных платформах. 

**Что вы узнаете:**
- Настройка вашей среды с помощью Aspose.Slides для .NET
- Связывание шрифтов при конвертации HTML
- Написание пользовательских контроллеров для встраивания шрифтов
- Практические применения и соображения производительности

Давайте рассмотрим шаги, необходимые для достижения этой цели.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

### Необходимые библиотеки и зависимости
- **Aspose.Slides для .NET** библиотека: Основной компонент нашей реализации.

### Требования к настройке среды
- Среда разработки с установленным .NET Framework или .NET Core.

### Необходимые знания
- Базовые знания программирования на C#.
- Знакомство с HTML и CSS, особенно `@font-face` правило.

## Настройка Aspose.Slides для .NET

Чтобы использовать Aspose.Slides в вашем проекте .NET, вам необходимо установить библиотеку. Вот несколько методов:

### Использование .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Использование консоли диспетчера пакетов
```powershell
Install-Package Aspose.Slides
```

### Через пользовательский интерфейс диспетчера пакетов NuGet
- Откройте свой проект в Visual Studio.
- Перейдите в «Менеджер пакетов NuGet».
- Найдите «Aspose.Slides» и установите последнюю версию.

### Этапы получения лицензии
Вы можете получить бесплатную пробную лицензию для тестирования всех функций без ограничений, выполнив следующие действия:
1. **Бесплатная пробная версия**: Загрузить временную лицензию [здесь](https://releases.aspose.com/slides/net/).
2. **Временная лицензия**: Подать заявку на расширенный доступ [здесь](https://purchase.aspose.com/temporary-license/).
3. **Покупка**: Для полной функциональности приобретите лицензию [здесь](https://purchase.aspose.com/buy).

### Базовая инициализация и настройка
```csharp
// Создать экземпляр класса License
easpose.slides.License license = new aspose.slides.License();

// Применить лицензию из пути к файлу
license.SetLicense("Aspose.Slides.lic");
```

## Руководство по внедрению

Теперь давайте реализуем привязку шрифтов в HTML-конвертации, используя **Aspose.Slides для .NET**.

### Обзор функций: Связывание шрифтов при конвертации HTML
Эта функция гарантирует, что все шрифты, используемые в презентации, напрямую связаны в конечном HTML-файле путем встраивания файлов шрифтов. Этот метод обеспечивает надежное решение для поддержания согласованности дизайна в различных браузерах и на различных платформах.

#### Шаг 1: Создание пользовательского контроллера
Создайте собственный класс контроллера `LinkAllFontsHtmlController` который наследует от `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Укажите каталог, в котором будут храниться файлы шрифтов.
    }
}
```
#### Шаг 2: Реализация метода написания шрифта
The `WriteFont` Метод записывает данные шрифта в файл и генерирует соответствующий HTML-код для встраивания:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Определите название используемого шрифта, отдавая предпочтение замещающим шрифтам, если они доступны.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Создайте путь к файлу шрифта .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Записать данные шрифта в указанный путь к файлу.
    File.WriteAllBytes(path, fontData);

    // Сгенерируйте блок стиля HTML, встраивая шрифт, используя правило @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}