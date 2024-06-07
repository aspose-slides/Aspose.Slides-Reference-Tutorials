---
title: Преобразование презентации в HTML с сохранением оригинальных шрифтов в слайдах Java
linktitle: Преобразование презентации в HTML с сохранением оригинальных шрифтов в слайдах Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Преобразуйте презентации PowerPoint в HTML, сохраняя оригинальные шрифты с помощью Aspose.Slides для Java.
type: docs
weight: 14
url: /ru/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Введение в преобразование презентации в HTML с сохранением оригинальных шрифтов в слайдах Java

В этом уроке мы рассмотрим, как преобразовать презентацию PowerPoint (PPTX) в HTML, сохранив исходные шрифты с помощью Aspose.Slides для Java. Это гарантирует, что полученный HTML-код будет очень похож на внешний вид исходной презентации.

## Шаг 1: Настройка проекта
Прежде чем мы углубимся в код, давайте убедимся, что у вас есть необходимые настройки:

1. Загрузите Aspose.Slides для Java. Если вы еще этого не сделали, загрузите и включите библиотеку Aspose.Slides для Java в свой проект.

2. Создайте проект Java. Настройте проект Java в своей любимой IDE и убедитесь, что у вас есть папка «lib», в которую можно поместить JAR-файл Aspose.Slides.

3. Импортируйте необходимые классы: импортируйте необходимые классы в начало вашего Java-файла:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Шаг 2. Преобразование презентации в HTML с использованием оригинальных шрифтов

Теперь давайте преобразуем презентацию PowerPoint в HTML, сохранив исходные шрифты:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Загрузите презентацию
Presentation pres = new Presentation("input.pptx");

try {
    //Исключить шрифты презентации по умолчанию, такие как Calibri и Arial.
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Создайте параметры HTML и установите собственный форматировщик HTML.
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Сохраните презентацию в формате HTML.
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Удалить объект презентации
    if (pres != null) pres.dispose();
}
```

В этом фрагменте кода:

-  Мы загружаем входную презентацию PowerPoint, используя`Presentation`.

- Определяем список шрифтов (`fontNameExcludeList`), который мы хотим исключить из встраивания в HTML. Это полезно для исключения распространенных шрифтов, таких как Calibri и Arial, для уменьшения размера файла.

-  Мы создаем экземпляр`EmbedAllFontsHtmlController` и передайте ему список исключений шрифтов.

-  Мы создаем`HtmlOptions` и установите собственный форматировщик HTML, используя`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Наконец, мы сохраняем презентацию в формате HTML с указанными параметрами.

## Полный исходный код для преобразования презентации в HTML с сохранением оригинальных шрифтов в слайдах Java

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// исключить шрифты презентации по умолчанию
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Заключение

В этом уроке вы узнали, как преобразовать презентацию PowerPoint в HTML, сохранив исходные шрифты, с помощью Aspose.Slides для Java. Это полезно, если вы хотите сохранить визуальное качество презентаций при публикации их в Интернете.

## Часто задаваемые вопросы

### Как загрузить Aspose.Slides для Java?

Вы можете скачать Aspose.Slides для Java с веб-сайта Aspose. Посещать[здесь](https://downloads.aspose.com/slides/java/) чтобы получить последнюю версию.

### Могу ли я настроить список исключенных шрифтов?

 Да, вы можете настроить`fontNameExcludeList` массив для включения или исключения определенных шрифтов в соответствии с вашими требованиями.

### Работает ли этот метод для старых форматов PowerPoint, таких как PPT?

Этот пример кода предназначен для файлов PPTX. Если вам нужно конвертировать старые файлы PPT, возможно, вам придется внести изменения в код.

### Как я могу дополнительно настроить вывод HTML?

 Вы можете изучить`HtmlOptions` класс для настройки различных аспектов вывода HTML, таких как размер слайда, качество изображения и т. д.