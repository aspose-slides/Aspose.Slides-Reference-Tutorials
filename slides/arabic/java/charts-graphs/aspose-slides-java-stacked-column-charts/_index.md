---
date: '2026-07-22'
description: تعلم Aspose Slides Maven Dependency لإنشاء مخطط عمودي مكدس في Java، وإضافة
  تسميات البيانات، وتغيير تنسيق أرقام المحور الرأسي، وتصدير النتيجة كملف PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: يتيح لك Aspose Slides Maven Dependency إنشاء مخطط عمودي مكدس في Java،
  وتخصيص تسميات البيانات، وضبط تنسيق المحور الرأسي، وحفظه كملف PPTX – كل ذلك باستخدام
  كود مختصر وجاهز للإنتاج.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: مخطط عمودي مكدس في Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: مخطط عمودي مكدس في Java'
url: /ar/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: مخطط عمودي مكدس في Java

## مقدمة

ارتقِ بعروضك التقديمية من خلال دمج تصورات بيانات بصرية ثاقبة باستخدام قوة **Aspose.Slides for Java**. في هذا الدليل ستقوم **بإنشاء مخطط عمودي مكدس** يبدو احترافيًا، سواء كنت تُعد تقارير أعمال أو تعرض إحصاءات مشروع. في نهاية هذا البرنامج التعليمي ستكون قادرًا على:

- إعداد بيئتك باستخدام **Aspose Slides Maven dependency**
- إنشاء عرض تقديمي من الصفر
- **إضافة مخطط مكدس بنسبة مئوية** وتخصيص مظهره
- **تنسيق تسميات بيانات المخطط** و **تغيير تنسيق أرقام المحور الرأسي**
- **حفظ العرض التقديمي كملف PPTX** بسطر واحد من الشيفرة

## إجابات سريعة
- **ما المكتبة التي أحتاجها؟** أضف تبعية Maven/Gradle `aspose-slides` (انظر “Aspose Slides Maven Dependency” أدناه).  
- **أي نوع مخطط يُنشئ عرضًا مكدسًا؟** استخدم `ChartType.PercentsStackedColumn` لمخطط عمودي مكدس بنسبة مئوية.  
- **كيف يمكنني تغيير تنسيق أرقام المحور؟** استدعِ `IAxis.setNumberFormat()` واضبط `setNumberFormatLinkedToSource(false)`.  
- **هل يمكنني تخصيص تسميات البيانات؟** نعم – كرّر عبر كل `IChartDataPoint` وعيّن `ITextFrame` مخصص.  
- **كيف أحفظ الملف؟** استدعِ `presentation.save("output.pptx", SaveFormat.Pptx)`.

## ما هو المخطط العمودي المكدس؟
المخطط العمودي المكدس يُظهر سلاسل بيانات متعددة مكدسة عموديًا في كل عمود فئة، مع النسخة **المكدسة بالنسبة المئوية** التي تُطبع كل عمود إلى 100 % لتسهيل مقارنة النسب. يتيح هذا الشكل للمشاهدين تقييم مساهمة كل مكوّن في الكل عبر الفئات المختلفة بسرعة، مما يجعل الاتجاهات والأحجام النسبية واضحة على الفور.

## لماذا تستخدم Aspose.Slides for Java؟
Aspose.Slides for Java يتيح لك إنشاء، تعديل، وتحويل ملفات PowerPoint **دون الحاجة إلى Microsoft Office** ويدعم **أكثر من 50 صيغة إخراج** على Windows وLinux وmacOS. تعمل المكتبة بالكامل على JRE، مما يتيح أتمتة الخادم وإنتاج تقارير عالية الإنتاجية. كما توفر تحكمًا دقيقًا في كائنات المخططات، تخطيطات الشرائح، وخصائص المستند، مما يجعلها مثالية لإنشاء عروض تقديمية على مستوى المؤسسات.

## المتطلبات المسبقة
- **مجموعة تطوير جافا (JDK):** 8 أو أعلى  
- **بيئة التطوير المتكاملة (IDE):** IntelliJ IDEA، Eclipse، أو أي محرر متوافق مع Java  
- **أداة البناء:** Maven أو Gradle (اختياري لكن يُنصح به)  
- **معرفة أساسية بجافا** – يجب أن تكون مرتاحًا مع الفئات والطرق  

## إعداد Aspose.Slides for Java
لبدء، أضف مكتبة Aspose.Slides إلى مشروعك.

### تبعية Aspose Slides Maven
أضف ما يلي إلى ملف `pom.xml` (هذه هي **aspose slides maven dependency** التي تحتاجها):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### بديل Gradle
إذا كنت تفضّل Gradle، أدرج هذا السطر في `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### تحميل مباشر
بدلاً من ذلك، قم بتحميل أحدث JAR من [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### الحصول على الترخيص
يمكنك البدء بتجربة مجانية لاستكشاف ميزات Aspose.Slides. لإزالة قيود التقييم، فكر في الحصول على ترخيص مؤقت أو مرخص.

- **تجربة مجانية:** الوصول إلى ميزات محدودة دون تكاليف فورية.  
- **ترخيص مؤقت:** طلب عبر [موقع Aspose](https://purchase.aspose.com/temporary-license/).  
- **شراء:** زر صفحة الشراء للحصول على وصول كامل.

### التهيئة الأساسية
`Presentation` هو الصف الأساسي في Aspose.Slides الذي يمثل ملف PowerPoint في الذاكرة. يوضح المقتطف الأدنى كيفية إنشاء كائن `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## دليل التنفيذ

