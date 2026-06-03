---
date: '2026-06-03'
description: Узнайте, как экспортировать диаграмму в Excel и создавать диаграммы Java
  с использованием Aspose.Slides for Java. Овладейте визуализацией данных, слайдами
  бизнес‑отчетов и генерацией рабочих книг.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Экспортировать диаграмму в Excel и создавать диаграммы с Aspose.Slides
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Экспорт диаграммы в Excel и создание диаграмм с помощью Aspose.Slides

**Освойте техники визуализации данных с Aspose.Slides для Java**

В современном мире, управляемом данными, программный *export chart to excel* — это навык, который может превратить сырые цифры в убедительные визуальные истории. Независимо от того, создаёте ли вы набор слайдов бизнес‑отчёта или интерактивную аналитическую панель, Aspose.Slides для Java предоставляет возможность генерировать, настраивать и экспортировать диаграммы непосредственно из кода. В этом руководстве вы узнаете, как создавать объекты диаграмм, экспортировать данные диаграмм в Excel и связывать диаграммы с внешними рабочими книгами для бесшовного управления данными.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides for Java (v25.4+).  
- **Могу ли я экспортировать данные диаграммы в Excel?** Да — используйте `readWorkbookStream()` и запишите байты в файл *.xlsx*.  
- **Какая версия Java требуется?** JDK 16 или выше.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; постоянная лицензия требуется для продакшн.  
- **Какой тип диаграммы демонстрируется?** Круговая диаграмма, но тот же подход работает для столбчатых, линейных и других типов диаграмм.

## Что такое Aspose.Slides для Java?
Aspose.Slides for Java — это чисто Java API, позволяющий разработчикам создавать, редактировать и конвертировать презентации PowerPoint без Microsoft Office. Он предоставляет обширный набор классов для работы со слайдами, создания диаграмм и конвертации форматов, что позволяет автоматизировать решения по отчётности. Он поддерживает **более 50 типов диаграмм**, полное привязывание данных и прямой экспорт в Excel, что делает его идеальным для проектов **data visualization java**.

## Почему стоит использовать Aspose.Slides для создания диаграмм и экспорта их в Excel?
Экспорт диаграммы в Excel быстро и надёжно. Aspose.Slides устраняет необходимость установки Office, предлагает **более 50 встроенных стилей диаграмм**, и обрабатывает презентации **до 300 МБ менее чем за 30 секунд** на стандартном серверном оборудовании. Вы также получаете нативную генерацию Excel‑рабочих книг, что позволяет аналитикам работать с сырыми цифрами без ручного копирования‑вставки.

## Предварительные требования
Прежде чем мы начнём, убедитесь, что у вас есть следующее:

### Требуемые библиотеки и версии
- **Aspose.Slides for Java** версия 25.4 или новее (поддерживает JDK 16+)

### Требования к настройке окружения
- Java Development Kit (JDK) 16 или выше  
- IDE, например IntelliJ IDEA или Eclipse (или любой предпочитаемый текстовый редактор)

### Требования к знаниям
- Базовые навыки программирования на Java  
- Знакомство с системами сборки Maven или Gradle

## Настройка Aspose.Slides для Java
Добавьте библиотеку в ваш проект, используя предпочитаемую систему сборки.

**Maven**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

