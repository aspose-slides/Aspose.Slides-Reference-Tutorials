---
"description": "Конвертируйте презентации PowerPoint в HTML, сохраняя оригинальные шрифты, с помощью Aspose.Slides для Java."
"linktitle": "Преобразование презентации в HTML с сохранением оригинальных шрифтов в Java Slides"
"second_title": "API обработки Java PowerPoint Aspose.Slides"
"title": "Преобразование презентации в HTML с сохранением оригинальных шрифтов в Java Slides"
"url": "/ru/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Преобразование презентации в HTML с сохранением оригинальных шрифтов в Java Slides


## Введение в преобразование презентации в HTML с сохранением исходных шрифтов в Java Slides

В этом уроке мы рассмотрим, как преобразовать презентацию PowerPoint (PPTX) в HTML, сохранив исходные шрифты с помощью Aspose.Slides for Java. Это гарантирует, что полученный HTML будет максимально похож на внешний вид исходной презентации.

## Шаг 1: Настройка проекта
Прежде чем погрузиться в код, давайте убедимся, что у вас выполнены все необходимые настройки:

1. Загрузите Aspose.Slides для Java: если вы еще этого не сделали, загрузите и включите библиотеку Aspose.Slides для Java в свой проект.

2. Создайте проект Java: настройте проект Java в своей любимой среде IDE и убедитесь, что у вас есть папка «lib», в которую вы можете поместить JAR-файл Aspose.Slides.

3. Импорт необходимых классов: Импортируйте необходимые классы в начало вашего файла Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Шаг 2: Преобразование презентации в HTML с оригинальными шрифтами

Теперь давайте преобразуем презентацию PowerPoint в HTML, сохранив исходные шрифты:

```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";

// Загрузить презентацию
Presentation pres = new Presentation("input.pptx");

try {
    // Исключить шрифты презентации по умолчанию, такие как Calibri и Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Создайте параметры HTML и установите пользовательский форматировщик HTML
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Сохранить презентацию как HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Утилизировать презентационный объект
    if (pres != null) pres.dispose();
}
```

В этом фрагменте кода:

- Мы загружаем входную презентацию PowerPoint с помощью `Presentation`.

- Мы определяем список шрифтов (`fontNameExcludeList`), которые мы хотим исключить из встраивания в HTML. Это полезно для исключения распространенных шрифтов, таких как Calibri и Arial, чтобы уменьшить размер файла.

- Мы создаем экземпляр `EmbedAllFontsHtmlController` и передайте ему список исключенных шрифтов.

- Мы создаем `HtmlOptions` и установите пользовательский форматировщик HTML с помощью `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Наконец, мы сохраняем презентацию как HTML с указанными параметрами.

## Полный исходный код для преобразования презентации в HTML с сохранением оригинальных шрифтов в Java Slides

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

В этом уроке вы узнали, как преобразовать презентацию PowerPoint в HTML, сохранив исходные шрифты с помощью Aspose.Slides for Java. Это полезно, когда вы хотите сохранить визуальную точность ваших презентаций при их публикации в Интернете.

## Часто задаваемые вопросы

### Как загрузить Aspose.Slides для Java?

Вы можете загрузить Aspose.Slides для Java с веб-сайта Aspose. Посетите [здесь](https://downloads.aspose.com/slides/java/) чтобы получить последнюю версию.

### Могу ли я настроить список исключенных шрифтов?

Да, вы можете настроить `fontNameExcludeList` массив для включения или исключения определенных шрифтов в соответствии с вашими требованиями.

### Работает ли этот метод для старых форматов PowerPoint, таких как PPT?

Этот пример кода предназначен для файлов PPTX. Если вам нужно преобразовать старые файлы PPT, вам может потребоваться внести изменения в код.

### Как можно дополнительно настроить вывод HTML?

Вы можете исследовать `HtmlOptions` класс для настройки различных аспектов вывода HTML, таких как размер слайда, качество изображения и многое другое.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}