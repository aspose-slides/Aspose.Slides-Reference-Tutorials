---
date: '2026-02-09'
description: Узнайте, как создавать диаграммы и экспортировать их в Excel с помощью
  Aspose.Slides for Java. Освойте визуализацию данных, слайды бизнес‑отчетов и генерацию
  рабочих книг.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Как создать диаграмму с помощью Aspose.Slides Java
url: /ru/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Как создать диаграмму с помощью Aspose.Slides for Java

**Освойте техники визуализации данных с Aspose.Slides for Java**

В современном мире, ориентированном на данные, программно *как создать диаграмму* — это навык, который может превратить сырые цифры в убедительные визуальные истории. Независимо от того, создаёте ли вы набор слайдов бизнес‑отчёта или интерактивную аналитическую панель, Aspose.Slides for Java предоставляет возможность генерировать, настраивать и экспортировать диаграммы непосредственно из кода. В этом руководстве вы узнаете, как создавать объекты диаграмм, экспортировать данные диаграммы в Excel и связывать диаграммы с внешними рабочими книгами для бесшовного управления данными.

## Быстрые ответы
- **Какая библиотека нужна?** Aspose.Slides for Java (v25.4+).  
- **Можно ли экспортировать данные диаграммы в Excel?** Да — используйте `readWorkbookStream()` и запишите байты в файл *.xlsx*.  
- **Какая версия Java требуется?** JDK 16 или выше.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для оценки; постоянная лицензия требуется для продакшн.  
- **Какой тип диаграммы демонстрируется?** Круговая диаграмма, но тот же подход работает для столбчатых, линейных и других типов диаграмм.

## Что такое Aspose.Slides for Java?
Aspose.Slides for Java — это чисто Java API, позволяющий разработчикам создавать, редактировать и конвертировать презентации PowerPoint без Microsoft Office. Он поддерживает полный набор типов диаграмм, привязку данных и возможности экспорта, что делает его идеальным для проектов **data visualization java**.

## Почему стоит использовать Aspose.Slides для создания диаграмм и их экспорта в Excel?
- **Без установки Office** — работает на любом сервере или в облачной среде.  
- **Богатая библиотека диаграмм** — десятки типов диаграмм и полный контроль над стилем.  
- **Прямой экспорт в Excel** — генерирует внешнюю рабочую книгу для последующего анализа.  
- **Ориентировано на производительность** — низкое потребление памяти и быстрая обработка больших наборов слайдов.

## Предварительные требования
Прежде чем погрузиться в детали, убедитесь, что у вас есть следующее:

### Требуемые библиотеки и версии
- **Aspose.Slides for Java** версия 25.4 или новее

### Требования к настройке окружения
- Java Development Kit (JDK) 16 или новее  
- IDE, например IntelliJ IDEA или Eclipse (или любой предпочитаемый текстовый редактор)

### Требования к знаниям
- Базовые навыки программирования на Java  
- Знакомство с системами сборки Maven или Gradle

## Настройка Aspose.Slides for Java
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

Кроме того, вы можете [скачать последнюю версию напрямую](https://releases.aspose.com/slides/java/).

### Шаги получения лицензии
Aspose.Slides предлагает бесплатную пробную лицензию для ознакомления со всеми возможностями. Вы также можете запросить временную лицензию или приобрести её для длительного использования. Следуйте этим шагам:

1. Перейдите на страницу [Aspose Purchase page](https://purchase.aspose.com/buy), чтобы получить лицензию.  
2. Для бесплатной пробной версии скачайте с [Releases](https://releases.aspose.com/slides/java/).  
3. Запросите временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

После получения файла лицензии инициализируйте его в вашем Java‑приложении:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Пошаговое руководство

### Как создать диаграмму – загрузка презентации
Загрузка существующего файла PowerPoint — первый шаг перед тем, как добавить или изменить диаграммы.

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

**Объяснение:**  
- `Presentation` представляет файл PowerPoint.  
- Всегда вызывайте `dispose()`, чтобы освободить нативные ресурсы.

### Как создать диаграмму – добавить круговую диаграмму на слайд
Теперь мы вставим круговую диаграмму, которая идеально подходит для отображения пропорциональных данных.

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

**Объяснение:**  
- `addChart` вставляет диаграмму на первый слайд.  
- Параметры определяют тип диаграммы, позицию X/Y и размер.

### Как экспортировать диаграмму в Excel – экспорт данных диаграммы
Экспорт данных диаграммы позволяет аналитикам работать с числами в Excel, получая более глубокие инсайты.

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

**Объяснение:**  
- `readWorkbookStream()` извлекает базовую Excel‑рабочую книгу диаграммы в виде массива байтов.  
- Массив байтов записывается в `externalWorkbook1.xlsx`, предоставляя готовый к использованию файл Excel.

### Как создать диаграмму – установить внешнюю рабочую книгу для динамических данных
Привязка диаграммы к внешней рабочей книге позволяет обновлять диаграмму простым редактированием файла Excel.

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

**Объяснение:**  
- `setExternalWorkbook` связывает диаграмму с указанным файлом Excel, позволяя обновлять данные в реальном времени без пересборки слайда.

## Практические применения
Aspose.Slides предлагает универсальные решения для различных реальных сценариев:

1. **Слайды бизнес‑отчётов:** Автоматически генерировать квартальные диаграммы производительности из ваших конвейеров данных.  
2. **Академические презентации:** Превращать исследовательские данные в чёткие визуализации без ручного построения диаграмм.  
3. **Финансовый анализ:** Экспортировать данные диаграмм в Excel для проверки аудиторами.  
4. **Маркетинговая аналитика:** Визуализировать метрики кампаний и делиться редактируемыми рабочими книгами со стейкхолдерами.

## Распространённые проблемы и устранение неполадок
- **`FileNotFoundException`** — Убедитесь, что `dataDir` указывает на существующую папку и путь вывода доступен для записи.  
- **Утечки памяти** — Всегда вызывайте `pres.dispose()` в блоке `finally`, чтобы освободить нативные ресурсы.  
- **Диаграмма не отображается** — Убедитесь, что индекс слайда (`get_Item(0)`) соответствует существующему слайду.

## Часто задаваемые вопросы

**Q: Могу ли я использовать другой тип диаграммы (например, Bar, Line) с тем же кодом?**  
A: Да. Замените `ChartType.Pie` на любое другое значение перечисления `ChartType`, например `ChartType.Bar` или `ChartType.Line`.

**Q: Можно ли обновить внешнюю рабочую книгу после создания диаграммы?**  
A: Конечно. Измените файл Excel напрямую; связанная диаграмма отразит изменения при следующем открытии презентации.

**Q: Нужна ли отдельная лицензия для функции экспорта в Excel?**  
A: Нет. Возможность экспорта в Excel включена в стандартную лицензию Aspose.Slides for Java.

**Q: Какие версии Java поддерживаются?**  
A: Aspose.Slides for Java поддерживает JDK 16 и новее; более ранние версии могут работать, но официально не тестируются.

**Q: Как встроить сгенерированную рабочую книгу Excel внутрь файла PPTX?**  
A: Используйте `chart.getChartData().setExternalWorkbook(null)`, чтобы встроить книгу, либо оставьте внешнюю ссылку для динамических обновлений.

---

**Последнее обновление:** 2026-02-09  
**Тестировано с:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}