В качестве альтернативы вы можете [скачать последнюю версию напрямую](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
Aspose.Slides предлагает бесплатную пробную лицензию для изучения всех возможностей. Вы также можете запросить временную лицензию или приобрести её для длительного использования. Следуйте этим шагам:

1. Посетите страницу [Aspose Purchase](https://purchase.aspose.com/buy), чтобы получить лицензию.  
2. Для бесплатной пробной версии скачайте с [Releases](https://releases.aspose.com/slides/java/).  
3. Подайте заявку на временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

После получения файла лицензии инициализируйте её в вашем Java‑приложении:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Пошаговое руководство

### Как создать диаграмму – загрузить презентацию
Загрузите существующий файл PowerPoint перед тем, как добавить или изменить диаграммы.  
Класс `Presentation` представляет файл PowerPoint в памяти, предоставляя доступ к слайдам, фигурам и объектам диаграмм.  
Загрузите файл с помощью `new Presentation("input.pptx")`, затем работайте с первым слайдом через `presentation.getSlides().get_Item(0)`. Всегда вызывайте `presentation.dispose()` в блоке `finally`, чтобы освободить нативные ресурсы.

### Как создать диаграмму – добавить круговую диаграмму на слайд
Вставьте круговую диаграмму, идеальную для отображения пропорциональных данных.  
Интерфейс `IChart` является основной точкой входа для работы с диаграммами; метод `addChart` создаёт новую диаграмму на целевом слайде. Укажите тип диаграммы (`ChartType.Pie`), координаты X/Y и ширину/высоту. После создания вы можете настроить заголовки, легенду и серии данных через объект `ChartData`.

### Как экспортировать диаграмму в Excel – экспорт данных диаграммы
Экспорт данных диаграммы позволяет аналитикам работать с цифрами в Excel, обеспечивая более глубокие инсайты.  
`readWorkbookStream()` возвращает подлежащую Excel‑рабочую книгу диаграммы в виде массива байтов. Вызовите `chart.getChartData().readWorkbookStream()`, чтобы получить рабочую книгу, и запишите этот массив в файл `externalWorkbook1.xlsx` с помощью стандартного Java I/O. Полученный файл Excel содержит точные данные, использованные в диаграмме, и готов к дальнейшему анализу.

### Как создать диаграмму – установить внешнюю рабочую книгу для динамических данных
Свяжите диаграмму с внешней рабочей книгой, чтобы обеспечить обновление данных в реальном времени без пересоздания слайда.  
`setExternalWorkbook()` привязывает диаграмму к внешнему файлу Excel для динамических обновлений данных. Используйте `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")`, чтобы привязать диаграмму к внешнему файлу. При изменении Excel‑книги диаграмма автоматически отразит изменения при следующем открытии презентации, поддерживая сценарии динамической отчётности.

## Практические применения
Aspose.Slides предлагает универсальные решения для различных реальных сценариев:

1. **Слайды бизнес‑отчётов:** Автоматически генерировать квартальные диаграммы производительности из ваших конвейеров данных.  
2. **Академические презентации:** Превращать исследовательские данные в чёткие визуализации без ручного построения диаграмм.  
3. **Финансовый анализ:** Экспортировать данные диаграммы в Excel для аудита, позволяя проверять цифры и снижать ручные ошибки.  
4. **Маркетинговая аналитика:** Визуализировать метрики кампаний и делиться редактируемыми рабочими книгами со стейкхолдерами для совместного принятия решений.  
5. **Автоматическое создание панелей управления:** Сочетать API создания диаграмм с запланированными задачами для генерации актуальных наборов слайдов каждое утро.

## Распространённые проблемы и устранение неполадок
- **`FileNotFoundException`** – Убедитесь, что `dataDir` указывает на существующую папку и путь вывода доступен для записи.  
- **Утечки памяти** – Всегда вызывайте `presentation.dispose()` в блоке `finally`, чтобы освободить нативные ресурсы.  
- **Диаграмма не отображается** – Убедитесь, что индекс слайда (`get_Item(0)`) соответствует существующему слайду и что размеры диаграммы находятся в пределах границ слайда.  
- **Экспорт в Excel создаёт пустой файл** – Убедитесь, что диаграмма действительно содержит серии данных перед вызовом `readWorkbookStream()`.

## Часто задаваемые вопросы

**В: Могу ли я использовать другой тип диаграммы (например, столбчатую, линейную) с тем же кодом?**  
О: Да. Замените `ChartType.Pie` на любое другое значение перечисления `ChartType`, например `ChartType.Bar` или `ChartType.Line`.

**В: Можно ли обновить внешнюю рабочую книгу после создания диаграммы?**  
О: Абсолютно. Измените файл Excel напрямую; связанная диаграмма отразит изменения при следующем открытии презентации.

**В: Нужна ли отдельная лицензия для функции экспорта в Excel?**  
О: Нет. Возможность экспорта в Excel включена в стандартную лицензию Aspose.Slides для Java.

**В: Какие версии Java поддерживаются?**  
О: Aspose.Slides для Java поддерживает JDK 16 и новее; более ранние версии могут работать, но официально не тестируются.

**В: Как встроить сгенерированную рабочую книгу Excel в файл PPTX?**  
О: Используйте `chart.getChartData().setExternalWorkbook(null)`, чтобы встроить рабочую книгу, либо оставьте внешнюю ссылку для динамических обновлений.

---

**Последнее обновление:** 2026-06-03  
**Тестировано с:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Автор:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Создать диаграмму в Java с Aspose.Slides – добавление и проверка диаграмм](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Восстановить данные рабочей книги из диаграмм PowerPoint с помощью Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Как обновить диапазон данных диаграммы PowerPoint с помощью Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}