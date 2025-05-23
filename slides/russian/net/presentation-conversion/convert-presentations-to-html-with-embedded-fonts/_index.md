---
"description": "Конвертируйте презентации PowerPoint в HTML со встроенными шрифтами с помощью Aspose.Slides для .NET. Сохраняйте оригинальность без проблем."
"linktitle": "Конвертируйте презентации в HTML со встроенными шрифтами"
"second_title": "API обработки PowerPoint Aspose.Slides .NET"
"title": "Конвертируйте презентации в HTML со встроенными шрифтами"
"url": "/ru/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Конвертируйте презентации в HTML со встроенными шрифтами


В сегодняшнюю цифровую эпоху обмен презентациями и документами в Интернете стал обычной практикой. Однако часто возникает одна проблема — обеспечение корректного отображения шрифтов при конвертации презентаций в HTML. Это пошаговое руководство проведет вас через процесс использования Aspose.Slides для .NET для конвертации презентаций в HTML со встроенными шрифтами, гарантируя, что ваши документы будут выглядеть именно так, как вы задумали.

## Введение в Aspose.Slides для .NET

Прежде чем погрузиться в учебник, давайте кратко рассмотрим Aspose.Slides для .NET. Это мощная библиотека, которая позволяет разработчикам работать с презентациями PowerPoint в приложениях .NET. С Aspose.Slides вы можете программно создавать, изменять и конвертировать файлы PowerPoint.

## Предпосылки

Прежде чем начать, убедитесь, что у вас выполнены следующие предварительные условия:

- Aspose.Slides для .NET: В вашем проекте должна быть установлена библиотека Aspose.Slides. Вы можете загрузить ее с [здесь](https://releases.aspose.com/slides/net/).

## Шаг 1: Настройте свой проект

1. Создайте новый проект или откройте существующий в предпочитаемой вами среде разработки .NET.

2. Добавьте ссылку на библиотеку Aspose.Slides в свой проект.

3. Импортируйте необходимые пространства имен в свой код:

   ```csharp
   using Aspose.Slides;
   ```

## Шаг 2: Загрузите презентацию

Для начала вам нужно загрузить презентацию, которую вы хотите преобразовать в HTML. Заменить `"Your Document Directory"` на фактический каталог, где находится файл вашей презентации.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // Ваш код будет здесь
}
```

## Шаг 3: Исключите шрифты презентации по умолчанию

На этом этапе вы можете указать любые шрифты презентации по умолчанию, которые вы хотите исключить из встраивания. Это может помочь оптимизировать размер итогового HTML-файла.

```csharp
string[] fontNameExcludeList = { };
```

## Шаг 4: Выберите HTML-контроллер

Теперь у вас есть два варианта встраивания шрифтов в HTML:

### Вариант 1: Встроить все шрифты

Чтобы встроить все шрифты, используемые в презентации, используйте `EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### Вариант 2: Связать все шрифты

Чтобы сделать ссылку на все шрифты, использованные в презентации, используйте ссылку `LinkAllFontsHtmlController`Вам следует указать каталог, в котором в вашей системе находятся шрифты.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## Шаг 5: Определите параметры HTML

Создайте `HtmlOptions` объект и установите HTML-форматер на тот, который вы выбрали на предыдущем шаге.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Используйте embedFontsController для встраивания всех шрифтов
};
```

## Шаг 6: Сохранить как HTML

Наконец, сохраните презентацию как HTML-файл. Вы можете выбрать либо `SaveFилиmat.Html` or `SaveFormat.Html5` в зависимости от Ваших требований.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Заключение

Поздравляем! Вы успешно преобразовали свою презентацию в HTML со встроенными шрифтами с помощью Aspose.Slides for .NET. Это гарантирует, что ваши шрифты будут отображаться правильно при публикации ваших презентаций в Интернете.

Теперь вы можете с легкостью и уверенностью делиться своими прекрасно отформатированными презентациями, зная, что ваша аудитория увидит их именно такими, какими вы их задумали.

Для получения дополнительной информации и подробных ссылок на API посетите [Документация Aspose.Slides для .NET](https://reference.aspose.com/slides/net/).

## Часто задаваемые вопросы

### 1. Можно ли конвертировать презентации PowerPoint в HTML с помощью Aspose.Slides для .NET в пакетном режиме?

Да, вы можете выполнить пакетное преобразование нескольких презентаций в HTML с помощью Aspose.Slides для .NET, пройдясь по файлам презентации и применив процесс преобразования к каждому из них.

### 2. Есть ли способ настроить внешний вид HTML-вывода?

Конечно! Aspose.Slides для .NET предоставляет различные возможности для настройки внешнего вида и форматирования выходных данных HTML, такие как настройка цветов, шрифтов и макета.

### 3. Существуют ли какие-либо ограничения на встраивание шрифтов в HTML с помощью Aspose.Slides для .NET?

Хотя Aspose.Slides для .NET предлагает отличные возможности внедрения шрифтов, имейте в виду, что размер ваших HTML-файлов может увеличиться при внедрении шрифтов. Обязательно оптимизируйте выбор шрифтов для использования в Интернете.

### 4. Можно ли конвертировать презентации PowerPoint в другие форматы с помощью Aspose.Slides для .NET?

Да, Aspose.Slides for .NET поддерживает широкий спектр выходных форматов, включая PDF, изображения и т. д. Вы можете легко конвертировать свои презентации в формат по вашему выбору.

### 5. Где я могу найти дополнительные ресурсы и поддержку для Aspose.Slides для .NET?

Вы можете получить доступ к множеству ресурсов, включая документацию, на сайте [Справочник API Aspose.Slides для .NET](https://reference.aspose.com/slides/net/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}