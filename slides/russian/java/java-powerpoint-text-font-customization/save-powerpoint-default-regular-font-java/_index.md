---
title: Сохраните PowerPoint с обычным шрифтом по умолчанию, используя Java
linktitle: Сохраните PowerPoint с обычным шрифтом по умолчанию, используя Java
second_title: Aspose.Slides API обработки Java PowerPoint
description: Узнайте, как программно управлять презентациями PowerPoint с помощью Aspose.Slides для Java. Освойте работу с Java PowerPoint с помощью пошаговых руководств.
type: docs
weight: 12
url: /ru/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## Введение
В области разработки Java программное создание презентаций PowerPoint и управление ими может значительно повысить производительность и расширить возможности настройки. Aspose.Slides для Java — это надежная библиотека, которая позволяет разработчикам эффективно обрабатывать файлы PowerPoint, предлагая полный набор функций: от простых модификаций до сложных презентаций.
## Предварительные условия
Прежде чем приступить к использованию Aspose.Slides для Java, убедитесь, что у вас настроены следующие предварительные условия:
1. Комплект разработки Java (JDK): для правильной работы Aspose.Slides for Java требуется JDK 1.8 или выше.
2. Aspose.Slides for Java JAR: загрузите последнюю версию Aspose.Slides for Java с сайта[здесь](https://releases.aspose.com/slides/java/).
3. Интегрированная среда разработки (IDE): используйте IntelliJ IDEA, Eclipse или другую Java IDE по вашему выбору.
4. Базовое понимание Java: необходимо знание основ языка программирования Java.

## Импортировать пакеты
Чтобы начать использовать Aspose.Slides для Java, импортируйте необходимые пакеты:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Это гарантирует, что у вас будет доступ ко всем классам и методам, предоставляемым Aspose.Slides для Java.
## Шаг 1. Настройте свой проект
Сначала создайте новый проект Java в своей IDE и включите JAR-файл Aspose.Slides for Java в путь сборки вашего проекта.
## Шаг 2. Инициализация объекта презентации
 Создать экземпляр`Presentation` объект, загрузив существующий файл PowerPoint (.pptx) из локального каталога.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Загрузить презентацию
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Заменять`"Your Document Directory"` и`"Your Output Directory"` с вашими фактическими путями к файлам.
## Шаг 3. Сохраните презентацию с обычными шрифтами по умолчанию
 Укажите обычный шрифт по умолчанию для выходных форматов (HTML и PDF), используя`HtmlOptions` и`PdfOptions` соответственно.
```java
try {
    // Параметры сохранения HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Параметры сохранения PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Обязательно замените`"Arial Black"` и`"Lucida Console"` с желаемыми обычными шрифтами по умолчанию.

## Заключение
Выполнив эти шаги, вы научились эффективно манипулировать презентациями PowerPoint с помощью Aspose.Slides для Java. Эта возможность позволяет автоматизировать задачи, настраивать презентации и расширять возможности Java-приложений с помощью расширенных функций обработки PowerPoint.
## Часто задаваемые вопросы
### Может ли Aspose.Slides для Java работать со старыми версиями JDK?
Для совместимости Aspose.Slides для Java требуется JDK 1.8 или выше.
### Как я могу получить временную лицензию на Aspose.Slides для Java?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Где я могу найти более подробную документацию по Aspose.Slides для Java?
 Изучите полную документацию[здесь](https://reference.aspose.com/slides/java/).
### Доступна ли поддержка сообщества для Aspose.Slides для Java?
 Да, вы можете получить поддержку сообщества[здесь](https://forum.aspose.com/c/slides/11).
### Могу ли я попробовать Aspose.Slides для Java бесплатно?
 Да, скачайте бесплатную пробную версию[здесь](https://releases.aspose.com/).