### إنشاء عرض تقديمي وإضافة شريحة
**نظرة عامة:**  
أولاً، سننشئ عرضًا تقديميًا فارغًا ونتحقق من وجود شريحة.

#### الخطوة 1: تهيئة كائن Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### الخطوة 2: حفظ العرض التقديمي
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### إضافة مخطط عمودي مكدس بنسبة مئوية إلى شريحة
**نظرة عامة:**  
الآن سنضع **مخطط مكدس بنسبة مئوية** على الشريحة الأولى.

`ChartType.PercentsStackedColumn` يحدد نوع مخطط عمودي مكدس بنسبة مئوية.

#### الخطوة 1: تهيئة والوصول إلى الشريحة
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### الخطوة 2: إضافة المخطط إلى الشريحة
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### تخصيص تنسيق أرقام محور المخطط
**نظرة عامة:**  
لتحسين قابلية القراءة سنقوم **بتغيير تنسيق المحور الرأسي** لعرض النسب المئوية.

`IAxis` هو الواجهة التي تمثل محور المخطط، وتسمح بتعديلات التنسيق والقياس.

#### الخطوة 1: إضافة والوصول إلى المخطط
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### الخطوة 2: ضبط تنسيق الرقم المخصص
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### إضافة سلاسل ونقاط بيانات إلى المخطط
**نظرة عامة:**  
سنملأ المخطط بسلاسل بيانات نموذجية.

#### الخطوة 1: تهيئة العرض التقديمي والمخطط
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### الخطوة 2: إضافة سلسلة بيانات
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### تنسيق لون تعبئة السلسلة
**نظرة عامة:**  
امنح كل سلسلة لونًا مميزًا لجعل المخطط أسهل للقراءة.

#### الخطوة 1: تهيئة والوصول إلى المخطط
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### الخطوة 2: ضبط ألوان التعبئة
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### تنسيق تسميات البيانات
**نظرة عامة:**  
الآن سنقوم **بتنسيق تسميات بيانات المخطط** لتعرض نصًا مخصصًا.

`IChartDataPoint` يمثل نقطة بيانات فردية داخل سلسلة المخطط، و `ITextFrame` يحتوي على نص التسمية.

#### الخطوة 1: الوصول إلى سلاسل المخطط ونقاط البيانات
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### الخطوة 2: تخصيص تسميات البيانات
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## المشكلات الشائعة والحلول
- **المخطط يظهر فارغًا:** تأكد من أنك أضفت على الأقل سلسلة بيانات واحدة ونقطة بيانات قبل الحفظ.  
- **أرقام المحور لا تظهر النسب المئوية:** تذكر ضبط `verticalAxis.setNumberFormatLinkedToSource(false)`؛ وإلا سيتجاهل التنسيق المخصص.  
- **رسالة تقييم الترخيص:** استخدم ملف ترخيص صالح قبل إنشاء كائن `Presentation` لتقليل بانر التقييم.

## الأسئلة المتكررة

**س: هل يمكنني استخدام هذا الكود مع Java 11 أو أحدث؟**  
ج: نعم. المكتبة تدعم JDK 8+؛ فقط استخدم المصنف المناسب (مثلاً `jdk16` لـ JDK 16 أو أحدث).

**س: كيف أصدّر المخطط كصورة بدلاً من PPTX؟**  
ج: استخدم `chart.getImage().save("chart.png", ImageFormat.Png);` بعد إضافة المخطط إلى الشريحة.

**س: هل يمكن إضافة مفتاح توضيحي إلى المخطط العمودي المكدس؟**  
ج: بالتأكيد. استدعِ `chart.getChartTitle().addTextFrameForOverriding("My Chart");` وقم بتكوين `chart.getLegend()` حسب الحاجة.

**س: ماذا لو احتجت لتحديث البيانات بعد إنشاء العرض التقديمي؟**  
ج: يمكنك تعديل خلايا `ChartDataWorkbook` ثم استدعاء `chart.refresh();` لتطبيق التغييرات.

**س: هل يعمل Aspose.Slides على خوادم Linux؟**  
ج: نعم. المكتبة جافا صافية وتعمل على أي نظام تشغيل يحتوي على JRE متوافق.

## الخلاصة
باتباعك لهذا الدليل تعلمت كيفية **إنشاء مخطط عمودي مكدس** في Java باستخدام **Aspose Slides Maven Dependency**، من إعداد البيئة إلى تنسيق بصري متقن. جرّب مجموعات بيانات مختلفة، ألوانًا، وتنسيقات تسميات لتجعل تقاريرك تبرز حقًا.

---

**آخر تحديث:** 2026-07-22  
**تم الاختبار مع:** Aspose.Slides 25.4 (jdk16 classifier)  
**المؤلف:** Aspose  

{{< blocks/products/products-backtop-button >}}

## دروس ذات صلة

- [كيفية إنشاء مخطط عمودي مجمع في Java باستخدام Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [كيفية ضبط تنسيقات الأرقام في نقاط بيانات المخطط باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [كيفية إضافة وتكوين المخططات في العروض التقديمية باستخدام Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}